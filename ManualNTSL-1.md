## Introdução

A  NTSL  (Nelogica  Trading  System  Language)  é  uma  poderosa  linguagem  criada  com  um  único propósito:  permitir  o  desenvolvimento  dos  melhores  e  mais eficientes  sistemas  algorítmicos  de operação. A Nelogica oferece juntamente com a NTSL um ambiente de criação pioneiro e revolucionário chamado  AlgoTools.  Com  o  AlgoTools  é  possível  codificar,  testar  e  simular  com  grande  agilidade qualquer estratégia de operação. Na NTSL, o usuário encontra uma grande facilidade no momento de criação de suas estratégias, a possibilidade de criar toda ela em português, havendo assim, a facilidade e fácil entendimento da estratégia criada.

## Estrutura de uma Estratégia

Observe o trecho de código abaixo que representa o indicador média móvel. Esse código apresenta as três áreas que definem a estrutura de uma estratégia. São elas: área de declaração de parâmetros de entrada, área de declaração de variáveis e funções e área de código.





A área de parâmetros de entrada compreende toda a região entre a palavra reservada input (parâmetro) e a palavra reservada var. A área de variáveis e funções começa com a palavra var e estende-se até a palavra begin (inicio) . Finalmente, a região de código inicia-se com a palavra reservada begin (inicio) e finaliza na palavra end (fim) , conforme imagem abaixo:


## Área de declaração de parâmetros de entrada

Na área de declaração de parâmetros de entrada informamos todos os parâmetros externos que a estratégia usará. Esses parâmetros são fundamentais, pois:




- ● Definem a interface com o mundo externo, ou seja, é onde usuário poderá alterar e o que servirá como parâmetro de chamada caso a estratégia seja utilizada em outra interface/estratégia. x x
- ● Define os itens que serão analisados no processo de otimização.

Para definir um parâmetro: NOME\_DO\_PARÂMETRO (VALOR\_DE\_INICIALIZAÇÃO) Exemplo :

| Input          | Definicão   |
|----------------|-------------|
| Preco (Close); |             |
|                | Dcfine      |

## Área de declaração de variáveis e funções

Na área de declaração de variáveis informamos todas as variáveis que serão utilizadas na estratégia. Nesta região também descrevemos funções que desejamos usar no código. As funções devem ser sempre codificadas após a declaração das variáveis.

Para declarar uma variável: NOME\_DA\_VARIAVEL: TIPO Exemplo :

| Fariável         | Definição                                     |
|------------------|-----------------------------------------------|
| sResult : Float; |                                               |
| nIndex: Integer; | chamada nIndex para anazenar numeros inteiros |

## Área de código

Nesta parte descreve-se o código propriamente dito, ou seja, as regras que utilizam parâmetros, variáveis e outros dados para calcular sinais e indicadores.

## Fluxo de Execução de uma Estratégia

- O  código de uma  estratégia é executado de maneira sequencial. Porém, ele é executado sequencialmente candle por candle, como se houvesse um laço que percorre toda série de dados de um ativo.




Sendo  assim,  a  sequência  de  comandos existente na área de código será executada uma vez para cada candle existente. Para cada candle, será executado o código da estratégia em um loop implícito. A regra em pseudocódigo é, portanto:

- ● Tendo uma série de dados X de tamanho N;
- ● Para cada item X[i], com i variando de 0 até N-1, executa-se a área de código da estratégia;
- ● A cada novo dado do ativo, o código da estratégia continua sendo executado, avaliando o último e o penúltimo candle;

## Importante:

- ● O mesmo candle pode ser processado diversas vezes. Isso ocorre muito em tempo real, onde cada trade pode gerar uma notificação de reprocessamento do fluxo de execução.
- ● Quando uma ordem é executada, o fluxo de execução reprocessa o mesmo candle para ativar as ordens Covers.
- ● Dependendo da notificação dos candles, podem ser reprocessados candles passados. Isso deve ser levado em consideração pelo programador.
- ● Sempre que um candle passado é reprocessado, serão reprocessados todos candles até o atual.
- ● Em tempo real, quando o código está executando ao mesmo tempo que recebe novos dados do mercado, o código da estratégia é executado diversas vezes para o último e o penúltimo candle durante a execução, podendo também executar em candles passados.

Esses  processamentos  podem  alterar  valores  de  variáveis  globais  ou  de  série,  e  podem  causar mudanças na coloração para  candles passados ou  mudança  de  comportamento  quando o  código é pausado e executado novamente.

Quando estiver utilizando séries em sua estratégia, é importante lembrar que o primeiro tick do candle terá o valor [0] zerado. Como comentamos anteriormente, sua estratégia será executada não apenas no último candle e sim também ao passado, devido aos cálculos que precisam ser feitos para garantir que a  NTSL  funcione  corretamente.  É  importante  ressaltar  que  não  se  pode  assumir  que  um  candle  no passado não será avaliado, porém, se desejar, é possível inibir o recálculo de algum valor utilizando a função  LastBarOnChart()  em  uma  condição  no  início  do  código  para  evitar  isso.  É  fundamental compreender  que  o  [0]  sempre  está  se  referindo  ao  candle  que  está  sendo  avaliado,  e  não necessariamente  será do último candle.

Abaixo, um exemplo de como uma variável arbitrária 'nValor' funcionaria caso o último candle estivesse sendo avaliado. Caso eu quisesse acessar o valor dela há 2 candles passados, utilizaria 'nValor[2]'.





Porém, caso o código esteja sendo executado em um candle no passado, o nValor[0] seria referente ao candle atual do processamento, e não ao último candle como no exemplo passado. Os outros candles também seriam  acessados  com  base no  candle  que está  sendo  processado  no  momento,  como no exemplo abaixo.





## Variáveis, tipos de dados e constantes

As variáveis são utilizadas para armazenar dados, conforme seu tipo específico.

## Tipos de dados

Float ou Real Representa números de ponto flutuante.

Integer ou Inteiro Representa números inteiros.

Boolean ou Booleano Representação lógica: True ou Verdadeiro e False ou Falso

Serie Representa uma série de dados.

A  NTSL  suporta  a  conversão  implícita  de  valores  Float  a  Inteiros,  isto  é,  atribuir  um  valor  Float diretamente a um valor Integer. O valor inteiro será o valor do ponto flutuante, descartandoas casas decimais. Por exemplo, se eu atribuir 2.99'ou 2.35 a um inteiro, o valor do inteiro será 2. Para outros comportamentos de arredondamento, a linguagem disponibiliza as funções Ceiling, Floor e Round. Para mais detalhes sobre essas funções, consulte esse mesmo manual na seção de funções.

As variáveis na linguagem oferecem uma flexibilidade muito maior do que na maioria dos sistemas de programação conhecidos.




Todas as variáveis são globais, e deve ser dada uma atenção especial quando utilizadas. Ao programar usando variáveis globais,  deve  ser  levado  em  consideração  o  comportamento  do processamento  do fluxo de execução, a cada vez que o fluxo de execução é realizado as variáveis podem ter seu valor alterado com base no último valor que tinham.

Quando uma variável for acessada utilizando colchetes (exemplo: [x]), ela será considerada uma série de dados pelo compilador. Seu comportamento é diferente: séries iniciam cada candle com seu valor zerado. Também é possível navegar entre valores atuais e passados, mediante indexação.

## Séries de dados

As séries de dados são utilizadas para obter dados específicos de cada Candle.

## Séries:

Open ou Abertura - Retorna o valor de abertura de cada candle.

Close ou Fechamento - Retorna o dado de fechamento.

Low ou Minima - Retorna o valor de mínima

High ou Maxima - Retorna o dado de máxima.

Quantity ou Quantidade - Retorna o valor de contratos negociados de cada candle

Volume - Retorna o dado de volume financeiro de cada candle

## Arrays

Análogo  ao  tipo  Serie,  a  estrutura  de  um  Array  permite  o  armazenamento  de  dados  de  um  tipo específico, contudo, após sua criação, seu comprimento será fixo, o que permite uma alocação menor de memória.

O acesso aos elementos de um Array é efetuado mediante indexação.

## Estrutura da declaração:


A fim de exemplificação, segue um exemplo de declaração de um Array  estático de 10 elementos, o qual é preenchido com valores de 1 a 10 (primeira estrutura de repetição), e efetuado o somatório dos valores:






## Correlação de múltiplos ativos

É possível ainda acessar os dados, ao utilizar o recurso Asset , onde é necessário parametrizar o ativo específico, e a bolsa a qual pertence. As bolsas visualizadas na plataforma dependem se o usuário possui acesso a elas. Na documentação na plataforma está disponível, na aba constantes, apenas os feeds que o usuário terá acesso.

## Bolsas que podem ser parametrizadas:

feedBMF

feedBMFSynthetic feedBovespa

feedCME

feedDowJones feedEconomic

feedNasdaq feedNyse

feedActivTrades

## Estrutura da declaração:


A seguir, um exemplo de declaração, e acesso aos dados de fechamento e abertura:

const

WDOFUT = Asset("WDOFUT", feedBMF);





Além do acesso às séries de dados, pode-se retornar o ticker (String) e bolsa (String) do Asset declarado, a partir das funções GetAsset e GetFeed:


É  possível  inclusive  declarar  N  ativos,  a  fim  de  correlacionar  os  dados  para  implementação  da estratégia.

A seguir, um exemplo de coloração, onde será aplicada a cor verde, caso o fechamento do WDO estiver acima de sua média (20 períodos), e o ativo WIN, fechando abaixo de sua média (20 períodos).

A coloração vermelha será aplicada, caso o fechamento do WDO estiver abaixo da média, e o último preço do WIN acima de sua média.

A coloração cinza será identificada, caso não sejam satisfeitas as condições.






Atenção: Ao utilizar gráficos atemporais em conjunto com múltiplos ativos, as avaliações de fechamento de candle serão feitas sempre em função do fechamento de candle do ativo principal. Nesse momento, os ativos auxiliares não necessariamente terão seus fechamentos no mesmo momento, já que esses gráficos são atemporais, e não respeitam o mesmo critério de fechamento: tempo.

Por conta disso, é esperado que o backtest ou o replay tenham resultados diferentes da automação (que acontece nos ativos em tempo real), isso porque, em tempo real, não se está levando em conta o mesmo candle fechado para a análise dos dados e, em backtest ou replay, o backtest pode estar olhando para candles que já estão completos, ou seja, fecharam após o fechamento do candle do ativo principal. Isso se deve ao fato que no backtest, só avaliamos candles já fechados e não há conhecimento do tick-a-tick dentro do candle. Deste modo, depois do candle do ativo principal ter fechado, os candles de outros ativos ainda estavam em formação.

## Acessando dados anteriores

- O  dado  atual  de uma variável pode ser descrito por Variavel[0]. O número entre colchetes indica o dado de quantos períodos anteriores deseja-se acessar (sendo 0, portanto, da barra corrente). Para ilustrar melhor, vamos a um exemplo:

sResult := Preco[1];

A linha de código acima está atribuindo o valor da variável Preco[1] para a variável sResult. Imagine que Preço corresponde a todos os valores de fechamento da série de dados de um certo ativo, como na tabela abaixo:

|            | Posição   | Falor   |
|------------|-----------|---------|
| 05/10/2010 | Preco[0]  | 12,43   |

Portanto, Preco[1] refere-se ao valor de ontem do preço de fechamento (sResult vale então 12,40 em nosso exemplo). Dessa forma, o número inteiro que especificarmos entre colchetes indica ao sistema quantos períodos no passado deve-se acessar a informação.




## Constantes

São utilizadas para a inserção de parâmetros de determinadas funções, estes valores não podem ser alterados pelo usuário.

## Lado da Ordem:

osBuy ou osCompra: Ordem de compra. osSell ou osVenda: Ordem de venda.

## Opções:

optCall - Opção de compra.

optPut - Opção de venda.

## Tipo de Ordem:

otLimit - Tipo limite. otMarket - A mercado. otStopLimit - Tipo stop.

## Cores:

clAqua ou clAzulClaro - Cor azul-claro clBlack ou clPreto - Cor preta clBlue ou clAzul - Cor azul clCream ou clCreme - Cor creme clDkGray ou clCinzaEscuro - Cor cinza-escuro clFuchsia ou clFucsia - Cor fúcsia clGray ou clCinza - Cor cinza clGreen ou clVerde - Cor verde clLime ou clVerdeLimao - Cor verde-limão clLtGray ou clCinzaClaro - Cor cinza-claro clMaroon ou clMarrom - Cor marrom clMedGray ou clCinzaMedio - Cor Cinza médio clMoneyGreen ou clVerdeClaro - Cor verde-claro clNavy ou clAzulMarinho - Cor azul-marinho clOlive ou clVerdeOliva - Cor verde-oliva clPurple ou clPurpura - Cor púrpura clRed ou clVermelho - Cor vermelha clSilver ou clPrata - Cor prata clSkyBlue ou clAzulClaro - Cor azul-claro clTeal - Cor Verde-azulado clWhite ou clBranco - Cor branca clYellow ou clAmarelo - Cor amarela




## Controle de Fluxo

As instruções de fluxo são utilizadas para administrar a sequência de execução das instruções dentro de um programa. A NTSL apresenta três tipos desse tipo:

## If then else

Se (condição) for verdadeiro executa-se a listagem (comandos 1), caso (condição) seja falso executa-se (comandos 2). Tanto (comandos 1) quanto (comandos 2) podem ser sequências de instruções.

A expressão (condição) pode ser qualquer tipo de teste que resulte em verdadeiro ou falso, alguns exemplos:


A seguir um exemplo de coloração de candles de acordo com a condição presente no If then else .


Se o valor de fechamento da barra atual (Close equivale a Close[0]) for igual ao fechamento da barra anterior  (Representado  por  Close[1])  executa-se  o  código  que  segue  a  palavra  reservada THEN (ENTÃO) .  Caso contrário, o sistema executa o código subsequente até chegar na palavra reservada ELSE (SENÃO) .




## For (To / DownTo) Do

- O  comando FOR é  utilizado  para  definir um  loop  controlado,  ou  seja,  o  bloco  é  executado repetidamente até que a variável de contagem saia do valor inicial e atinja o valor final.

Para  a  variável  controladora,  pode-se  incremetá-la,  a  partir  do  comando To, ou  decrementá-la,  ao utilizar na estrutura o DownTo .

## Exemplo (For To Do):

Observe  o  código  da  média  móvel,  a  variável  de  contagem  nIndex  começa  com  o  valor  0  e  deve chegar ao valor de Periodo - 1. No exemplo, Periodo foi definido como parâmetro de entrada, para definir o tamanho da média.

Assim, caso seja parametrizado o valor 0 (Periodo), o comando FOR criará um loop de 9 iterações (de 0 até 8) para cada barra, calculando assim o valor médio para a posição atual.


Exemplo (For To Do x For DownTo Do):

A fim didático, segue um exemplo de cálculo de fatorial, utilizando as duas estruturas.

## For To Do:






## For DownTo Do:


## While

A  execução  da  estratégia  ao  chegar  no  comando  WHILE  testa  o  resultado  de  (condição).  Caso (condição) seja verdadeiro (true) a listagem (comandos) é executada. Após a execução a (condição) volta a ser testada, assim, o loop apenas irá se encerrar quando (condição) deixar de ser verdadeira.

## Exemplo:

No código a seguir, reescrevemos o indicador média móvel utilizando a instrução WHILE (ENQUANTO) ao invés de FOR (PARA) .






## Repeat

Este comando difere-se do For e While, no sentido de que a condição será testada no final da estrutura, e não no início, portanto, as instruções do bloco serão executadas pelo menos uma vez.

## Exemplo:

A fim de comparação com as outras estruturas já abordadas, segue o exemplo de cálculo de fatorial:





## Operadores

Os operadores constituem os símbolos matemáticos e lógicos usados em cálculos e comparações.

## Operadores matemáticos

Os operadores matemáticos são:

| Descrição   | Exemplo   | Resultado   |
|-------------|-----------|-------------|
| Adição      |           | 9           |
|             |           | 20          |
| Divisão     | 5 4       |             |

O operador de divisão possui a maior força de precedência, seguido por multiplicação. Assim, como consta na imagem abaixo:

|                | Resultado   |
|----------------|-------------|
| 10*10/5+2      | 22          |
| 10*10+2        | 102         |
| 50+100*10/22-1 |             |

## Operadores lógicos

Os Operadores lógicos são utilizados principalmente para comparações.

## "E" lógico

Representado pela palavra reservada and (e) , retornará TRUE somente quando as duas condições de teste forem verdadeiras conforme Tabela Verdade abaixo:




| Condição   | AND   | Condição 2   | Resultado   |
|------------|-------|--------------|-------------|
| FALSE      | AND   | FALSE        |             |
| FALSE      |       |              |             |
|            | AND   | FALSE        | FALSE       |
| TRUE       | AND   | TRUE         |             |

## "OU" lógico

Representado pela palavra reservada or (ou) , retornará TRUE (verdadeiro) sempre que pelo menos uma das condições de teste for verdadeira, conforme Tabela Verdade abaixo:

|       | OR   | Condição 2   | Resultado   |
|-------|------|--------------|-------------|
| FALSE | OR   | FALSE        | FALSE       |
|       | OR   |              |             |
|       |      | FALSE        | IRUE        |
| TRUE  | OR   | TRUE         | TRUF        |

## Funções

Conforme visto, funções são declaradas e descritas na área de declaração de variáveis e funções, abaixo um exemplo de funções:









Observe  que  primeiro  são  declaradas  as  seis  variáveis  usadas  na  área  principal.  É  sempre interessante manter o código o mais claro e organizado possível e as funções desempenham um papel fundamental nessa tarefa.

## Criando Funções (Sintaxe)

Function (funcao) Nome da Função ((parâmetro 1 : TIPO); (parâmetro 2: TIPO:);(parâmetro n: TIPO)): Tipo de Retorno

Begin(inicio)

Comandos

End (fim);


## Funções de biblioteca

Além do usuário poder criar seus próprios indicadores, é possível utilizar a biblioteca do sistema, ou seja, o usuário pode utilizar estratégias já criadas em novas.

Dentro  das  funcionalidades  de  bibliotecas,  o  usuário  poderá  colorir  os  gráficos  de  acordo  com  as condições determinadas pelo seu indicador.

## Funções Matemáticas

As funções matemáticas têm como finalidade implementar as seguintes funcionalidades:

- ● Power(valor,potência):  Tem como funcionalidade, gerar valores elevados em determinada potência;
- ● Round(valor): Tem como funcionalidade, arredondamento de números quebrados, caso o valor após a vírgula seja menor do que cinco, arredonda para baixo, caso contrário, arredonda para cima;
- ● Sqrt(valor): Tem como funcionalidade mostrar a raiz quadrada de valores desejados pelo usuário;

## Funções Gráficas

Como visto anteriormente, a função Plot realiza a  ligação  dos  valores  gerados  na  estratégia  e  cria gráficos de linhas, mas caso haja a necessidade, o usuário também poderá colorir o gráfico de acordo com o desejado.

Esta  funcionalidade  denominada PaintBar(cor) permite  ao  usuário,  colorir  o  gráfico  com  cores  em determinadas situações do indicador, como na imagem abaixo(as cores podem ser determinadas por Strings , ou a partir da função RGB):









## Back-Testing

A funcionalidade de Back-testing permite ao usuário avaliar uma determinada estratégia, teoria ou modelo através de uma análise de dados históricos.

Lista de funcionalidades utilizadas para Back-Testing:

- ● Lista de funções;
- ● Criar regra de execução;
- ● Execução da estratégia.

Após criada a estratégia de Back-Testing, para ser adicionado diretamente no gráfico, clique no botão direito sobre o mouse e selecione a opção "Inserir Regra de Execução".

O código de back-testing simula o mesmo comportamento da automação, as simulações de execução de ordens são processadas todas ao final do fluxo de execução do candle. Quando ocorre aumento de posição ao final do fluxo de execução, o código é reprocessado para ativar as  ordens de cobertura da operação  (ordens  ToCover).  O  usuário  pode  observar  esse  comportamento  quando  utilizar  o  modo debug.

## Automação de Estratégias

O  módulo  de  Automação  de  Estratégias  tem  o  objetivo  de  automatizar  as  estratégias  de  execução criadas  no  Editor  de  Estratégias.  Ele  está  disponível  nas  versões  mais  avançadas  das  plataformas Nelogica, em modo simulação de forma gratuita e disponível para contas reais por meio de módulos opcionais.

O novo módulo de automação espelha o funcionamento do backtest das estratégias para execução de ordens reais e em simulador. Para fazer o gerenciamento dessas automações pode-se acessar o menu Estratégias &gt; Automação de Estratégias.

A  janela  de  Automações  de  Estratégias  permite  que  possamos  criar  e  gerenciar  automações, acompanhar  o  resultado de todas as automações  de  maneira  simplificada. Caso  queira um detalhamento maior da automação pode-se clicar com o botão direito e ir em Detalhes. Nos detalhes é possível  acompanhar todos os eventos que a execução gerou, assim como diversos indicadores de performance da automação.



Os  próximos  capítulos  detalham  desde  a  criação  de  uma  estratégia  de  execução  utilizando  o  novo módulo de Automação de Estratégias, como o usuário pode acompanhar essas automações, e por fim detalha regras gerais da execução das estratégias.

## Criando uma estratégia de execução

Para criar uma automação você precisará criar uma estratégia de execução, que pode ser criada a partir do Editor de Estratégias. Se você já sabe o que é isso, pode seguir para o próximo passo.

Ao  abrir  o  Editor  de  Estratégias,  você  pode  criar  sua  estratégia  de  execução  utilizando  funções  de backtest (essas funções irão caracterizar a estratégia como sendo uma estratégia de execução e isso possibilitará a sua seleção no próximo passo para que a estratégia seja automatizada). Para criar uma estratégia  de  execução  você  deve usar  funções  do  módulo backtest,  que  pode  ser  visto na imagem abaixo:





Sugerimos que você utilize a função Nova estratégia, e selecione exemplos de estratégias de execução se você não estiver familiarizado com programação ou com o Editor de Estratégias






Abaixo é apresentado um exemplo de estratégia, utilizando o indicador IFR/RS, que pode ser utilizado no módulo de estratégias automatizadas:






## Criando uma automação

Para criar uma nova automação basta abrir a interface de controle e localizar o botão 'Nova Automação' localizada no menu superior da janela (indicado pelo número 1 na imagem), este botão estará sempre disponível para e visível na janela. No entanto, caso ainda não possua nenhuma automação criada, o mesmo botão 'Nova Automação' será apresentado em destaque no centro da tela.





Após  clicar  nesse  botão  será  aberta  a  janela  de  criação  da  da  estratégia  automatizada  onde  será configurada  os  parâmetros  da  automação  em  duas  etapas.  A  primeira  etapa  contém  configurações essenciais e obrigatórias para a criação da automação.

Na primeira etapa, nas configurações obrigatórias,  é possível definir a conta, a estratégia de execução, ativo alvo, quantidade por ordem, quantidade máxima da posição e o período que a estratégia usará como base para as análises.

A  Estratégia  de  execução  é  o  'cérebro'  da  automação.  Aqui  será  selecionado  aquela  estratégia implementada no editor. Ao clicar no botão 'Selecionar Estratégia' estarão listadas todas as estratégias de execução presentes na plataforma.  Além disso, caso a estratégia selecionada possua parâmetros de entrada, os mesmos serão listados nessa janela  para que possam ser editados da melhor maneira para a estratégia específica.


A próxima etapa contém configurações opcionais que podem ser exploradas nos menus acima quando as  Configurações  Avançadas  estiverem  ativas  (canto  inferior  esquerdo).  Aqui  podemos  configurar opções de Entrada e Saída, Risco e Segurança. Essas opções estão detalhadas a seguir:


## Opções de entrada

Nesta  seção  é  possível  especificar  parâmetros  que  alterem  a  estratégia  de  abertura  de  ordens  da automatização.

Em ordem de entrada você pode especificar qual vai ser o tipo de abertura de posição, ou seja, se a estratégia irá abrir novas posições apenas de compra, ou apenas de venda ou ambos os lados.

Em  horário  de  entrada  é  possível  especificar  o  período  de  tempo  em  que  a  estratégia  se  manterá habilitada. Após o horário final a estratégia é pausada. Ao desabilitar esta configuração, a estratégia permanecerá executando até o usuário pausá-la ou que o software seja encerrado.

É possível também escolher se você deseja confirmar cada ordem de aumento de posição. Neste caso, a confirmação de ordens será mostrada para cada nova ordem da estratégia.


## Modo de Execução

Há dois modos de execução: Realizar envio de ordens no fechamento do candle e Realizar envio de ordens quando a condição for satisfeita, também chamado de modo Tick a Tick. A mudança de uma opção  para  a  outra  causa  grande  impacto  na  maneira  como  o  código  da  estratégia  é  interpretado. Abaixo, é detalhado como cada modo se comporta.





## Ordens no Fechamento do Candle

Esta é a configuração padrão do modo de execução da automação e é a que traz maior semelhança com as operações realizadas por meio do backtest no Editor de Estratégias. Para ativar este modo selecione a opção 'Realizar envio de ordens no fechamento do candle'.

A cada fechamento de candle, o código para envio de ordens é reavaliado e se torna disponível para o envio de novas ordens de entrada, ou a alteração de ordens de entrada abertas ou de ordens Cover, caso haja posição. Deste modo, a escolha de tempo gráfico é crucial para sua automação.

Ordens que aumentem a exposição para o mercado e foram enviadas ao final de um candle e que não forem executadas até o final do candle seguinte serão canceladas ou editadas quando o próximo candle finalizar, de acordo com a estratégia do usuário. Uma vez que, apenas sabemos que um candle foi finalizado quando o próximo iniciar em gráficos atemporais, poderá ocorrer a execução de ordens em um candle subsequente caso o cancelamento chegue na bolsa após a execução da mesma.

É importante ressaltar que a automação poderá apresentar divergências em relação ao backtest ao ser comparado com a execução da automação em uma conta de simulação (ordens simuladas) ou conta




real (ordens reais), operando ao vivo no mercado real. Isso se deve a diversos fatores, como: Spread, Margem, RLP, Delays na Bolsa, Alta volatilidade de preço de alguns ativos, entre outros.

Essas diferenças acontecem primordialmente em séries de dados atemporais, as quais podem causar a criação de muitos candles em pouco tempo. No backtest, por termos zero delay, as ordens são criadas sempre no candle subsequente, porém no mercado real, onde há delay, por menor que ele seja, ordens podem ser executadas em candles subsequentes já que não houve tempo na criação do cancelamento dessas ordens.

Além disso, há uma segunda opção caso esse modo seja selecionado. Ativando essa função, você terá uma execução mais próxima ao backtest, já que o código executará apenas no fechamento do candle ou com uma atualização de posição. Com a opção desativada, o código é executado diversas vezes no mesmo candle.

## Ordens ao Satisfazer Condição

Este é o modo avançado de envio de ordens automatizadas, ele não é compatível com o backtest da aplicação, já que realiza operações a qualquer momento durante a formação dos candles, e fazendo com que o backtest não consiga simular esse modo de execução. Para ativar este modo selecione a opção 'Realizar envio de ordens quando a condição for satisfeita'.

Neste  modo,  o  código  é  constantemente  avaliado  durante  a  execução  da  automação  e  as  ordens podem  ser  enviadas  a  qualquer  momento  durante  o  candle,  uma  vez  que  seu  código  satisfaça  a condição  de  envio.  Como  pode  ser  visto  na  imagem  acima,  existem  duas  opções  que  podem  ser escolhidas para este modo. Detalhamos abaixo cada uma delas.

A  primeira  opção,  ' Esperar  o  fechamento  do  candle  para  primeira  execução '  faz  com  que  a automação aguarde o candle atual que está aberto para começar a executar ordens. Ou seja, apenas quando um novo candle for criado que ordens serão enviadas.

A segunda opção, ' Permitir múltiplos envios e alterações de ordens para a mesma barra ' quando selecionada, faz com que a automação envie e modifique ordens de entrada e saída a medida que o código satisfazer as condições de envio, mantendo um tempo mínimo entre alterações para proteção de flood  de ordens.  Caso  esta  opção  não  for  selecionada,  a automação  irá  limitar  o  envio  de ordens  e modificações para apenas 1 vez por barra, quando a condição no seu código for satisfeita.

A estratégia de atualização das ordens, quando a opção de múltiplos envios de ordens para a mesma barra estiver selecionada, seguirá uma equação linear que dependerá de quão perto as ordens sendo enviadas ou modificadas estão do preço atual, ou seja, caso as ordens estiverem muito longes do preço atual,  suas  ordens  serão  atualizadas  menos  frequentemente,  e  caso  suas  ordens  estiverem  muito próximas do preço atual, as ordens serão atualizadas mais frequentemente. Lembrando, todas ordens serão atualizadas ao mesmo tempo, o que vai importar é sempre a ordem mais próxima do preço para a decisão da frequência de atualização. As ordens tem um limite mínimo de atualização de 10 segundos, deste modo elas serão enviadas/alteradas de no máximo de 10 em 10 segundos.

O temporizador de envio de ordens só atualiza quando alguma modificação de ordem é enviada, ou seja, se o código executado enviar alguma ordem diferente das que já estão apregoadas, ele irá avaliar quando foi a última modificação feita e quando deverá fazer a próxima modificação e então liberar novos envios e modificações de ordens.




{ deprecated } A configuração antiga de número de ordens por candle não existe mais, vimos que ela mais atrapalhava o usuário do que ajudava, e escolhemos seguir em uma estratégia mais segura e inteligente.

Caso você havia configurado mais de uma ordem por candle para sua automação, a sua configuração irá automaticamente para 'Permitir múltiplos envios e alterações de ordens para a mesma barra', caso estivesse configurado para apenas uma, essa opção virá desselecionada.

Da mesma forma que o modo de atualização no fechamento do candle, as ordens de saída sempre serão  atualizadas  quando  houver  um  aumento  de  posição  para  rebalanceamento  das  ordens  de cobertura.

O modo de execução Tick a Tick é recomendado para que as estratégias se beneficiem do tempo real, já que o candle que será constantemente avaliado é o último candle da série que ainda está aberto. Este  modo  permite  que  a  entrada  seja  executada  imediatamente  na  condição  especificada,  por exemplo, um cruzamento de médias, ou quando o preço romper um determinado patamar estabelecido.

Relembrando, esse modo não é compatível com o backtest de estratégias de execução, pois depende dos  dados  em  tempo  real,  não  sendo  possível  realizar  uma  previsão  de  como  a  automação  irá  se comportar. Para testes de performance de sua estratégia tick-a-tick é necessário o uso do replay, ou o teste no pregão real, utilizando sua conta de simulação.

## Opções de saída

Nesta outra etapa da configuração, é possível alterar configurações de saída de sua automação. Aqui é possível configurar uma estratégia OCO que será aberta junto com suas ordens, mas atenção, caso  você  já  tenha  ordens  de  saída  implementadas  em  sua  estratégia  de  negociação  (ordens  de cobertura), estas não serão mais executadas já que as ordens OCO terão preferência. Também é possível  configurar nesta  seção  a  zeragem automática  por  horário.  A  plataforma  precisa estar aberta para que a zeragem aconteça, assim como para que a automação funcione.


## Risco

Seguindo as configurações temos as configurações de risco da automação. Na seção Pausar e Zerar ao Alcançar é possível configurar parâmetros que irão pausar e encerrar as posições abertas de acordo




com um objetivo de ganho, ou um limite de perda. Caso você não deseje encerrar a posição quando atingir um objetivo de ganho seleciona a opção 'Não Zerar ao Atingir Objetivo de Ganho'.

Já  a  seção  Pausar  ao  Alcançar  possibilita  que  a  automação  seja  pausada  quando  alcançados  os números de perdas consecutivas e máximo de operações configurados.

Aqui também disponibilizamos um atalho para que você possa configurar o risco global da carteira/conta no gerenciador de risco da plataforma.


## Segurança

Por fim, na seção Segurança, temos algumas configurações para definir o comportamento da estratégia em caso ocorra um erro de execução no código da mesma ou eventuais mudanças do mercado, como a entrada do ativo em leilão.





Uma vez criada a automação, você pode visualizá-la na janela Automação de Estratégias:



## Acompanhamento

Para acompanhar a sua automação você pode visualizar um resumo rápido das principais informações na lista de automações da janela Automação de Estratégias. Nela você pode visualizar o status, conta e carteira em que a automação está vinculada, ativo, nome da estratégia, período gráfico e os resultados relacionados à execução.

Você também pode visualizar nesta janela um resumo das estatísticas relacionadas a essa estratégia que contém mais detalhes da estratégia:


Para ligar/pausar uma automação de maneira individual pode-se utilizar o painel, e clicar em executar:


Através do menu de contexto também é possível zerar a posição de uma estratégia pausada ou Pausar + Zerar Posição de uma estratégia em execução. Podemos também editar o código da automação no Editor de Estratégias, Excluir a automação que irá excluir também a carteira atrelada a ela. Para realizar edições na  sua  automação,  você  pode,  dentro  do  interface  de  controle,  clicar  com  botão direito na




estratégia desejada e ir em 'Editar Automação' ou clicar diretamente na engrenagem. Lembrando que caso a sua automação esteja ligada, ao realizar alguma edição ela será pausada.


Para acompanhar os detalhes do que a execução está executando, vá em Detalhes. Nesta janela você poderá acompanhar tanto as ordens e sinais que a estratégia está gerando, como também acompanhar a performance e resultados da estratégia mais detalhadamente.





Na janela de Automações é possível utilizar os botões no canto superior direito da interface de controle para pausar todas as automações em execução ou para pausar e zerar todas as posições em aberto:





Caso você possua alguma automação ligada será possível identificar mesmo com a janela de estratégias automatizadas fechadas, pois no menu superior da sua Plataforma será destacado em azul o menu de Estratégias.


Neste menu você será informado quantas estratégias você possui em execução e permitirá que você tome ações rápidas através do menu como pausar tudo ou pausar e zerar tudo.

## Regras de Execução

As automações de estratégias funcionam com as mesmas regras que são utilizadas no backtest das estratégias  de  execução.  Para  entender  melhor  o  que  cada  função  faz  relacionada  à  execução  de ordens, recomendamos primeiramente a leitura das funções de backtest. Aqui detalhamos as regras por trás dos mecanismos de automação para facilitar o entendimento do usuário na hora de implementar uma estratégia de execução já pensando na sua automação.




## Modo de Execução do Backtest: OHLC e Tick a Tick

O Profit Ultra permite escolher entre dois modos de execução para o backtest: OHLC ou Tick a Tick. Abaixo, explicamos como cada um desses modos opera e suas características específicas.

O modo OHLC (Open, High, Low, Close) utiliza apenas os preços de abertura, máxima, mínima e fechamento de cada candle para realizar os cálculos e simular o movimento das operações. As saídas Limit e Stop utilizam os preços de máxima, mínima e fechamento para simular as execuções.

Como os movimentos dentro do candle não são considerados, as simulações são menos detalhadas em relação ao fluxo real de preços intraday.  Em casos de ordens de stop ou gain, o movimento do preço é verificado com base nos níveis OHLC do candle.

O modo Tick a Tick utiliza exatamente o fluxo dos preços dentro de cada candle para simular as operações. Isso garante maior precisão ao refletir como as ordens seriam executadas em tempo real. Permitindo simulações de saídas Limit e Stop nos exatos pontos em que seriam executadas durante o pregão.

Em simulações OHLC, o backtest pode concluir que um stop ou um gain não foi atingido ao avaliar apenas os preços do OHLC, por achar que a ordem executou após a variação de preço. Já no modo Tick a Tick, o mesmo stop pode ser executado corretamente ao analisar os preços intraday, assegurando a aderência à lógica operacional real.

Por utilizar uma granularidade mais fina, o modo Tick a Tick tem menor disponibilidade de histórico quando comparado ao OHLC. Isso pode afetar simulações de períodos longos. Essa limitação pode ser encontrada ao executar uma estratégia no modo Tick a Tick.

Considere a imagem abaixo, que ilustra dois candles de alta, onde a linha verde representa o movimento real dos preços dentro do candle e o ponto vermelho, a ponto onde uma ordem foi enviada. No caso de um backtest enviando uma ordem alguns ticks acima da abertura, no modo OHLC, a ordem só seria executada após o preço atingir a mínima (LOW) e, posteriormente, alcançar o fechamento (CLOSE). Já no modo Tick a Tick, a ordem poderia ser executada assim que o preço atinge o nível programado, mesmo antes do candle ser concluído, permitindo, por exemplo, que uma ordem de LOSS seja disparada antes do fechamento do candle.





## Reprocessamento do candle em aumentos de posição

Caso houver execução de alguma ordem (aumento de posição), o código é reprocessado para a criação de  eventuais  ordens  de  cobertura  da  operação  (ordens  ToCover).  A  reexecução  da  estratégia  para posicionamento de ordens de cobertura acontece quando ordens forem executadas, ou seja, podem ocorrer  no  meio  de  um  candle  para  não  deixar  o  usuário  exposto  a  riscos  do  mercado.  Nesse reprocessamento,  por  mais  que  o  código  faça  a  chamada  de  ordens  que  poderiam  aumentar  a exposição, essas ordens não são enviadas.

Mais detalhes sobre ordens de cobertura podem ser vistos a seguir.

## Ordens para aumento de posição (Buy e Sell)

É possível enviar ordens Buy e Sell tanto quando você estiver comprado ou vendido, porém quando uma ordem Buy for enviada enquanto você estiver em uma posição vendida, ela será tratada como uma ordem de cobertura automaticamente. O mesmo acontece para uma ordem Sell, quando você estiver uma posição comprada, ela será tratada como uma ordem de cobertura. Caso contrário, elas apenas aumentaram a sua posição até o limite definido na configuração da estratégia.

Ordens conflitantes são automaticamente gerenciadas pelo automatizador, ou seja, quando for enviada uma ordem BuyToCover e você estiver em uma posição comprada ou zerada, ela será ignorada, da mesma maneira se for enviada uma ordem SellToCover e você estiver em uma posição vendida ou zerada, ela também será ignorada.

## Ordens de cobertura de posição (BuyToCover e SellToCover)

Ordens de cobertura, ou ordens ToCover. nunca irão inverter a sua posição; elas garantem que a ordem contrária  vai  respeitar  sempre  a  posição  da  operação.  Recomendamos  que  o  programador  utilize sempre ordens de saída de posição como ordens ToCover explicitamente no código para garantir que o operacional que o usuário está programando está correto. Para isso, as ordens ToCover são sempre enviadas como ordens OCO, logo você não precisa se preocupar em gerenciar e cancelar eventuais ordens de cobertura que poderiam ficar abertas após a execução de apenas uma das pernas de saída. Ordens de cobertura são enviadas ou atualizadas a toda mudança de candle, cabe ao usuário gerenciar a quantidade de cada ordem caso você esteja posicionado em mais de um lote para cobrir corretamente a  exposição  ao  mercado.  Na  finalização  do  candle,  caso  o  código indique um envio de um mesmo




número de ordens de cobertura, será realizada uma edição da OCO para os novos valores de preço correspondentes. Por outro lado, caso o envio aumente ou diminua o número de ordens para aquele candle, a OCO aberta será cancelada, e será enviada uma nova OCO com as saídas definidas pelo código.

## Ordens OCO

Caso o usuário configure uma ordem OCO pela configuração da automação, as ordens de cobertura definidas  pela  estratégia  serão  desconsideradas,  já  que  todas  ordens  já  vão  possuir  essa  cobertura natural da ordem OCO.




## Indicadores que atualizam valores anteriores

Se forem utilizados indicadores que alterem seus valores em candles antigos (candles já finalizados), o valor do indicador que será considerado será o do momento em que o candle finalizar, desse modo caso não houver a entrada da execução na virada do candle, não será feito envio de ordens para aquele candle no futuro, mesmo que algum indicador altere seu valor no passado e troque a decisão de envio de ordem. Alguns exemplos de indicadores que podem causar esse comportamento são indicadores que tem apenas um valor durante todo dia, por exemplo: Preço Ask e Bid e também indicadores que decidem apenas depois de alguns candles, como por exemplo o Detector de topos e fundos ou a linha Chikou Span (2) do indicador IchimokuCloud , entre outros.

## Abrir Estratégias

Na opção de "Abrir Estratégias", o usuário terá acesso a três abas, elas são:

- ● Todas: O usuário poderá ver todas as estratégias dentro do sua plataforma;
- ● Minhas Estratégias: O usuário irá filtrar para somente exibir todas as estratégias criadas por ele dentro da plataforma;
- ● Exemplos: O usuário irá filtrar para exibir exemplos de estratégias que já vem como padrão na plataforma.

Além  das  abas,  o  usuário  também  poderá  pré-visualizar  o  seu  código  de  estratégia  para  confirmar informações.





## Gerenciador de Estratégias

A opção de gerenciador de estratégias, permite ao usuário escolher uma determinada estratégia criada para edição, fazendo com que o Editor de estratégias carregue a estratégia determinada, ao clicar em "Editar".

O usuário também poderá excluir as estratégias desejadas, selecionando as mesmas e clicando no botão "Excluir", além da funcionalidade de renomear a estratégia através do botão "Renomear".


## Exportar / Importar Estratégias

Nesta funcionalidade, permite ao usuário exportar as estratégias criadas por eles para que possam ser importadas novamente.

O usuário também tem a possibilidade de querer exportar o código fonte da estratégia ou apenas o arquivo executável.





Na  importação,  o  usuário  tem  a  funcionalidade  de  escolher  quais  estratégias  serão  carregadas  e adicionadas junto à sua plataforma Nelogica.



## Criar Regra de Coloração

A  funcionalidade  de  criar  regra  de  coloração,  mostra  de  forma  visual,  como  criar  uma  regra  de coloração com as condições desejadas.

A cada vez que for clicado no botão "+" irá criar uma condição para que se Condição 1 e Condição 2 sejam verdadeiras irá colorir de acordo com a cor desejada, na cor padrão será se caso as condições não retornem verdadeiro irá pintar em determinada cor.

Caso o usuário deseje utilizar outras informações, ele irá poder clicar no botão "Mais" que se encontra ao lado da variável para selecionar outras condições.


## Criar Regra de Alarme

A funcionalidade do Criar Regra de Alarme mostra de forma visual, como criar uma regra de alarme de acordo com as condições desejadas.

A cada vez que for clicado no botão "+", será criada uma condição para que se Condição 1 e Condição 2 sejam verdadeiras irá acionar o alarme desejado, e o pop-up de alarme será emitido de acordo com a cor estabelecida.

Caso o usuário deseje utilizar outras informações, ele poderá clicar no botão "Mais" que se encontra ao lado da variável para selecionar outras condições.

Após a criação da regra de alarme, a estratégia deverá ser ativada, através do menu "Ferramentas &gt; Gerenciador de Alarmes &gt; Estratégias", selecione "Novo Alarme".





## Criar Regra de Execução

A  funcionalidade  do  Criar  Regra  de  Execução  mostra  de  forma  visual,  como  criar  uma  regra  de execução de acordo com as condições desejadas.

A cada vez que for clicado no botão "+" irá criar uma condição para que se Condição 1 e Condição 2 sejam verdadeiras irá acionar o alarme desejado e irá colorir o pop-up de alarme de acordo com a cor estabelecida.

Caso o usuário deseje utilizar outras informações, ele poderá clicar no botão "Mais" que se encontra ao lado da variável para selecionar outras condições.



## Screening

A funcionalidade de Screening mostra, de forma visual, os ativos que se encontram na base de dados e que satisfazem as condições da estratégia.

No  filtro, ao clicar no botão "+", será criada uma condição para que, se Condição 1 e Condição 2 sejam verdadeiras, irá mostrar o ativo dentro da aba selecionada.


Caso o usuário deseje utilizar outras informações, ele irá poder clicar no botão "Mais" que se encontra ao lado da variável para selecionar outras condições.

Ao clicar no botão "Aplicar" a estratégia criada é aplicada à lista e irá mostrar os ativos que satisfazem a condição.





## Inserir Regra de Coloração

A funcionalidade de inserir regra de coloração permite ao usuário colorir o gráfico de acordo como ele determinou os parâmetros nos gráficos dos ativos.

As regras de coloração serão feitas seguindo a ideologia de um indicador ou seja, respeitando o layout atual da janela.





## Condições de Coloração

As condições de coloração permitem ao usuário, quais valores ele irá utilizar no momento em que irá criar uma nova regra de coloração, elas podem ser:

- ● Numérico: O usuário poderá utilizar números inteiros ou reais;
- ● Cotação:  O  usuário  poderá  utilizar  os  valores  presente  nas  cotações,  sendo  elas:  Abertura, Máxima, Mínima, Fechamento, Quantidade;
- ● Indicador:  O  usuário  poderá  utilizar  os  valores  presentes  nos  indicadores  criados  por  ele,  e alterar os parâmetros presentes para de acordo com a vontade para coloração;
- ● Cotações Anteriores: Permite ao usuário utilizar os valores presentes nas cotações anteriores, conforme mostra na guia Variáveis e séries de dados.





## Editor de Estratégias

A janela de Editor de estratégias é onde o usuário poderá criar suas próprias estratégias, juntamente com a funcionalidade de visualizar diretamente no gráfico a estratégia criada.

## O Editor de Estratégias possui três abas:

- ● Editor : Onde o usuário escreve a estratégia seguindo as instruções da linguagem NTSL.
- ● Gráfico : Onde o usuário visualiza a estratégia após executada diretamente no gráfico;
- ● Misto :  É onde o usuário visualiza as informações da aba Editor e a aba Gráfico em uma só, onde a cada vez que ele execute o código, já irá aparecer diretamente no gráfico.
- ● Estatísticas : Ao executar uma estratégia de execução pelo editor,  o usuário poderá visualizar a estatística do relatório de performance.








Dentro do Editor de estratégias o usuário irá possuir as seguintes opções:

Nova Estratégia: Onde o usuário irá poder criar uma nova estratégia;

Abrir Estratégia: Permite ao usuário abrir estratégias já criadas e edita-las

Fechar:

Fecha a aba da estratégia atual;

Salvar:

Salva a estratégia atual;

Salvar Como: Salva a estratégia atual, podendo ser adicionado uma descrição da mesma;

Verificar Sintaxe: Realiza a leitura do código verificando se há erros e a transforma em uma estratégia executável;

Trace: Mostra passo-a-passo o que o código da estratégia está realizando e mostrando os valores naquele momento;

Trace Into: Semelhante ao Trace, mostra passo a passo o que a estratégia está realizando no momento de criação, porém, quando há funções no código ele irá abri a função para mostrar ao usuário que a função está executando;

Executar: Após apertar o botão "Compilar", o botão executar irá executar a estratégia criada e a mostra no gráfico;

Parar: Tem como funcionalidade parar a estratégia para que o usuário pare a execução da estratégia criada;

Propriedades: Tem como funcionalidade mostrar as propriedades que irão constituir a estratégia, como desenho no gráfico, linhas guias e escala.

## Propriedades do Editor de Estratégias

Nas propriedades do Editor de estratégias, o usuário irá poder utilizar valores e informações adicionais no momento de criação da estratégia:

- ● Parâmetros: Permite ao usuário utilizar estratégias já criadas como parâmetros para uma nova estratégia junto com o valor desejado para a mesma;
- ● Aparência: Permite ao usuário determinar se deseja que a estratégia seja mostrada em linha ou em histograma;
- ● Linhas Guia: Permite ao usuário criar linhas para se basear como exemplos de linha de suporte e resistência.
- ● Preenchimento: Configuração para visualizar um preenchimento entre as linhas.





## Nova Estratégia

Ao clicar no botão de Nova Estratégia, o usuário poderá escolher entre as opções abaixo:

- ● Em branco (Texto): Ao escolher desta maneira, o usuário ira criar uma estratégia em branco;
- ● Indicador: Ao abrir  a  estratégia,  irá  carregar  um  exemplo  de  estratégia  de  indicador para o usuário;
- ● Coloração: Ao abrir a estratégia, irá carregar um exemplo de regra de coloração para o usuário.
- ● Execução: Será criado um exemplo, com uma função para estratégia de execução.
- ● Screening: Será inserido um exemplo para a criação de um filtro para o Screening.
- ● Alarme: Será criado um exemplo, com a função Alert.





## Lista de Funções

A seguir de forma descritiva, segue a lista de funções presentes nas plataformas da Nelogica:

## Alarme

Alert(Cor : Integer): Dispara uma notificação de alarme.

## Back-Testing

BuyAtMarket: Realiza envio de ordem de compra a mercado.

BuyLimit(Preco : Float; Quantidade : Float= ''):

Realiza envio de uma ordem limite de compra.

BuyPosition: Retorna o tamanho da posição da compra.

BuyPrice: Retorna o preço de compra da posição.

BuyStop(Stop : Float; Limite : Float; Quantidade : Float = ''): Realiza envio de ordem de compra stop.

BuyToCoverAtMarket: Realiza o fechamento de uma operação de venda.




BuyToCoverLimit(Preco : Float; Quantidade : Float = ''): Envia uma ordem de compra limite para fechar a operação.

BuyToCoverStop(Stop  :  Float;  Limite  :  Float; Quantidade : Float = ''): Realiza o envio de ordem de compra stop para fechar posição.

CancelPendingOrders: Cancela as ordens pendentes.

ClosePosition:

Envia ordens para encerrar todas as posições.

HasPendingOrders:

Retorna verdadeiro (True) caso existam ordens pendentes.

HasPosition: Retorna verdadeiro se a posição não é zero.

IsBought: Retorna verdadeiro (True) caso exista posição de compra.

IsSold: Retorna verdadeiro (True) caso exista posição de venda.

MyPrice: Retorna a média entre a máxima, mínima e fechamento.

Position: Retorna o tamanho da posição, positivo para compra e negativo para venda.

Price: Retorna o preço de compra ou venda da posição, dependendo se estiver comprado ou vendido.

ReversePosition: Envia ordens para inverter a posição.

SellPosition: Retorna o tamanho da posição de venda.

SellPrice: Retorna o preço de venda da posição.

SellShortAtMarket: Envia ordem de venda a mercado para abrir posição.

SellShortLimit(Preco : Float; Quantidade : Float = ''): Envia ordem de venda do tipo limite.

SellShortStop(Stop : Float, Limite : Float; Quantidade : Float = ''): Abre uma posição de venda enviando uma ordem do tipo Stop.

SellToCoverAtMarket: Realiza uma ordem de venda a mercado caso exista uma posição de compra.

SellToCoverLimit(Preco : Float; Quantidade : Float = ''): Envia uma ordem de venda limite para fechar a operação.

SellToCoverStop(Stop : Float, Limite : Float; Quantidade : Float = ''): Envia uma ordem stop caso exista uma posição de compra.

SendOrder(Lado : Integer, Tipo : Integer, Quantidade : Float , Limite : Float, Stop : Float): Envia uma ordem customizada.

DailyResult(OpenResult : Boolean):

Retorna o resultado diário

OpenResult : Retorna o resultado diário das operações em aberto

XRay(strName : String, bValue : Boolean, strGroup : String, dValue : Float, ColorOn : Color, ColorOff : Color) : Adiciona uma variável a lista do Raio-X da automação

## Depuração

ConsoleLog(Content : String, Color : Integer = clBlack) Imprime uma string no terminal de console para ajudar na depuração do código.




## Calendário

BarAnnualization: Retorna o fator de anualização, baseado no intervalo da barra.

BarDuration: Retorna, em minutos, a duração da barra atual.

BarDurationF: Retorna, em minutos, a duração da barra atual.

BarType: Retorna um número referente à periodicidade setada.

CalcDate(DataReferencia  :  Integer,  DiasDeslocamento  :  Integer): Retorna  o  resultado  ao efetuar a adição ou subtração de datas.

CalcTime(HoraReferencia : Integer, MinutosDeslocamento : Integer): Retorna o cálculo de adição ou subtração de horas.

CloseD(QuantidadeDiasAnteriores : Integer): Retorna o valor de fechamento de determinado dia anterior.

CloseM(QuantidadeMesesAnteriores : Integer): Retorna o valor de fechamento de determinado mês anterior.

CloseW(QuantidadeSemanasAnteriores  :  Integer): Retorna  o  valor  de  fechamento  de determinada semana anterior.

CloseY(QuantidadeAnosAnteriores : Integer): Retorna o valor de fechamento de determinado ano anterior.

CurrentAssetDate: Retorna a data atual do ativo no gráfico.

CurrentDate:

Retorna a data atual do sistema.

CurrentTime: Retorna a hora atual do sistema.

Date: Retorna a data da barra que está sendo analisada.

DayOfMonth(Data : Integer): Retorna o dia do mês de uma data específica.

DayOfWeek(Data : Integer): Retorna o dia da semana de uma data específica.

DaysToExpiration(Mes : Integer, Ano : Integer): Retorna a quantidade de dias úteis restantes até a terceira sexta-feira de um determinado mês e ano.

ELDate(Ano  :  Integer,  Mes  :  Integer,  Dia  :  Integer): Retorna  a  data  em  EasyLanguage format(YYYMMDD).

ELDate\_Consol(Data : Integer): Transforma uma data YYYYMMDD em EasyLanguage format(YYYMMDD).

FindBar(Data : Integer, Hora : Integer): Localiza uma barra de uma data e hora específica.

Friday: Retorna o número 5 referente ao dia da semana: sexta-feira.

HighestVolume (Interval : Integer; Offset : Integer = 1; Type : Integer = 0; Standard : Boolean = True; Auction : Boolean = True; Cross : Boolean = True)|Rank : Integer|: Retorna o maior volume de acordo com o tipo.

HighestVolumePrice (Interval : Integer; Offset : Integer = 1; Type : Integer = 0; Standard : Boolean = True; Auction : Boolean = True; Cross : Boolean = True  )|Rank : Integer|: ) Retorna o preço do maior volume de acordo com o tipo.

HighD(QuantidadeDiasAnteriores : Integer): dia retroativo.

Retorna o valor de máxima de determinado

HighM(QuantidadeMesesAnteriores : Integer): Retorna o valor de máxima de determinado




mês retroativo.




HighW(QuantidadeSemanasAnteriores  :  Integer): Retorna  o  valor  de  máxima  de determinada semana anterior.

HighY(QuantidadeAnosAnteriores : Integer): Retorna o valor  de máxima  de determinado ano anterior.

LastCalcDate:

Retorna a data do último candle completo do gráfico.

LastCalcTime:

Retorna o horário de fechamento do último candle.

LastDayOfMonth(MesReferencia  :  Integer): Retorna  o  valor  do  último  dia  do  mês  de referência.

LowD(QuantidadeDiasAnteriores : Integer):

Retorna o valor de mínima de determinado dia anterior.

LowM(QuantidadeMesesAnteriores : Integer): Retorna o valor de mínima de determinado mês anterior.

LowW(QuantidadeSemanasAnteriores  :  Integer): Retorna  o  valor  de  mínima  de determinada semana anterior.

LowY(QuantidadeAnosAnteriores : Integer): Retorna o valor de mínima de determinado ano anterior.

MinutesIntoWeek - Retorna o número de minutos até domingo 12 am.

Monday: Retorna o número 1 referente ao dia da semana: segunda-feira.

Month(Date : Integer): Retorna o mês de uma data específica.

Next3rdFriday(Mes : Integer): Retorna quantos dias úteis faltam para a terceira sexta-feira de determinado mês.

OpenD(QuantidadeDiasAnteriores : Integer): Retorna o valor de abertura de determinado dia anterior.

OpenM(QuantidadeMesesAnteriores Integer): Retorna o valor de abertura de determinado mês anterior.

OpenW(QuantidadeSemanasAnteriores :  Integer) Retorna  o  valor  de  abertura  de determinado semana anterior.

OpenY(QuantidadeAnosAnteriores : Integer): Retorna o valor de abertura de determinado ano anterior.

RS\_BarsPerDay: Obtém o número estimado de barras de determinada periodicidade(em minutos).

Saturday: Retorna o número 6 referente ao dia da semana: sábado.

Sunday: Retorna o número 0 referente ao dia da semana: domingo.

Thursday: Retorna o número 4 referente ao dia da semana: quinta-feira.

Time: Retorna a hora de abertura da barra atual.

TimeToMinutes(Hora : Integer): Converte um horário em minutos.

Today: Retorna a data atual do sistema.




Tuesday: Retorna o número 2 referente ao dia da semana: Terça-feira.

VolumeAtPrice (Interval : Integer; Offset : Integer = 1; Type : Integer = 0; Standard : Boolean = True; Auction : Boolean = True; Cross : Boolean = True)|Preço : Float|: Retorna o volume financeiro em determinado preço.

VolumeD(QuantidadeDiasAnteriores : Integer): Retorna o volume financeiro de determinado dia retroativo.

VolumeM(QuantidadeMesesAnteriores  : Integer): Retorna o volume financeiro de determinado mês retroativo.

VolumeW(QuantidadeSemanasAnteriores  :  Integer): Retorna  o  volume  financeiro  de determinada semana anterior.

VolumeY(QuantidadeAnosAnteriores : Integer): Retorna o volume financeiro de determinado ano anterior.

Wednesday: Retorna o número 3 referente ao dia da semana: Quarta-feira.

Year(Date : Integer): Retorna o ano de uma data específica.

## Candlestick

- C\_3WhSolds\_3BlkCrows(Comprimento : Integer,  Fator :  Integer,  var  o3WhiteSoldiers  :  Integer,  var o3BlackCrows  :  Integer): Identifica  a  ocorrência  de  dois  tipos  de  candles:  3  White  Soldiers  e  3  Black Crows.
- C\_BullEng\_BearEng(Comprimento : Integer, var oBullishEngulfing: Integer, var oBearishEngulfing : Integer): Identifica a ocorrência de dois tipos de candles: Bullish Engulfing e Bearish Engulfing.
- C\_Doji(Percentual : Integer): Identifica a ocorrência de um candle: Doji.
- C\_Hammer\_HangingMan(Comprimento  :  Integer,  Fator  :  Integer,  var  oHammer  :  Integer,  var oHangingMan : Integer): Identifica a ocorrência de dois tipos de candles: Hammer e Hanging Man.
- C\_MornDoji\_EveDoji(Comprimento      : Integer, Percentual : Float, var oMorningDojiStar :  Integer,  var  oEveningDojiStar : Integer): Identifica  a  ocorrência de  dois tipos de candles: Morning Doji Star e Evening Doji Star.
- C\_MornStar\_EveStar(Comprimento : Integer, var oMorningStar : Integer, var oEveningStar  :  Integer): Identifica  a  ocorrência  de  dois  tipos  de  candles:  Morning  Star  e Evening Star.
- C\_PierceLine\_DkCloud(Comprimento : Integer, var oPiercingLine : Integer, var oDarkCloud : Integer): Identifica a ocorrência de dois  tipos de candles: Piercing Line e Dark Cloud.
- C\_ShootingStar(Comprimento  :  Integer,    Fator    :    Integer): Identifica    a    ocorrência    de    candles: C\_ShootingStar .

## Exemplos

DiMaisDiMenos(Periodo : Integer): Exemplo de implementação do indicador DI+/DI-.

IFR(Periodo : Integer): Exemplo de implementação do indicador IFR.




## Gráficas

Media(Periodo  :  Integer,  TipoSerie  :  Serie): Exemplo  de  implementação  do  indicador  Média Móvel(Aritmética).

MediaExp(Periodo  :  Integer,  TipoSerie  :  Serie): Exemplo  de  implementação  do  indicador  Média Móvel(Exponencial).

PaintVar: Exemplo de implementação de estratégia de coloração.

WellesSum(Periodo : Integer, SerieReferencia : Serie, Offset : Integer): Exemplo de implementação do indicador WellesSum.

AvgPrice: Retorna a média entre Abertura, Máxima, Mínima, Fechamento de determinado candle.

BarCount: Retorna a quantidade total de barras.

CurrentBar: Retorna o índice atual da barra(candle).

GetPlotColor(NumeroPlot : Integer): Retorna o valor numérico da cor de determinado Plot.

GetPlotWidth(NumeroPlot : Integer): Retorna o valor da espessura de determinado Plot.

GraphicInterval: Retorna o intervalo do gráfico.

GraphicOffset: Retorna o offset do gráfico.

HorizontalLine (Y : Float; Color : Interger): Adiciona um estudo horizontal, em um indicador.

LastBarOnChart: Retorna se é a última barra do gráfico.

Leader: Retorna se ponto médio é menor que mínima ou maior que máxima de candle anterior.

MaxBarsBack:

Percorre a lista da série, a partir do primeiro candle criado(índice 0).

MaxBarsForward: Percorre a lista da série, a partir do candle atual(índice 0).

MedianPrice: Retorna a média entre a máxima e a mínima de determinado candle.

NoPlot(NumeroPlot : Integer): Remove determinado Plot.

PaintBar(Cor : Integer): Colore os candles e indicadores do gráfico.

Plot(Dado : Float): Desenha o indicador de acordo com o gráfico.

PlotN(Plot : Interger; Valor : Float):

Adiciona um valor em um indicador.

PlotText(Content : String; Color : Integer; Position : Integer; FontSize : Integer; dPrice : Float): Adiciona um texto a um indicador.

Range: Retorna o valor de Máxima menos Mínima do determinado candle.

RangeLeader:

Verifica se a barra atual é Range Leader.

RGB(Red : Integer, Green : Integer, Blue : Integer): Coloração a partir dos parâmetros RGB.

SetPlotColor(NumeroPlot : Integer, Cor : Integer): Altera a coloração de determinado Plot.




SetPlotStyle(NumeroPlot  :  Integer;  Estilo  :  Integer): Altera  o  estilo  da  linha  de  um  plot específico.

SetPlotType(Number : Integer; Type : Integer): Altera o tipo de gráfico de determinado plot.

SetPlotWidth(NumeroPlot : Integer, Espessura : Integer): Altera a espessura de determinado Plot.

TrueHigh: Retorna o maior entre o máximo da barra e o fechamento da barra anterior.

TrueLow: Retorna o menor entre o mínimo da barra e o fechamento da barra anterior.

TrueRange: Retorna o valor do indicador TrueRange.

TrueRangeCustom(Maxima  :  Float,  Minima  :  Float,  Fechamento  :  Float): Retorna  o  TrueRange  de acordo com os dados informados pelo usuário.

TypicalPrice: Retorna o valor médio entre a máxima, mínima e fechamento de determinado candle.

VerticalLine(X : Integer; Color : Integer): Adiciona um estudo vertical em um indicador.

WeightedClose: Retorna a média entre o ponto médio da barra e dois fechamentos.

## Indicadores

AccAgressSaldo(TipoVolume :  Integer): Retorna  o  valor  do  indicador  TR  -  Acúmulo  de  Agressão  - Saldo.

AccuDistr: Retorna o valor do indicador Acumulação/Distribuição.

AccuDistrW: Retorna o valor do indicador Acumulação/Distribuição Williams.

AdaptiveMovingAverage(Periodo  :  Integer,  FastSC  :  Integer,  SlowSC  :  Integer): Retorna  o  valor  do indicador Adaptive Moving Average(AMV).

ADX(Periodo : Integer, PeriodoMedia : Integer): Retorna o valor do indicador ADX.

AgressionVolBalance: Retorna o valor do indicador TR - Volume de Agressão - Saldo.

AgressionVolBuy: Retorna o valor do indicador TR - Volume de Agressão - Compra.

AgressionVolSell: Retorna o valor do indicador TR - Volume de Agressão - Venda.

ArmsEaseOfMov(Media  :  Integer,  TipoMedia  :  Integer): Retorna  o  valor  do  indicador  Arms  Ease  of Movement.

AroonLin(Periodo : Integer)|Linha Desejada|: Retorna o valor do indicador Aroon Linha.

AroonOsc(Periodo : Integer): Retorna o valor do indicador Aroon Oscilador.

AvgAgrBuySell(AlertaVariacoes :  Integer,  TipoVolume  :  Integer,  TipoDesenho:  Integer)|Linha  : Integer|: Retorna o valor do indicador TR - Agressão Média - Compra e Venda.

AvgAgrTotal(AlertaVariacoes : Integer,  TipoVolume  :  Integer,  TipoDesenho:  Integer)|Linha  : Integer|: Retorna o valor do indicador TR - Agressão Média - Total.

AvgSeparation(Periodo  :  Integer,  TipoMedia  :  Integer): Retorna  o  valor  do  indicador Afastamento Médio.




AvgTrueRange(Periodo : Integer, TipoMedia : Integer): Retorna o valor do indicador True Range.

BalanceOfPower(Media : Integer, TipoMedia : Integer): Retorna o valor do indicador Balança do poder.

BearPower(Periodo : Integer): Retorna o valor do indicador Bear Power.

BollingerBands(Desvio : Float, Media : Integer, TipoMedia : Integer)|Linha : Integer|: Retorna o valor da linha da Banda de Bollinger de acordo com a linha desejada.

BollingerBandW(Desvio  :  Float,  Media  :  Integer,  TipoMedia  :  Integer): Retorna  o  valor  do indicador Bollinger Band Width.

BollingerBPerc(Desvio  :  Float,  Media  :  Integer,  TipoMedia  :  Integer): Retorna  o  valor  do indicador Boolinger b%.

BullPower(Periodo : Integer, PeriodoMedia : Integer, TipoMedia : Integer): Retorna o valor do indicador Bull Power.

CCI(Periodo : Integer): Retorna o valor do indicador CCI.

ChaikinMoneyFlow(Periodo : Integer): Retorna o valor do indicador Chaikin Money Flow.

ChaikinOsc(MediaLonga:  Integer,  MediaCurta  :  Integer): Retorna  o  valor  do  indicador Oscilador Chaikin.

ChainSetup: Retorna o dado do indicador ChainSetup.

CohenPriceWave(Ticks : Integer): Desenvolvido por Rodrigo Cohen e equipe, indica a diferença absoluta de preços de cada swing do ativo.

CohenWeisWave(Ticks : Integer): Desenvolvido por Rodrigo Cohen e equipe, indica a soma do volume de cada swing do ativo. Serve como um indicador de exaustão.

ContadorDeCandle: Contabiliza e sinaliza  de forma numérica e organizada no gráfico o número de cada candle.

DarvasBox|Linha : Integer|: Retorna o valor do indicador Darvas Box.

DecisionPoints(Tipo : Integer, Linha : Integer): Retorna o valor do indicador Pontos de Decisão.

DiDiIndex(MedRef : Integer, TipoMedRef : Integer, Med1 : Integer, TipoMed1 : Integer, Med2

: Integer, TipoMed2 : Integer)|Linha : Integer|:

Retorna o valor do indicador DiDi Index.

DiPDiM(Periodo : Integer)|Linha : Integer|: Retorna o valor do indicador DI+/DI- de acordo com a linha desejada.

DonchianCH(Periodo : Integer)|Linha : Integer|: Retorna o valor do indicador Canal Donchian de acordo com a linha desejada.

DTOscillator(PeriodoEstocastico : Integer, PeriodoSK : Integer, TipoSK : Integer, PeriodoSD :  Integer,  TipoSD  :  Integer)|Linha  :  Integer|: Retorna  o  valor  do  indicador  DT Oscillator, de acordo com a linha desejada.

Envelope(Percentual : Float, PeriodoMedia : Integer, TipoMedia : Integer)|Linha : Integer|: Retorna o valor do indicador Envelope.

Euroinvest(Risco:  Integer,  ModoCalculo  :  Integer,  Periodo  :  Integer,  Desvio  :  Float,  UsarVWAP  : Boolean, UsarAtr : Boolean) Retorna o valor do indicador Euroinvest.




FastStochastic(Periodo  :  Integer,  PeriodoMedia  :  Integer,  TipoMedia  :  Integer): Retorna  o  valor  do indicador Estocástico Rápido.

FinancialVol(VolumeProjetado : Boolean, Agressores : Boolean): Retorna o Valor do volume financeiro.

ForceIndex(Periodo : Integer, TipoMedia : Integer):

Retorna o valor do indicador Force Index.

FrassonATR(Fator : Float, PeriodoMaxMin : Integer, PeriodoATR : Integer)|Linha : Integer|: Retorna o valor do indicador Frasson ATR.

FrassonVH(Fator : Float, PeriodoMaxMin : Integer, PeriodoVH : Integer)|Linha : Integer|: Retorna o valor do indicador Frasson VH.

FullStochastic(Periodo : Integer): Retorna o valor do indicador Estocástico Pleno.

FuraChao(Coeficiente  :  Float,  Deslocamento : Integer): Retorna o valor do indicador Fura Chão.

FuraTeto(Coeficiente  :  Float,  Deslocamento  :  Integer): Retorna  o  valor  do indicador Fura Teto.

HeikinAshi(Media : Integer, TipoMedia : Integer)|Dado : Integer|: Retorna o valor do indicador HeikinAshi.

HiLoActivator(Periodo  :  Integer)|Linha  :  Integer|: Retorna  o  valor  do  HiLo  Activator  de acordo com a linha desejada.

HistVolatility(Periodo : Integer, TipoMedia : Integer): Retorna o valor do indicador Volatilidade Histórica.

HSI(Periodo : Integer):

Retorna o valor do indicador IFR Índice de Força Harmônico (HSI).

HullMovingAverage(Periodo : Integer): Retorna o valor do indicador Hull Moving Average.

IchimokuCloud(TenkanSen : Integer, KijunSen : Integer, SenkouSpanB : Integer)|Linha : Integer|: Retorna o valor do indicador Ichimoku Cloud.

IFR(Periodo : Integer): Retorna o valor do indicador IFR.

ImpliedVolatility(ModeloTeorico :  Boolean,  TipoOpcao  :  Boolean): Retorna  o  cálculo  do  indicador Volatilidade Implícita, dependendo do tipo de cálculo utilizado.

KeltnerCH(Desvio : Float, Periodo : Integer, TipoMedia : Integer)|Linha : Integer|: Retorna o valor do indicador Keltner Chanels, conforme com a linha desejada.

KVO(MediaLonga  :  Integer,  MediaCurta  :  Integer,  Sinal  :  Integer)|Dado  :  Integer|: Retorna  o  dado desejado do indicador KVO Linha &amp; Histograma.

LinearRegressionChannel(Periodo : Integer; UsarDesvioSuperior : Boolean; DesvioSuperior : Float; UsarDesvioInferior : Boolean; DesvioInferior : Float): Canal de regressão linear

LSVolatilityIndex Retorna o dado desejado do indicador L&amp;S Volatility Index.

MACD(MediaLonga  :  Integer,  MediaCurta  :  Integer,  Sinal  :  Integer)|Dado : Integer|: Retorna o dado desejado do indicador KVO Linha &amp; Histograma.

Media(Periodo : Integer, TipoSerie : Serie): Retorna o dado do indicador Média Móvel(Aritmética).

MediaExp(Periodo : Integer, TipoSerie : Serie): Retorna o dado do indicador Média Móvel(Exponencial).




MFI: Retorna o valor do indicador Market Facilitation Index.

MIMA(Periodo : Integer): Retorna o dado do indicador PhiCube - MIMA.

MIMAROC(Periodo : Integer): Retorna o dado do indicador PhiCube - MIMAROC.

Momentum(Periodo  :  Integer,  Media  :  Integer,  TipoMedia  :  Integer): Retorna  o  valor  do  indicador Momentum.

MomentumStochastic(Periodo  : Integer): Retorna o valor do indicador Momento Estocástico.

MoneyFlow:

Retorna o valor do indicador Money Flow.

MoneyFlowIndex(Periodo  :  Integer): Retorna o valor do indicador Money Flow Index de acordo com o período utilizado.

NelogicaBottomFinder|Dado : Integer|: Retorna o valor do indicador Nelogica Bottom Finder de acordo com a linha Desejada.

NelogicaPullBackFinder|Dado :  Integer|:

Retorna  o  valor  do  indicador  Nelogica  PullBack  Finder  de

acordo com a linha desejada.

NelogicaWeisWave(Periodo período desejado.

: Integer): Retorna o valor do indicador Nelogica Weis Wave, conforme o

OBV: Retorna o valor do indicador OBV.

OBVAvg: Retorna o valor do indicador OBV Ponderado.

OnBalanceTR: Retorna o valor do indicador On Balance True Range.

OpenDaily(DaysBack : Integer):

Retorna o dado de abertura, conforme o deslocamento especificado.

OpenInterest: Retorna o valor do indicador Contratos em aberto.

ParabolicSAR(Fator : Float, Limite : Float):

Retorna o valor do indicador SAR Parabólico.

Phibo(Periodo : Integer): Retorna o valor do indicador PhiCube - Phibo Line.

Pivot(Normal : Boolean, TresLinhas : Boolean)|Linha : Integer|: Retorna o valor do indicador Pivot, de acordo com a linha selecionada.

PowerMeter(Side  :  Integer,  Minutes  :  Integer  =  0,  InitialDate  :  Integer  =  0,  EndDate  :  Integer  =  0): Retorna  os  dados  do  indicador  PowerMeter(Medidor  de  Pressão),  informa  a  quantidade  do  Agressor Comprador ou do Agressor Vendedor, dependendo dos parâmetros fornecidos

PriceNery: Retorna os dados do indicador Price Nery.

PriceOsc(Media1 : Integer, TipoMedia1 : Integer, Media2 : Integer, TipoMedia2 : Integer) : Retorna o valor do indicador Oscilador de Preços.

PriceVolumeTrend:

Retorna o valor do indicador Tendência Preço/Volume.

PriorCote(Dado : Integer): Retorna o valor do indicador Prior Cote, de acordo com o dado desejado.

PTAX: Retorna o valor do indicador TR - PTAX.

PTAXFuturo: Retorna o valor do indicador TR - PTAX Futuro.




QuantityVol(VolumeProjetado : Boolean, Agressores : Boolean): Retorna o valor do indicador Volume Quantidade.

Rafi: Retirna o valor do indicador Rafi.

Ravi(MediaCurta  :  Integer,  MediaLonga  :  Integer): Retorna  o  valor  do  indicador  Ravi,  de acordo com os períodos das médias desejadas.

RBG: Retorna os dados do indicador RBG.

RenkoVTwo(Periodo : Integer, Abertura : Float, Deslocamento : Integer): Retorna o dado do indicador RenkoV2, conforme a linha desejada.

ROC(Periodo : Integer, Media : Integer, TipoMedia : Integer): Retorna o valor do indicador ROC.

RSI(Periodo : Integer, Tipo : Integer): Retorna o valor do indicador IFR(RSI).

RsiStochastic(Periodo : Integer): Retorna o valor do indicador IFR Estocástico.

SafeZoneDownTrend(Multiplicador : Float, Periodo : Integer, Deslocamento : Integer): Retorna o valor do indicador Stop SafeZone DownTrend.

SafeZoneUpTrend(Multiplicador : Float, Periodo : Integer, Deslocamento : Integer): Retorna o valor do indicador Stop SafeZone UpTrend.

Santo(Periodo : Integer)|Linha : Integer|: Retorna o valor do indicador PhiCube - Santo.

SlowStochastic(Periodo : Integer): Retorna o valor do indicador Estocástico Lento.

SOMOSRENKOTRENDMPONTO  |Linha  :  Integer|: Retorna  o  valor  do  indicador  SomoRenko  - SR\_MPONTO, de acordo com a linha desejada

StopATR(Desvio  :  Float,  Periodo  :  Integer,  TipoMedia  : Integer)|Dado : Integer|: Retorna o valor do indicador Stop ATR, de acordo com o dado desejado.

TendencyTracker(Dias :  Integer): Retorna  o  valor  do  indicador  Rastreador  de Tendências, conforme o período desejado.

Tilson(Fator : Float, Media : Integer): Retorna o valor do indicador Tillson's T3 Moving Average.

TimeAgrBuySell(AlertaVariacoes  :  Integer): Retorna  o  valor  do  indicador  TR  -  Tempo Agressão - Compra.

TimeAgrTotal(AlertaVariacoes  : Integer):

Retorna o valor do indicador TR - Tempo Agressão - Total.

TopBottomDetector(Periodo    : Integer):

Retorna o valor do indicador Detector de Topos e Fundos.

Trades: Retorna o valor do indicador Negócios.

TrendCloud (DiasRetroativos  :  Integer; CorCompra : Integer; VWAP : Integer; CorVenda : Integer): Retorna o valor do indicador TrendCloud, de acordo com os parâmetros desejados.

TrendSniper(DiasRetroativos  :  Integer;  VWAP  :  Integer;  CorCompra  :  Integer;  CorVenda : Integer; Reversao : Integer): Retorna o valor do indicador TrendSniper, de acordo com os parâmetros desejados.

TRIX(Media : Integer, TipoMedia : Integer): Retorna o valor do indicador TRIX.

TRIXM(Media : Integer, TipoMedia : Integer): Retorna o valor do indicador TRIXM.




## Livro

TwoMVAggression:

Retorna o dado do indicador 2MV Agressão.

TwoMVPower(Periodo1 : Integer, Periodo2 : Integer, Periodo3 : Integer, Media : Integer): Retorna o valor do indicador 2MV Power.

TwoMVStandard: Retorna o dado do indicador 2MV Padrão.

UltimateOscillator(PeriodoCurto: Integer, PeriodoMedio : Integer, PeriodoLongo : Integer): Retorna o valor do Ultimate Oscillator desenvolvido por Larry Williams.

Valerie(Periodo : Integer; Offset : Integer): Retorna o valor do indicador Valerie, conforme os parâmetros desejados.

VSS(Multiplicador  :  Float,  Media  :  Integer,  Deslocamento  :  Integer): indicador VSS.

Retorna  o  valor  do

VWAP(Periodo : Integer):

Retorna o valor do indicador VWAP, conforme a periodicidade desejada.

VWAPDate(Date  :  Integer;  Time  :  Integer)(Periodo  : Integer): Retorna o preço médio ponderado pelo volume, a partir de uma data e horário específicos.

VWAPMonthly: Retorna o dado do indicador VWMA Mensal.

VWAPWeekly: Retorna o dado do indicador VWMA Semanal.

VWMA(Periodo : Integer): Retorna o dado do indicador VWMA, conforme o período desejado.

WAverage(TipoSerie : SeriePeriodo, Periodo : Integer): Retorna o dado do indicador Média Móvel(Ponderada).

WellesSum(Periodo  :  Integer, SerieReferencia : Serie, Offset : Integer): Retorna o dado do indicador WellesSum.

Williams(Periodo : Integer): Retorna o valor do indicador Williams %R, de acordo com o período desejado.

xAverage(TipoSerie  :  SeriePeriodo,  Periodo  :  Integer): Retorna  o  dado  do  indicador  Média Móvel(Exponencial).

AskPrice: Retorna o preço da melhor oferta de venda.

AskSize: Retorna a quantidade da melhor oferta de venda.

BidPrice: Retorna o preço da melhor oferta de compra.

BidSize: Retorna a quantidade da melhor oferta de compra.

BookSpread: Retorna a diferença entre o topo do livro.

BuyOfferCount(Asset : Ativo = '', Preço Considerado : Integer = 0): Retorna a quantidade de ofertas de compra do Ativo.

GetAsset(Asset : Ativo = ''):

Retorna o ticker do ativo

GetFeed(Asset : Ativo = ''): Retorna o código textual do Feed do ativo.

IsBMF: Verifica se o ativo pertence ao segmento BMF.




Lote: Retorna a quantidade de contratos referente ao lote.

MinPriceIncrement:

Retorna o incremento mínimo do preço.

SellOfferCount(Asset : Ativo = '', Preço Considerado : Integer = 0): venda do Ativo.

Retorna a quantidade de ofertas de

TotalBuyQtd(Asset : Ativo = '', Preço Considerado : Integer = 0):

Retorna a quantidade de compras do

Ativo.

TotalSellQtd(Asset : Ativo = '', Preço Considerado : Integer = 0): Retorna a quantidade de vendas do

Ativo.

## Matemáticas

ABS(Valor : Float): Retorna o valor absoluto(sem sinal).

Arctangent(Numero : Float): Retorna o arcotangente(em graus) de um número.

Ceiling(Numero : Float): Retorna o menor inteiro maior que um número específico.

Combination(Numero  :  Integer,  QtdGrupos  :  Integer): Retorna  a  quantidade  de  combinações, considerando um conjunto específico de números.

Cos(Valor : Float): Retorna o valor de um Cosseno em radianos.

Cosine(Valor : Float): Retorna o valor de um Cosseno em graus.

Cotangent(Valor : Float): Retorna o valor de uma Cotangente em graus.

Cum(SerieDeDados : Serie): Acumula o valor de uma série de dados.

Exp(Valor : Float): Retorna a enésima potência do número de Euler.

ExpValue(Valor : Float): Retorna o valor exponencial de um determinado número(e^x).

ExtremePriceRatio:

Obtém o ratio das extremidades de um número determinado de barras.

Factorial(Valor : Float):

Retorna o fatorial do valor estabelecido (1*2*. n).

FastD(Periodo : Integer): Retorna o valor de FastD do Oscilador Estocástico.

FastK(Periodo : Integer): Retorna o valor de FastK do Oscilador Estocástico.

FastKCustom(PrecoH  : Serie, PrecoL : Serie, PrecoC : Serie, Periodo : Integer): Retorna o valor de FastK a partir de preços específicos.

Floor(Valor : Float): Retorna o maior inteiro, menor que um número específico.

FracPortion(Valor : Float): Retorna a parte fracionário de um número.

GCD(Valor1 : Float, Valor2 : Float): Retorna o maior divisor comum entre dois números.

HarmonicMean(SerieDados : Serie, Periodo : Integer): Retorna a média harmônica de uma série de dados baseada em um período.

Highest(SerieS Dados : Serie, Periodo : Integer): Retorna o maior valor da série dentro do período.




HighestBar(SerieDeDados : Serie, Periodo : Integer): Retorna o índice do maior valor da série no período.

IntPortion(Valor : Float): Retorna a parte inteira de um número.

Log(Valor : Float): Retorna o logaritmo natural(ln) de um número de um número.

Lowest(SerieDeDados : Serie, Periodo : Integer): Retorna o menor valor da série dentro no período.

LowestBar(SerieDeDados : Serie, Periodo : Integer): Retorna o índice da barra com o menor valor da série no período.

Max(Valor1

: Float, Valor2 : Float): Retorna o maior valor entre dois números.

MidPoint(SerieDados  :  Serie,  Periodo  :  Integer):

Retorna  a  média  entre  o  maior  e  o  menor  valor

encontrados no período.

Min(Valor1

: Float, Valor2 : Float): Retorna o menor valor entre dois números.

MinutesIntoWeek(DiaLimite :  Integer,  HoraLimite  :  Integer): Retorna  o  valor  de  minutos desde  a meia noite em horas.

MinutesToTime(Minutos : Integer): Retorna o valor de minutos desde a meia noite em horas.

Mod(Dividendo : Integer, Divisor : Integer): Retorna o resto da divisão entre dois números.

Neg(Numero : Float): Retorna o valor negativo de um determinado número.

NumUnits(Amnt  :  Integer,  MinLot  :  Integer): Retorna  o  número  de  contratos/ações  de  um  certo investimento.

PercentChange(SerieDados  :  Serie,  Periodo  :  Integer): Retorna  a  alteração  percentual  no  preço  do candle atual.

PercentR(Comprimento : Integer): Retorna uma porcentagem de onde o preço atual está, relacionado com a faixa de negociação avaliada.

Permutation(Numero : Integer, NumeroObjetos : Integer): Calcula um número de permutações.

Pos(Valor : Float):

Retorna o valor absoluto(sem sinal).

Power(Base : Float, Expoente : Integer): Eleva valores nas determinadas potências.

PriceOscillator(SerieDados  :  Serie,  ComprimentoRapido  :  Integer,  ComprimentoLento  :  Integer): Retorna o valor do indicador Price Oscillator.

Random(Limite : Integer): Retorna um valor aleatório de 0 até o limite.

RateOfChange(SerieDados : Serie, Periodo : Integer): Retorna a variação percentual de uma série.

Round(Valor : Float): Arredondamento de número.

Round2Fraction(Valor  :  Float): Arredonda  o  número  para  o  valor  mais  próximo  de  um  múltiplo  do incremento mínimo de um ativo.

Sign(Valor : Float): Retorna um número inteiro, baseado no sinal de um número.

Sin(Valor : Float): Retorna o valor de Seno em radianos.




Sine(Valor : Float):

Retorna o valor de Seno em graus .

SlowD(Periodo : Integer):

Retorna o valor SlowD do Oscilador Estocástico.

SlowK(Periodo : Integer): Retorna o valor SlowK do Oscilador Estocástico.

Sqrt(Valor : Float):

Retorna raiz quadrada dos valores.

Square(Valor : Float): Retorna o valor de um número ao quadrado.

StdDevs(SerieDados : Serie, Periodo : Integer): Calcula o desvio padrão de uma série de dados em um determinado período.

Summation(SerieDados : Serie, Periodo : Integer): Acumula o valor do preço de um determinado número de barras.

Tangent(Valor : Float): Retorna a tangente de um número em graus.

TriAverage(SerieDados  : Serie, Periodo : Integer): Calcula a média triangular de uma série de dados, dentro de um certo período.

UlcerIndex(SerieDados : Serie, Periodo : Integer): Retorna o valor do indicador UlcerIndex.

Volatility(Periodo : Integer): Retorna a volatilidade de determinado período.

VolumeOsc(PeriodoMediaRapida :  Integer,  PeriodoMediaLenta  :  Integer): Retorna  a  diferença entre a média aritmética rápida e a média aritmética lenta da série Volume.

VolumeROC(Periodo : Integer): Retorna VolumeROC baseado em um número de barras.

## Opções

Delta(DaysLeft : Integer, StrikePr : Float, AssetPr : Float, Rate100 : Float, Volty100 : Float, PutCall : Integer): Retorna o valor de Delta.

Gamma(DaysLeft : Integer, StrikePr : Float, AssetPr : Float, Rate100 : Float, Volty100 : Float, PutCall :

Integer): Retorna o valor de Gamma.

Rho(DaysLeft : Integer, StrikePr : Float, AssetPr : Float, Rate100 : Float, Volty100 : Float, PutCall :

Integer): Retorna o valor de Gamma.

Theta(DaysLeft : Integer, StrikePr : Float, AssetPr : Float, Rate100 : Float, Volty100 : Float, PutCall : Integer): Retorna o valor de Theta.

Vega(DaysLeft : Integer, StrikePr : Float, AssetPr : Float, Rate100 : Float, Volty100 : Float, PutCall : Integer): Retorna o valor de Vega.

## Screening

Select: Seleciona um ativo para mostrar no Screening.

