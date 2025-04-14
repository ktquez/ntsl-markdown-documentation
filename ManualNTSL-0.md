# Introdução

A  NTSL  (Nelogica  Trading  System  Language)  é  uma  poderosa  linguagem  criada  com  um  único propósito:  permitir  o  desenvolvimento  dos  melhores  e  mais eficientes  sistemas  algorítmicos  de operação. A Nelogica oferece juntamente com a NTSL um ambiente de criação pioneiro e revolucionário chamado  AlgoTools.  Com  o  AlgoTools  é  possível  codificar,  testar  e  simular  com  grande  agilidade qualquer estratégia de operação. Na NTSL, o usuário encontra uma grande facilidade no momento de criação de suas estratégias, a possibilidade de criar toda ela em português, havendo assim, a facilidade e fácil entendimento da estratégia criada.

# Estrutura de uma Estratégia

Observe o trecho de código abaixo que representa o indicador média móvel. Esse código apresenta as três áreas que definem a estrutura de uma estratégia. São elas: área de declaração de parâmetros de entrada, área de declaração de variáveis e funções e área de código.

```
///////////////////////////////////////////////////////////////
//                                                          //
//                Cruzamento de Médias                      //
//                                                          //
///////////////////////////////////////////////////////////////

input
  FastAverage(9);
  SlowAverage(21);

var
  sAvgFast     : Float;
  sAvgSlow     : Float;
  sPrevAvgFast : Float;
  sPrevAvgSlow : Float;

begin
  ///////////////////////////////////////////////////////////////
  // Armazena os valores das médias em variáveis de apoio      //
  sAvgFast     := Media(FastAverage, Close);
  sAvgSlow     := Media(SlowAverage, Close);
  sPrevAvgFast := sAvgFast[1];
  sPrevAvgSlow := sAvgSlow[1];

  ///////////////////////////////////////////////////////////////
  // Verifica se as condições de disparos de alarmes           //
  // foram satisfeitas                                         //
  if (sPrevAvgFast < sPrevAvgSlow) and (sAvgFast > sAvgSlow) then
    Alert(clGreen)
  else if (sPrevAvgFast > sPrevAvgSlow) and (sAvgFast < sAvgSlow) then
    Alert(clRed);
end;
```

## Área de declaração de parâmetros de entrada

Na área de declaração de parâmetros de entrada informamos todos os parâmetros externos que a estratégia usará. Esses parâmetros são fundamentais, pois:

- Definem a interface com o mundo externo, ou seja, é onde usuário poderá alterar e o que servirá como parâmetro de chamada caso a estratégia seja utilizada em outra interface/estratégia.
- Define os itens que serão analisados no processo de otimização.

Para definir um parâmetro: NOME_DO_PARÂMETRO (VALOR_DE_INICIALIZAÇÃO)

Exemplo:

```
Preco(Close); // Define um parâmetro inicializado com o valor de fechamento de preços da série de dados
Periodo(2); // Define um parâmetro chamado Perioro como valor 2
```

## Área de declaração de variáveis e funções

Na área de declaração de variáveis informamos todas as variáveis que serão utilizadas na estratégia. Nesta região também descrevemos funções que desejamos usar no código. As funções devem ser sempre codificadas após a declaração das variáveis.

Para declarar uma variável: NOME_DA_VARIAVEL: TIPO

Exemplo:
```
sResult : Float; // Cria uma variável chamada sResult do tipo ponto flutuante
nIndex: Integer; // Cria uma variável chamada nIndex para armazenar números inteiros
```

## Área de código

Nesta parte descreve-se o código propriamente dito, ou seja, as regras que utilizam parâmetros, variáveis e outros dados para calcular sinais e indicadores.

# Fluxo de Execução de uma Estratégia

O código de uma estratégia é executado de maneira sequencial. Porém, ele é executado
sequencialmente candle por candle, como se houvesse um laço que percorre toda série de dados de
um ativo.

Sendo assim, a sequência de comandos existente na área de código será executada uma vez para
cada candle existente. Para cada candle, será executado o código da estratégia em um loop implícito. A
regra em pseudocódigo é, portanto:

- Tendo uma série de dados X de tamanho N;
- Para cada item X[i], com i variando de 0 até N-1, executa-se a área de código da estratégia;
- A cada novo dado do ativo, o código da estratégia continua sendo executado, avaliando o último
e o penúltimo candle;

## Importante:
- O mesmo candle pode ser processado diversas vezes. Isso ocorre muito em tempo real, onde
cada trade pode gerar uma notificação de reprocessamento do fluxo de execução.
- Quando uma ordem é executada, o fluxo de execução reprocessa o mesmo candle para ativar
as ordens Covers.
- Dependendo da notificação dos candles, podem ser reprocessados candles passados. Isso deve
ser levado em consideração pelo programador.
- Sempre que um candle passado é reprocessado, serão reprocessados todos candles até o atual.
- Em tempo real, quando o código está executando ao mesmo tempo que recebe novos dados do
mercado, o código da estratégia é executado diversas vezes para o último e o penúltimo candle
durante a execução, podendo também executar em candles passados.

Esses processamentos podem alterar valores de variáveis globais ou de série, e podem causar
mudanças na coloração para candles passados ou mudança de comportamento quando o código é
pausado e executado novamente.

Quando estiver utilizando séries em sua estratégia, é importante lembrar que o primeiro tick do candle
terá o valor [0] zerado. Como comentamos anteriormente, sua estratégia será executada não apenas no
último candle e sim também ao passado, devido aos cálculos que precisam ser feitos para garantir que
a NTSL funcione corretamente. É importante ressaltar que não se pode assumir que um candle no
passado não será avaliado, porém, se desejar, é possível inibir o recálculo de algum valor utilizando a função LastBarOnChart() em uma condição no início do código para evitar isso. É fundamental
compreender que o [0] sempre está se referindo ao candle que está sendo avaliado, e não
necessariamente será do último candle.

# Variáveis, tipos de dados e constantes

As variáveis são utilizadas para armazenar dados, conforme seu tipo específico.

## Tipos de dados

**Float ou Real** - Representa números de ponto flutuante.
**Integer ou Inteiro** - Representa números inteiros.
**Boolean ou Booleano** - Representação lógica: True ou Verdadeiro e False ou Falso
**Serie** - Representa uma série de dados.

A NTSL suporta a conversão implícita de valores Float a Inteiros, isto é, atribuir um valor Float
diretamente a um valor Integer. O valor inteiro será o valor do ponto flutuante, descartandoas casas
decimais. Por exemplo, se eu atribuir 2.99”ou 2.35 a um inteiro, o valor do inteiro será 2. Para outros comportamentos de arredondamento, a linguagem disponibiliza as funções Ceiling, Floor e Round. Para mais detalhes sobre essas funções, consulte esse mesmo manual na seção de funções.

As variáveis na linguagem oferecem uma flexibilidade muito maior do que na maioria dos sistemas de
programação conhecidos.

Todas as variáveis são globais, e deve ser dada uma atenção especial quando utilizadas. Ao programar
usando variáveis globais, deve ser levado em consideração o comportamento do processamento do
fluxo de execução, a cada vez que o fluxo de execução é realizado as variáveis podem ter seu valor
alterado com base no último valor que tinham.

Quando uma variável for acessada utilizando colchetes (exemplo: [x]), ela será considerada uma série
de dados pelo compilador. Seu comportamento é diferente: séries iniciam cada candle com seu valor
zerado. Também é possível navegar entre valores atuais e passados, mediante indexação.

## Séries de dados

As séries de dados são utilizadas para obter dados específicos de cada Candle.

### Séries:

**Open ou Abertura** - Retorna o valor de abertura de cada candle.
**Close ou Fechamento** - Retorna o dado de fechamento.
**Low ou Minima** - Retorna o valor de mínima
**High ou Maxima** - Retorna o dado de máxima.
**Quantity ou Quantidade** - Retorna o valor de contratos negociados de cada candle
**Volume** - Retorna o dado de volume financeiro de cada candle

### Arrays

Análogo ao tipo Serie, a estrutura de um Array permite o armazenamento de dados de um tipo
específico, contudo, após sua criação, seu comprimento será fixo, o que permite uma alocação menor
de memória.

O acesso aos elementos de um Array é efetuado mediante indexação.

#### Estrutura da declaração:

 ```
var
  Variavel : Array[Tamanho] Of Tipo;
 ```

A fim de exemplificação, segue um exemplo de declaração de um Array estático de 10 elementos, o
qual é preenchido com valores de 1 a 10 (primeira estrutura de repetição), e efetuado o somatório dos
valores:

```
var
  i, sum : Integer;
  lista : array[1..10] of Integer;

begin
  for i:=1 to 10 do
    lista[i] := i;

  sum:=0;
  for i:=1 to 10 do
    sum:=sum+i;
    
  Plot(sum);
end;
```

## Correlação de múltiplos ativos

É possível ainda acessar os dados, ao utilizar o recurso Asset, onde é necessário parametrizar o ativo
específico, e a bolsa a qual pertence. As bolsas visualizadas na plataforma dependem se o usuário
possui acesso a elas. Na documentação na plataforma está disponível, na aba constantes, apenas os
feeds que o usuário terá acesso.

Bolsas que podem ser parametrizadas:
- feedBMF
- feedBMFSynthetic
- feedBovespa
- feedCME
- feedDowJones
- feedEconomic
- feedNasdaq
- feedNyse
- feedActivTrades

### Estrutura da declaração:

```
const
  variavel = Asset("nomeDoAtivo", feedNOMEDABOLSA);
```

A seguir, um exemplo de declaração, e acesso aos dados de fechamento e abertura:

```
const
  WDOFUT = Asset("WDOFUT", feedBMF);

begin
  Plot(WDOFUT.close);
  Plot2(WDOFUT.open);
end;
```

Além do acesso às séries de dados, pode-se retornar o ticker (String) e bolsa (String) do Asset
declarado, a partir das funções GetAsset e GetFeed:

```
const
  WDO = Asset("WDOFUT", feedBMF);

begin
  if(MaxBarsForward = 0) then
  PlotText("Ticker: " + WDO.GetAsset + " - Bolsa: " + WDO.GetFeed, clRed, 0, 7);
end;
```

É possível inclusive declarar N ativos, a fim de correlacionar os dados para implementação da
estratégia.

A seguir, um exemplo de coloração, onde será aplicada a cor verde, caso o fechamento do WDO estiver
acima de sua média (20 períodos), e o ativo WIN, fechando abaixo de sua média (20 períodos).
A coloração vermelha será aplicada, caso o fechamento do WDO estiver abaixo da média, e o último
preço do WIN acima de sua média.

A coloração cinza será identificada, caso não sejam satisfeitas as condições.

```
const
  WDO = Asset("WDOFUT", feedBMF);
  WIN = Asset("WINFUT", feedBMF);

input
  Periodo(20);

var
  wdoMedia : Float;
  winMedia : Float;

begin
  wdoMedia := MediaExp(Periodo, WDO.close);
  winMedia := MediaExp(Periodo, WIN.close);
  
  if(WDO.close > wdoMedia) and (WIN.close < winMedia) then
    PaintBar(clLime)
  else if(WDO.close < wdoMedia) and (WIN.close > winMedia) then
    PaintBar(clRed)
  else
    PaintBar(clGray);

end;
```

**Atenção:** Ao utilizar gráficos atemporais em conjunto com múltiplos ativos, as avaliações de
fechamento de candle serão feitas sempre em função do fechamento de candle do ativo principal.
Nesse momento, os ativos auxiliares não necessariamente terão seus fechamentos no mesmo
momento, já que esses gráficos são atemporais, e não respeitam o mesmo critério de fechamento:
tempo.

Por conta disso, é esperado que o backtest ou o replay tenham resultados diferentes da automação
(que acontece nos ativos em tempo real), isso porque, em tempo real, não se está levando em conta o
mesmo candle fechado para a análise dos dados e, em backtest ou replay, o backtest pode estar
olhando para candles que já estão completos, ou seja, fecharam após o fechamento do candle do ativo
principal. Isso se deve ao fato que no backtest, só avaliamos candles já fechados e não há
conhecimento do tick-a-tick dentro do candle. Deste modo, depois do candle do ativo principal ter
fechado, os candles de outros ativos ainda estavam em formação

## Acessando dados anteriores

O dado atual de uma variável pode ser descrito por Variavel[0]. O número entre colchetes indica o
dado de quantos períodos anteriores deseja-se acessar (sendo 0, portanto, da barra corrente). Para
ilustrar melhor, vamos a um exemplo:

```
sResult := Preco[1];
```

A linha de código acima está atribuindo o valor da variável Preco[1] para a variável sResult. Imagine
que Preço corresponde a todos os valores de fechamento da série de dados de um certo ativo, como
na tabela abaixo:

Exemplo:

Data | Posição | Valor
05/10/2010 | Close[0] | 12.43
04/10/2010 | Close[1] | 12.40
01/10/2010 | Close[2] | 11.39
30/09/2010 | Close[3] | 12.51

Portanto, Preco[1] refere-se ao valor de ontem do preço de fechamento (sResult vale então 12,40 em
nosso exemplo). Dessa forma, o número inteiro que especificarmos entre colchetes indica ao sistema
quantos períodos no passado deve-se acessar a informação.

## Constantes

São utilizadas para a inserção de parâmetros de determinadas funções, estes valores não
podem ser alterados pelo usuário.

### Lado da Ordem:
- **osBuy** ou osCompra: Ordem de compra.
- **osSell** ou osVenda: Ordem de venda.

### Opções:
- **optCall** - Opção de compra.
- **optPut** - Opção de venda.

### Tipo de Ordem:
- **otLimit** - Tipo limite.
- **otMarket** - A mercado.
- **otStopLimit** - Tipo stop.

### Cores:
- **clAqua ou clAzulClaro** - Cor azul-claro
- **clBlack ou clPreto** - Cor preta
- **clBlue ou clAzul** - Cor azul
- **clCream ou clCreme** - Cor creme
- **clDkGray ou clCinzaEscuro** - Cor cinza-escuro
- **clFuchsia ou clFucsia** - Cor fúcsia
- **clGray ou clCinza** - Cor cinza
- **clGreen ou clVerde** - Cor verde
- **clLime ou clVerdeLimao** - Cor verde-limão
- **clLtGray ou clCinzaClaro** - Cor cinza-claro
- **clMaroon ou clMarrom** - Cor marrom
- **clMedGray ou clCinzaMedio** - Cor Cinza médio
- **clMoneyGreen ou clVerdeClaro** - Cor verde-claro
- **clNavy ou clAzulMarinho** - Cor azul-marinho
- **clOlive ou clVerdeOliva** - Cor verde-oliva
- **clPurple ou clPurpura** - Cor púrpura
- **clRed ou clVermelho** - Cor vermelha
- **clSilver ou clPrata** - Cor prata
- **clSkyBlue ou clAzulClaro** - Cor azul-claro
- **clTeal** - Cor Verde-azulado
- **clWhite ou clBranco** - Cor branca
- **clYellow ou clAmarelo** - Cor amarela

## Controle de Fluxo

As instruções de fluxo são utilizadas para administrar a sequência de execução das
instruções dentro de um programa. A NTSL apresenta três tipos desse tipo:

### If then else

Se (condição) for verdadeiro executa-se a listagem (comandos 1), caso (condição) seja
falso executa-se (comandos 2). Tanto (comandos 1) quanto (comandos 2) podem ser
sequências de instruções.

A expressão (condição) pode ser qualquer tipo de teste que resulte em verdadeiro ou falso, alguns
exemplos:

```
if(Close > Close[1])
if(nIndex = 10)
if(bCond = false) and (Volume > 1000)
```
A seguir um exemplo de coloração de candles de acordo com a condição presente no **If then else** .

```
begin
  if(close = close[1]) then
    PaintBar(clYellow)
  else if(close > close[1]) then
    PaintBar(clGreen)
  else
    PaintBar(clRed);
end;
```

Se o valor de fechamento da barra atual (Close equivale a Close[0]) for igual ao fechamento da barra
anterior (Representado por Close[1]) executa-se o código que segue a palavra reservada **THEN**
**(ENTÃO)**. Caso contrário, o sistema executa o código subsequente até chegar na palavra reservada
**ELSE (SENÃO)**

## For (To / DownTo) Do

O comando **FOR** é utilizado para definir um loop controlado, ou seja, o bloco é executado
repetidamente até que a variável de contagem saia do valor inicial e atinja o valor final.

Para a variável controladora, pode-se incremetá-la, a partir do comando To, ou decrementá-la, ao
utilizar na estrutura o **DownTo**.

**Exemplo (For To Do):**
Observe o código da média móvel, a variável de contagem nIndex começa com o valor 0 e deve
chegar ao valor de Periodo – 1. No exemplo, Periodo foi definido como parâmetro de entrada, para
definir o tamanho da média.

Assim, caso seja parametrizado o valor 0 (Periodo), o comando FOR criará um loop de 9 iterações (de
0 até 8) para cada barra, calculando assim o valor médio para a posição atual.

```
input
  Preco(close);
  Periodo(9);

var
  sResult : Float;
  nIndex : Integer;

begin
  sResult := 0;
  for nIndex := 0 to Periodo -1 do
    begin
      sResult := sResult + Preco[nIndex];
    end;
  Plot(sResult / Periodo);
end;
```

**Exemplo (For To Do x For DownTo Do)**:
A fim didático, segue um exemplo de cálculo de fatorial, utilizando as duas estruturas.

### For To Do

```
input
  n(6);
var
  fatorial : Integer;
  i : Integer;

begin
  fatorial:=1;
  For i:=1 To n Do
    fatorial := fatorial * i;

  Plot(fatorial);
end;
```

### For DownTo Do

```
input
  n(6);
var
  fatorial : Integer;
  i : Integer;

begin
  fatorial:=1;
  For i:=n DownTo 1 Do
    fatorial := fatorial * i;

  Plot(fatorial);
end;
```

## While
A execução da estratégia ao chegar no comando WHILE testa o resultado de (condição). Caso
(condição) seja verdadeiro (true) a listagem (comandos) é executada. Após a execução a (condição)
volta a ser testada, assim, o loop apenas irá se encerrar quando (condição) deixar de ser verdadeira.

**Exemplo:**
No código a seguir, reescrevemos o indicador média móvel utilizando a instrução **WHILE (ENQUANTO)**
ao invés de **FOR (PARA)**

```
input
  Preco(close);
  Periodo(9);

var
  sResult : Float;
  nIndex : Integer;

begin
  sResult := 0;
  nIndex := 0;

  while(nIndex <= Periodo -1) do
    begin
      sResult := sResult + Preco[nIndex];
      nIndex := nIndex + 1;
    end;

  Plot(sResult/Periodo);
end;
```

## Repeat

Este comando difere-se do For e While, no sentido de que a condição será testada no final da estrutura, e não no início, portanto, as instruções do bloco serão executadas pelo menos uma vez.

**Exemplo**:
A fim de comparação com as outras estruturas já abordadas, segue o exemplo de cálculo de fatorial:

```
input
  n(5);

var
  fatorial : Integer;
  i : Integer;

begin
  fatorial:=1;
  i := n;
  repeat
    begin
      fatorial := fatorial * i;
      i:=i-1;
    end
  until (i=1);

  Plot(fatorial);
end;
```

# Operadores
Os operadores constituem os símbolos matemáticos e lógicos usados em cálculos e comparações.

## Operadores matemáticos
Os operadores matemáticos são:

Operador | Descrição | Exemplo | Resultado
+ | Adição | 5+4 | 9
- | Subtração | 5-4 | 1
* | Multiplicação | 5*4 | 20
/ | Divisão | 5/4 | 1,25

O operador de divisão possui a maior força de precedência, seguido por multiplicação. Assim,
como consta na imagem abaixo:

Expressão | Resultado
10*10/5+2 | 22
10*10+ | 102
50+100*10/2-1 | 549

## Operadores lógicos

Os Operadores lógicos são utilizados principalmente para comparações.

**"E" lógico**

Representado pela palavra reservada and (e), retornará TRUE somente quando as duas
condições de teste forem verdadeiras conforme Tabela Verdade abaixo:

Condição 1 | and | Condição 2 | Resultado
false | and | false | false
false | and | true | false
true | and | false | false
true | and | true | true

**"OU" lógico**

Representado pela palavra reservada or (ou) , retornará TRUE (verdadeiro) sempre que pelo
menos uma das condições de teste for verdadeira, conforme Tabela Verdade abaixo:

Condição 1 | or | Condição 2 | Resultado
false | or | false | false
false | or | true | true
true | or | false | true
true | or | true | true

## Funções
Conforme visto, funções são declaradas e descritas na área de declaração de variáveis e
funções, abaixo um exemplo de funções

```
input
BreakPeriodo (5);
HiLoPeriodo (3);

var
  bBuy : Boolean;
  bShor : Boolean;
  sMax : Float;
  sWin : Float;
  sWinHiLo : Float;
  sMaxHiLo : Float;
  fPlot : Float;

function Max(Values : Float; nPeriodo : Integer): Float;
var
  nIndex : Integer;
  sAux : Float;
begin
  sAux := Values;
  Result := sAux;
  
  For nIndex := 0 to nPeriodo - 1 do
  begin
    if (sAux[nIndex] > Result) then
    begin
      Result := sAux[nIndex];
    end;
  end;
end;

begin
  fPlot := Max(Close, 5);
  Plot(fPlot);
end;
```

### Criando Funções (Sintaxe)

```
Function (funcao) Nome da Função ((parâmetro 1 : TIPO); (parâmetro 2: TIPO:);(parâmetro
n: TIPO)): Tipo de Retorno
  Begin(inicio)
    Comandos
  End (fim);
```

## Funções de biblioteca
Além do usuário poder criar seus próprios indicadores, é possível utilizar a biblioteca do sistema, ou
seja, o usuário pode utilizar estratégias já criadas em novas.

Dentro das funcionalidades de bibliotecas, o usuário poderá colorir os gráficos de acordo com as
condições determinadas pelo seu indicador

### Funções Matemáticas
As funções matemáticas têm como finalidade implementar as seguintes funcionalidades:

- Power(valor,potência): Tem como funcionalidade, gerar valores elevados em determinada
potência;
- Round(valor): Tem como funcionalidade, arredondamento de números quebrados, caso o valor
após a vírgula seja menor do que cinco, arredonda para baixo, caso contrário, arredonda para
cima;
- Sqrt(valor): Tem como funcionalidade mostrar a raiz quadrada de valores desejados pelo
usuário;

### Funções Gráficas
Como visto anteriormente, a função Plot realiza a ligação dos valores gerados na estratégia e cria
gráficos de linhas, mas caso haja a necessidade, o usuário também poderá colorir o gráfico de acordo
com o desejado.

Esta funcionalidade denominada PaintBar(cor) permite ao usuário, colorir o gráfico com cores em
determinadas situações do indicador, como na imagem abaixo(as cores podem ser determinadas por
Strings , ou a partir da função RGB):

```
begin
  if (Close = Close[1]) then
  begin
    PaintBar(clYellow);
  end
  else if (Close > Close[1]) then
  begin
    PaintBar(clGreen);
  end
  else
  begin
    PaintBar(clRed);
  end;
end;
```

## Back-Testing

A funcionalidade de Back-testing permite ao usuário avaliar uma determinada estratégia, teoria ou
modelo através de uma análise de dados históricos.

Lista de funcionalidades utilizadas para Back-Testing:
- Lista de funções;
- Criar regra de execução;
- Execução da estratégia.

Após criada a estratégia de Back-Testing, para ser adicionado diretamente no gráfico, clique no botão
direito sobre o mouse e selecione a opção "Inserir Regra de Execução".

O código de back-testing simula o mesmo comportamento da automação, as simulações de execução
de ordens são processadas todas ao final do fluxo de execução do candle. Quando ocorre aumento de
posição ao final do fluxo de execução, o código é reprocessado para ativar as ordens de cobertura da
operação (ordens ToCover). O usuário pode observar esse comportamento quando utilizar o modo
debug.

## Automação de Estratégias

O módulo de Automação de Estratégias tem o objetivo de automatizar as estratégias de execução
criadas no Editor de Estratégias. Ele está disponível nas versões mais avançadas das plataformas
Nelogica, em modo simulação de forma gratuita e disponível para contas reais por meio de módulos
opcionais.

O novo módulo de automação espelha o funcionamento do backtest das estratégias para execução de
ordens reais e em simulador. Para fazer o gerenciamento dessas automações pode-se acessar o menu
Estratégias > Automação de Estratégias.

A janela de Automações de Estratégias permite que possamos criar e gerenciar automações,
acompanhar o resultado de todas as automações de maneira simplificada. Caso queira um
detalhamento maior da automação pode-se clicar com o botão direito e ir em Detalhes. Nos detalhes é
possível acompanhar todos os eventos que a execução gerou, assim como diversos indicadores de
performance da automação.

## Criando uma estratégia de execução


Para criar uma automação você precisará criar uma estratégia de execução, que pode ser criada a partir
do Editor de Estratégias. Se você já sabe o que é isso, pode seguir para o próximo passo.

Ao abrir o Editor de Estratégias, você pode criar sua estratégia de execução utilizando funções de
backtest (essas funções irão caracterizar a estratégia como sendo uma estratégia de execução e isso
possibilitará a sua seleção no próximo passo para que a estratégia seja automatizada). Para criar uma
estratégia de execução você deve usar funções do módulo backtest, que pode ser visto na imagem
abaixo:

Sugerimos que você utilize a função Nova estratégia, e selecione exemplos de estratégias de execução
se você não estiver familiarizado com programação ou com o Editor de Estratégias

Abaixo é apresentado um exemplo de estratégia, utilizando o indicador IFR/RS, que pode ser utilizado
no módulo de estratégias automatizadas:

```
///////////////////////////////////////////////////////////////////
// IFR //
///////////////////////////////////////////////////////////////////
begin
  // Verifica se está comprado
  if (IsBought) then
    begin
      // Fecha a posição com uma venda caso o IFR
      // esteja superior a 70 (sobrecomprado)
      if (RSI(9, 0) > 70) then
        SellToCoverAtMarket;
    end
  // Verifica se está vendido
  else if (IsSold) then
    begin
      // Fecha a posição com uma compra caso o IFR
      // esteja inferior a 30 (sobrevendido)
      if (RSI(9, 0) < 30) then
        BuyToCoverAtMarket;
    end
  // Verifica se deve abrir uma posição,
  // com o ativo sobrecomprado ou sobrevendido
  else if (RSI(9, 0)[1] < 30) and (RSI(9, 0) > 30) then
    BuyAtMarket
  else if (RSI(9, 0)[1] > 70) and (RSI(9, 0) < 30) then
    SellShortAtMarket;
end;
```

### Criando uma automação

Para criar uma nova automação basta abrir a interface de controle e localizar o botão “Nova Automação”
localizada no menu superior da janela (indicado pelo número 1 na imagem), este botão estará sempre
disponível para e visível na janela. No entanto, caso ainda não possua nenhuma automação criada, o
mesmo botão “Nova Automação” será apresentado em destaque no centro da tela.

Após clicar nesse botão será aberta a janela de criação da da estratégia automatizada onde será
configurada os parâmetros da automação em duas etapas. A primeira etapa contém configurações
essenciais e obrigatórias para a criação da automação.

Na primeira etapa, nas configurações obrigatórias, é possível definir a conta, a estratégia de execução, ativo alvo, quantidade por ordem, quantidade máxima da posição e o período que a estratégia usará como base para as análises.

A Estratégia de execução é o “cérebro” da automação. Aqui será selecionado aquela estratégia
implementada no editor. Ao clicar no botão “Selecionar Estratégia” estarão listadas todas as estratégias de execução presentes na plataforma. Além disso, caso a estratégia selecionada possua parâmetros de entrada, os mesmos serão listados nessa janela para que possam ser editados da melhor maneira para a estratégia específica.

A próxima etapa contém configurações opcionais que podem ser exploradas nos menus acima quando
as Configurações Avançadas estiverem ativas (canto inferior esquerdo). Aqui podemos configurar
opções de Entrada e Saída, Risco e Segurança. Essas opções estão detalhadas a seguir:

### Opções de entrada

Nesta seção é possível especificar parâmetros que alterem a estratégia de abertura de ordens da
automatização.

Em ordem de entrada você pode especificar qual vai ser o tipo de abertura de posição, ou seja, se a
estratégia irá abrir novas posições apenas de compra, ou apenas de venda ou ambos os lados.
Em horário de entrada é possível especificar o período de tempo em que a estratégia se manterá
habilitada. Após o horário final a estratégia é pausada. Ao desabilitar esta configuração, a estratégia permanecerá executando até o usuário pausá-la ou que o software seja encerrado.
É possível também escolher se você deseja confirmar cada ordem de aumento de posição. Neste caso,
a confirmação de ordens será mostrada para cada nova ordem da estratégia.

### Modo de Execução

Há dois modos de execução: Realizar envio de ordens no fechamento do candle e Realizar envio de
ordens quando a condição for satisfeita, também chamado de modo Tick a Tick. A mudança de uma
opção para a outra causa grande impacto na maneira como o código da estratégia é interpretado.
Abaixo, é detalhado como cada modo se comporta.

### Ordens no Fechamento do Candle

Esta é a configuração padrão do modo de execução da automação e é a que traz maior semelhança
com as operações realizadas por meio do backtest no Editor de Estratégias. Para ativar este modo
selecione a opção “Realizar envio de ordens no fechamento do candle”.

A cada fechamento de candle, o código para envio de ordens é reavaliado e se torna disponível para o
envio de novas ordens de entrada, ou a alteração de ordens de entrada abertas ou de ordens Cover,
caso haja posição. Deste modo, a escolha de tempo gráfico é crucial para sua automação.

Ordens que aumentem a exposição para o mercado e foram enviadas ao final de um candle e que não
forem executadas até o final do candle seguinte serão canceladas ou editadas quando o próximo candle
finalizar, de acordo com a estratégia do usuário. Uma vez que, apenas sabemos que um candle foi
finalizado quando o próximo iniciar em gráficos atemporais, poderá ocorrer a execução de ordens em
um candle subsequente caso o cancelamento chegue na bolsa após a execução da mesma.

É importante ressaltar que a automação poderá apresentar divergências em relação ao backtest ao ser
comparado com a execução da automação em uma conta de simulação (ordens simuladas) ou conta real (ordens reais), operando ao vivo no mercado real. Isso se deve a diversos fatores, como: Spread,
Margem, RLP, Delays na Bolsa, Alta volatilidade de preço de alguns ativos, entre outros.

Essas diferenças acontecem primordialmente em séries de dados atemporais, as quais podem causar a
criação de muitos candles em pouco tempo. No backtest, por termos zero delay, as ordens são criadas
sempre no candle subsequente, porém no mercado real, onde há delay, por menor que ele seja, ordens
podem ser executadas em candles subsequentes já que não houve tempo na criação do cancelamento
dessas ordens.

Além disso, há uma segunda opção caso esse modo seja selecionado. Ativando essa função, você terá
uma execução mais próxima ao backtest, já que o código executará apenas no fechamento do candle
ou com uma atualização de posição. Com a opção desativada, o código é executado diversas vezes no
mesmo candle.

## Ordens ao Satisfazer Condição
Este é o modo avançado de envio de ordens automatizadas, ele não é compatível com o backtest da
aplicação, já que realiza operações a qualquer momento durante a formação dos candles, e fazendo
com que o backtest não consiga simular esse modo de execução. Para ativar este modo selecione a
opção “Realizar envio de ordens quando a condição for satisfeita”.

Neste modo, o código é constantemente avaliado durante a execução da automação e as ordens
podem ser enviadas a qualquer momento durante o candle, uma vez que seu código satisfaça a
condição de envio. Como pode ser visto na imagem acima, existem duas opções que podem ser
escolhidas para este modo. Detalhamos abaixo cada uma delas.

A primeira opção, “Esperar o fechamento do candle para primeira execução” faz com que a
automação aguarde o candle atual que está aberto para começar a executar ordens. Ou seja, apenas
quando um novo candle for criado que ordens serão enviadas.

A segunda opção, “Permitir múltiplos envios e alterações de ordens para a mesma barra” quando
selecionada, faz com que a automação envie e modifique ordens de entrada e saída a medida que o
código satisfazer as condições de envio, mantendo um tempo mínimo entre alterações para proteção de
flood de ordens. Caso esta opção não for selecionada, a automação irá limitar o envio de ordens e
modificações para apenas 1 vez por barra, quando a condição no seu código for satisfeita.

A estratégia de atualização das ordens, quando a opção de múltiplos envios de ordens para a mesma
barra estiver selecionada, seguirá uma equação linear que dependerá de quão perto as ordens sendo
enviadas ou modificadas estão do preço atual, ou seja, caso as ordens estiverem muito longes do preço
atual, suas ordens serão atualizadas menos frequentemente, e caso suas ordens estiverem muito
próximas do preço atual, as ordens serão atualizadas mais frequentemente. Lembrando, todas ordens
serão atualizadas ao mesmo tempo, o que vai importar é sempre a ordem mais próxima do preço para a
decisão da frequência de atualização. As ordens tem um limite mínimo de atualização de 10 segundos,
deste modo elas serão enviadas/alteradas de no máximo de 10 em 10 segundos.

O temporizador de envio de ordens só atualiza quando alguma modificação de ordem é enviada, ou
seja, se o código executado enviar alguma ordem diferente das que já estão apregoadas, ele irá avaliar
quando foi a última modificação feita e quando deverá fazer a próxima modificação e então liberar novos envios e modificações de ordens.


> { deprecated } A configuração antiga de número de ordens por candle não existe mais, vimos que ela mais atrapalhava o usuário do que ajudava, e escolhemos seguir em uma estratégia mais segura e inteligente.

> Caso você havia configurado mais de uma ordem por candle para sua automação, a sua configuração irá automaticamente para “Permitir múltiplos envios e alterações de ordens para a mesma barra”, caso estivesse configurado para apenas uma, essa opção virá desselecionada

Da mesma forma que o modo de atualização no fechamento do candle, as ordens de saída sempre
serão atualizadas quando houver um aumento de posição para rebalanceamento das ordens de
cobertura.

O modo de execução Tick a Tick é recomendado para que as estratégias se beneficiem do tempo real,
já que o candle que será constantemente avaliado é o último candle da série que ainda está aberto. Este modo permite que a entrada seja executada imediatamente na condição especificada, por
exemplo, um cruzamento de médias, ou quando o preço romper um determinado patamar estabelecido.

Relembrando, esse modo não é compatível com o backtest de estratégias de execução, pois depende
dos dados em tempo real, não sendo possível realizar uma previsão de como a automação irá se
comportar. Para testes de performance de sua estratégia tick-a-tick é necessário o uso do replay, ou o
teste no pregão real, utilizando sua conta de simulação.

## Opções de saída
Nesta outra etapa da configuração, é possível alterar configurações de saída de sua automação.
Aqui é possível configurar uma estratégia OCO que será aberta junto com suas ordens, mas atenção,
caso você já tenha ordens de saída implementadas em sua estratégia de negociação (ordens de
cobertura), estas não serão mais executadas já que as ordens OCO terão preferência.

Também é possível configurar nesta seção a zeragem automática por horário. A plataforma precisa
estar aberta para que a zeragem aconteça, assim como para que a automação funcione.

## Risco
Seguindo as configurações temos as configurações de risco da automação. Na seção Pausar e Zerar ao
Alcançar é possível configurar parâmetros que irão pausar e encerrar as posições abertas de acordo com um objetivo de ganho, ou um limite de perda. Caso você não deseje encerrar a posição quando
atingir um objetivo de ganho seleciona a opção “Não Zerar ao Atingir Objetivo de Ganho”.

Já a seção Pausar ao Alcançar possibilita que a automação seja pausada quando alcançados os
números de perdas consecutivas e máximo de operações configurados.

Aqui também disponibilizamos um atalho para que você possa configurar o risco global da carteira/conta
no gerenciador de risco da plataforma.

## Segurança
Por fim, na seção Segurança, temos algumas configurações para definir o comportamento da estratégia
em caso ocorra um erro de execução no código da mesma ou eventuais mudanças do mercado, como a
entrada do ativo em leilão.

Uma vez criada a automação, você pode visualizá-la na janela Automação de Estratégias:

## Acompanhamento
Para acompanhar a sua automação você pode visualizar um resumo rápido das principais informações
na lista de automações da janela Automação de Estratégias. Nela você pode visualizar o status, conta e
carteira em que a automação está vinculada, ativo, nome da estratégia, período gráfico e os resultados
relacionados à execução.

Você também pode visualizar nesta janela um resumo das estatísticas relacionadas a essa estratégia
que contém mais detalhes da estratégia:

Para ligar/pausar uma automação de maneira individual pode-se utilizar o painel, e clicar em executar:

Através do menu de contexto também é possível zerar a posição de uma estratégia pausada ou Pausar
+ Zerar Posição de uma estratégia em execução. Podemos também editar o código da automação no
Editor de Estratégias, Excluir a automação que irá excluir também a carteira atrelada a ela. Para realizar edições na sua automação, você pode, dentro do interface de controle, clicar com botão direito na estratégia desejada e ir em “Editar Automação” ou clicar diretamente na engrenagem. Lembrando que caso a sua automação esteja ligada, ao realizar alguma edição ela será pausada.

Para acompanhar os detalhes do que a execução está executando, vá em Detalhes. Nesta janela você
poderá acompanhar tanto as ordens e sinais que a estratégia está gerando, como também acompanhar
a performance e resultados da estratégia mais detalhadamente.

Na janela de Automações é possível utilizar os botões no canto superior direito da interface de controle para pausar todas as automações em execução ou para pausar e zerar todas as posições em aberto:

Caso você possua alguma automação ligada será possível identificar mesmo com a janela de
estratégias automatizadas fechadas, pois no menu superior da sua Plataforma será destacado em azul
o menu de Estratégias.

Neste menu você será informado quantas estratégias você possui em execução e permitirá que você
tome ações rápidas através do menu como pausar tudo ou pausar e zerar tudo.

## Regras de Execução

As automações de estratégias funcionam com as mesmas regras que são utilizadas no backtest das
estratégias de execução. Para entender melhor o que cada função faz relacionada à execução de
ordens, recomendamos primeiramente a leitura das funções de backtest. Aqui detalhamos as regras por
trás dos mecanismos de automação para facilitar o entendimento do usuário na hora de implementar
uma estratégia de execução já pensando na sua automação.

## Modo de Execução do Backtest: OHLC e Tick a Tick

O Profit Ultra permite escolher entre dois modos de execução para o backtest: OHLC ou Tick a Tick.
Abaixo, explicamos como cada um desses modos opera e suas características específicas.

O modo OHLC (Open, High, Low, Close) utiliza apenas os preços de abertura, máxima, mínima e
fechamento de cada candle para realizar os cálculos e simular o movimento das operações.

As saídas Limit e Stop utilizam os preços de máxima, mínima e fechamento para simular as execuções.

Como os movimentos dentro do candle não são considerados, as simulações são menos detalhadas em
relação ao fluxo real de preços intraday. Em casos de ordens de stop ou gain, o movimento do preço é
verificado com base nos níveis OHLC do candle.

O modo Tick a Tick utiliza exatamente o fluxo dos preços dentro de cada candle para simular as
operações. Isso garante maior precisão ao refletir como as ordens seriam executadas em tempo real.
Permitindo simulações de saídas Limit e Stop nos exatos pontos em que seriam executadas durante o
pregão.

Em simulações OHLC, o backtest pode concluir que um stop ou um gain não foi atingido ao avaliar
apenas os preços do OHLC, por achar que a ordem executou após a variação de preço. Já no modo
Tick a Tick, o mesmo stop pode ser executado corretamente ao analisar os preços intraday,
assegurando a aderência à lógica operacional real.

Por utilizar uma granularidade mais fina, o modo Tick a Tick tem menor disponibilidade de histórico
quando comparado ao OHLC. Isso pode afetar simulações de períodos longos. Essa limitação pode ser
encontrada ao executar uma estratégia no modo Tick a Tick.

Considere a imagem abaixo, que ilustra dois candles de alta, onde a linha verde representa o
movimento real dos preços dentro do candle e o ponto vermelho, a ponto onde uma ordem foi enviada.
No caso de um backtest enviando uma ordem alguns ticks acima da abertura, no modo OHLC, a ordem
só seria executada após o preço atingir a mínima (LOW) e, posteriormente, alcançar o fechamento
(CLOSE). Já no modo Tick a Tick, a ordem poderia ser executada assim que o preço atinge o nível
programado, mesmo antes do candle ser concluído, permitindo, por exemplo, que uma ordem de LOSS
seja disparada antes do fechamento do candle.

### Reprocessamento do candle em aumentos de posição
Caso houver execução de alguma ordem (aumento de posição), o código é reprocessado para a criação
de eventuais ordens de cobertura da operação (ordens ToCover). A reexecução da estratégia para
posicionamento de ordens de cobertura acontece quando ordens forem executadas, ou seja, podem
ocorrer no meio de um candle para não deixar o usuário exposto a riscos do mercado. Nesse
reprocessamento, por mais que o código faça a chamada de ordens que poderiam aumentar a
exposição, essas ordens não são enviadas.

Mais detalhes sobre ordens de cobertura podem ser vistos a seguir

### Ordens para aumento de posição (Buy e Sell)
É possível enviar ordens Buy e Sell tanto quando você estiver comprado ou vendido, porém quando
uma ordem Buy for enviada enquanto você estiver em uma posição vendida, ela será tratada como uma
ordem de cobertura automaticamente. O mesmo acontece para uma ordem Sell, quando você estiver
uma posição comprada, ela será tratada como uma ordem de cobertura. Caso contrário, elas apenas
aumentaram a sua posição até o limite definido na configuração da estratégia.

Ordens conflitantes são automaticamente gerenciadas pelo automatizador, ou seja, quando for enviada
uma ordem BuyToCover e você estiver em uma posição comprada ou zerada, ela será ignorada, da
mesma maneira se for enviada uma ordem SellToCover e você estiver em uma posição vendida ou
zerada, ela também será ignorada.

### Ordens de cobertura de posição (BuyToCover e SellToCover)
Ordens de cobertura, ou ordens ToCover. nunca irão inverter a sua posição; elas garantem que a ordem
contrária vai respeitar sempre a posição da operação. Recomendamos que o programador utilize
sempre ordens de saída de posição como ordens ToCover explicitamente no código para garantir que o
operacional que o usuário está programando está correto. Para isso, as ordens ToCover são sempre
enviadas como ordens OCO, logo você não precisa se preocupar em gerenciar e cancelar eventuais
ordens de cobertura que poderiam ficar abertas após a execução de apenas uma das pernas de saída.
Ordens de cobertura são enviadas ou atualizadas a toda mudança de candle, cabe ao usuário gerenciar
a quantidade de cada ordem caso você esteja posicionado em mais de um lote para cobrir corretamente
a exposição ao mercado. Na finalização do candle, caso o código indique um envio de um mesmo número de ordens de cobertura, será realizada uma edição da OCO para os novos valores de preço
correspondentes. Por outro lado, caso o envio aumente ou diminua o número de ordens para aquele
candle, a OCO aberta será cancelada, e será enviada uma nova OCO com as saídas definidas pelo
código.

### Ordens OCO
Caso o usuário configure uma ordem OCO pela configuração da automação, as ordens de cobertura
definidas pela estratégia serão desconsideradas, já que todas ordens já vão possuir essa cobertura
natural da ordem OCO.

### Indicadores que atualizam valores anteriores
Se forem utilizados indicadores que alterem seus valores em candles antigos (candles já finalizados), o
valor do indicador que será considerado será o do momento em que o candle finalizar, desse modo caso
não houver a entrada da execução na virada do candle, não será feito envio de ordens para aquele
candle no futuro, mesmo que algum indicador altere seu valor no passado e troque a decisão de envio
de ordem. Alguns exemplos de indicadores que podem causar esse comportamento são indicadores
que tem apenas um valor durante todo dia, por exemplo: **Preço Ask e Bid** e também indicadores que
decidem apenas depois de alguns candles, como por exemplo o **Detector de topos e fundos** ou a linha
Chikou Span (2) do indicador **IchimokuCloud**, entre outros.

## Abrir Estratégias
Na opção de "Abrir Estratégias", o usuário terá acesso a três abas, elas são:
-  Todas: O usuário poderá ver todas as estratégias dentro do sua plataforma;
-  Minhas Estratégias: O usuário irá filtrar para somente exibir todas as estratégias criadas por ele
dentro da plataforma;
-  Exemplos: O usuário irá filtrar para exibir exemplos de estratégias que já vem como padrão na
plataforma.

Além das abas, o usuário também poderá pré-visualizar o seu código de estratégia para confirmar
informações

## Gerenciador de Estratégias
A opção de gerenciador de estratégias, permite ao usuário escolher uma determinada
estratégia criada para edição, fazendo com que o Editor de estratégias carregue a estratégia
determinada, ao clicar em "Editar".

O usuário também poderá excluir as estratégias desejadas, selecionando as mesmas e
clicando no botão "Excluir", além da funcionalidade de renomear a estratégia através do
botão "Renomear".

## Exportar / Importar Estratégias
Nesta funcionalidade, permite ao usuário exportar as estratégias criadas por eles para que possam ser
importadas novamente.

O usuário também tem a possibilidade de querer exportar o código fonte da estratégia ou apenas o
arquivo executável.

Na importação, o usuário tem a funcionalidade de escolher quais estratégias serão carregadas e
adicionadas junto à sua plataforma Nelogica.

## Criar Regra de Coloração

A funcionalidade de criar regra de coloração, mostra de forma visual, como criar uma regra de
coloração com as condições desejadas.

A cada vez que for clicado no botão "+" irá criar uma condição para que se Condição 1 e Condição 2
sejam verdadeiras irá colorir de acordo com a cor desejada, na cor padrão será se caso as condições
não retornem verdadeiro irá pintar em determinada cor.

Caso o usuário deseje utilizar outras informações, ele irá poder clicar no botão "Mais" que se encontra ao lado da variável para selecionar outras condições.

## Criar Regra de Alarme
A funcionalidade do Criar Regra de Alarme mostra de forma visual, como criar uma regra de alarme de
acordo com as condições desejadas.

A cada vez que for clicado no botão "+", será criada uma condição para que se Condição 1 e Condição
2 sejam verdadeiras irá acionar o alarme desejado, e o pop-up de alarme será emitido de acordo com
a cor estabelecida.

Caso o usuário deseje utilizar outras informações, ele poderá clicar no botão "Mais" que se encontra
ao lado da variável para selecionar outras condições.

Após a criação da regra de alarme, a estratégia deverá ser ativada, através do menu "Ferramentas >
Gerenciador de Alarmes > Estratégias", selecione "Novo Alarme".

## Criar Regra de Execução
A funcionalidade do Criar Regra de Execução mostra de forma visual, como criar uma regra de
execução de acordo com as condições desejadas.

A cada vez que for clicado no botão "+" irá criar uma condição para que se Condição 1 e Condição 2
sejam verdadeiras irá acionar o alarme desejado e irá colorir o pop-up de alarme de acordo com a cor
estabelecida.

Caso o usuário deseje utilizar outras informações, ele poderá clicar no botão "Mais" que se encontra
ao lado da variável para selecionar outras condições.

## Screening
A funcionalidade de Screening mostra, de forma visual, os ativos que se encontram na base de dados
e que satisfazem as condições da estratégia.

No filtro, ao clicar no botão "+", será criada uma condição para que, se Condição 1 e Condição 2
sejam verdadeiras, irá mostrar o ativo dentro da aba selecionada.

Caso o usuário deseje utilizar outras informações, ele irá poder clicar no botão "Mais" que se encontra ao lado da variável para selecionar outras condições.

Ao clicar no botão "Aplicar" a estratégia criada é aplicada à lista e irá mostrar os ativos que satisfazem a condição.

## Inserir Regra de Coloração
A funcionalidade de inserir regra de coloração permite ao usuário colorir o gráfico de acordo como ele determinou os parâmetros nos gráficos dos ativos.

As regras de coloração serão feitas seguindo a ideologia de um indicador ou seja, respeitando o layout atual da janela.

## Condições de Coloração
As condições de coloração permitem ao usuário, quais valores ele irá utilizar no momento em que irá
criar uma nova regra de coloração, elas podem ser:
- Numérico: O usuário poderá utilizar números inteiros ou reais;
- Cotação: O usuário poderá utilizar os valores presente nas cotações, sendo elas: Abertura,
Máxima, Mínima, Fechamento, Quantidade;
- Indicador: O usuário poderá utilizar os valores presentes nos indicadores criados por ele, e
alterar os parâmetros presentes para de acordo com a vontade para coloração;
- Cotações Anteriores: Permite ao usuário utilizar os valores presentes nas cotações anteriores,
conforme mostra na guia Variáveis e séries de dados.

## Editor de Estratégias
A janela de Editor de estratégias é onde o usuário poderá criar suas próprias estratégias, juntamente
com a funcionalidade de visualizar diretamente no gráfico a estratégia criada.

O Editor de Estratégias possui três abas:
- Editor: Onde o usuário escreve a estratégia seguindo as instruções da linguagem NTSL.
- Gráfico: Onde o usuário visualiza a estratégia após executada diretamente no gráfico;
- Misto: É onde o usuário visualiza as informações da aba Editor e a aba Gráfico em uma só,
onde a cada vez que ele execute o código, já irá aparecer diretamente no gráfico.
- Estatísticas: Ao executar uma estratégia de execução pelo editor, o usuário poderá visualizar a
estatística do relatório de performance.

Dentro do Editor de estratégias o usuário irá possuir as seguintes opções:
- **Nova Estratégia**: Onde o usuário irá poder criar uma nova estratégia;
- **Abrir Estratégia**: Permite ao usuário abrir estratégias já criadas e edita-las
- **Fechar**: Fecha a aba da estratégia atual;
- **Salvar**: Salva a estratégia atual;
- **Salvar Como**: Salva a estratégia atual, podendo ser adicionado uma descrição da mesma;
- **Verificar Sintaxe**: Realiza a leitura do código verificando se há erros e a transforma em uma
estratégia executável;
- **Trace**: Mostra passo-a-passo o que o código da estratégia está realizando e mostrando os valores
naquele momento;
- **Trace Into**: Semelhante ao Trace, mostra passo a passo o que a estratégia está realizando no
momento de criação, porém, quando há funções no código ele irá abri a função para mostrar ao usuário
que a função está executando;
- **Executar**: Após apertar o botão "Compilar", o botão executar irá executar a estratégia criada e a
mostra no gráfico;
- **Parar**: Tem como funcionalidade parar a estratégia para que o usuário pare a execução da estratégia
criada;
- **Propriedades**: Tem como funcionalidade mostrar as propriedades que irão constituir a estratégia,
como desenho no gráfico, linhas guias e escala.

## Propriedades do Editor de Estratégias
Nas propriedades do Editor de estratégias, o usuário irá poder utilizar valores e informações adicionais no momento de criação da estratégia:

Parâmetros: Permite ao usuário utilizar estratégias já criadas como parâmetros para uma nova
estratégia junto com o valor desejado para a mesma;
- **Aparência**: Permite ao usuário determinar se deseja que a estratégia seja mostrada em linha ou
em histograma;
- **Linhas Guia**: Permite ao usuário criar linhas para se basear como exemplos de linha de suporte
e resistência.
- **Preenchimento**: Configuração para visualizar um preenchimento entre as linhas

## Nova Estratégia
Ao clicar no botão de Nova Estratégia, o usuário poderá escolher entre as opções abaixo:

Em branco (Texto): Ao escolher desta maneira, o usuário ira criar uma estratégia em branco;
- **Indicador**: Ao abrir a estratégia, irá carregar um exemplo de estratégia de indicador para o
usuário;
- **Coloração**: Ao abrir a estratégia, irá carregar um exemplo de regra de coloração para o usuário.
- **Execução**: Será criado um exemplo, com uma função para estratégia de execução.
- **Screening**: Será inserido um exemplo para a criação de um filtro para o Screening.
- **Alarme**: Será criado um exemplo, com a função Alert.