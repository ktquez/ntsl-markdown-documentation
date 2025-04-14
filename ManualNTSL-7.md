# Função VWAP

## Descrição:
A função VWAP retorna o valor do indicador VWAP, de acordo com a periodicidade desejada.

## Sintaxe:
VWAP(Periodo : Integer)

## Parâmetros:
- Periodo: Período para obter o dado do indicador:
  - 0 - Barra
  - 1 - Diário
  - 2 - Semanal
  - 3 - Mensal

## Retorno:
Float

## Exemplos:
No exemplo, a variável "nVWAP" irá receber o valor do indicador VWAP, considerando a periodicidade diária.

```
nVWAP := VWAP(1);
```

# Função VWAPDate

## Descrição:
A função VWAPDate retorna o preço médio ponderado pelo volume, a partir de uma data e horário específicos.

## Sintaxe:
VWAPDate(Data : Integer; Time : Integer)

## Parâmetros:
- Data: Data de referência para início do cálculo. A Data precisa ser uma constante.
- Time: Horário inicial.

## Retorno:
Float

## Exemplos:
No exemplo, será plotado o retorno da chamada, considerando a partir da data atual às 9h00.

```
const startdate = 1230101;
begin
  Plot(VWAPDate(startdate, 900));
end;
```

# Função VWAPMonthly

## Descrição:
A função VWAPMonthly retorna o valor do indicador VWAP Mensal.

## Sintaxe:
VWAPMonthly

## Parâmetros:
Sem parâmetros.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "nVWAP" irá receber o valor do indicador VWAPMonthly.

```
nVWAP := VWAPMonthly;
```

# Função VWAPWeekly

## Descrição:
A função VWAPWeekly retorna o valor do indicador VWAP Semanal.

## Sintaxe:
VWAPWeekly

## Parâmetros:
Sem parâmetros.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "nVWAP" irá receber o valor do indicador VWAPWeekly.

```
nVWAP := VWAPWeekly;
```

# Função VWMA

## Descrição:
A função VWMA retorna o valor do indicador VWMA, de acordo com o período desejado.

## Sintaxe:
VWMA(Periodo : Integer)

## Parâmetros:
- Periodo: Período utilizado no momento do cálculo do indicador.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "nVWMA" irá receber o valor do indicador VWMA, considerando 10 períodos para o cálculo.

```
nVWMA := VWMA(10);
```

# Função WAverage

## Descrição:
A função WAverage retorna o valor do indicador Média Móvel, tipo ponderada.

## Sintaxe:
WAverage(TipoSerie : SeriePeriodo, Periodo : Integer)

## Parâmetros:
- TipoSerie: Série que será considerada para o cálculo.
- Periodo: Período utilizado no momento do cálculo do indicador.

## Retorno:
Float

## Exemplos:
No exemplo, será atribuído à variável "vMed" o valor do indicador Média Móvel(Ponderada), considerando 100 períodos, e a série de fechamento(Close) para o cálculo.

```
vMed := WAverage(Close, 100);
```

# Função Williams

## Descrição:
A função Williams retorna o valor do indicador Williams %R, de acordo com o período desejado.

## Sintaxe:
Williams(Periodo : Integer)

## Parâmetros:
- Periodo: Período utilizado no momento do cálculo do indicador.

## Retorno:
Float

## Exemplos:
No exemplo, será atribuído à variável "nW" o valor do indicador Williams %R, considerando 14 períodos para o cálculo.

```
nW := Williams(14);
```

# Função xAverage

## Descrição:
A função xAverage retorna o valor do indicador Média Móvel, tipo exponencial.

## Sintaxe:
xAverage(TipoSerie : SeriePeriodo, Periodo : Integer)

## Parâmetros:
- TipoSerie: Série que será considerada para o cálculo.
- Periodo: Período utilizado no momento do cálculo do indicador.

## Retorno:
Float

## Exemplos:
No exemplo, será atribuído à variável "vMed" o valor do indicador Média Móvel(Exponencial), considerando 100 períodos, e a série de fechamento(Close) para o cálculo.

```
vMed := xAverage(Close, 100);
```

## Livro

## ask := AskPrice;

# Função AskPrice

## Descrição:
A função AskPrice retorna o preço da melhor oferta de venda.

## Sintaxe:
AskPrice

## Parâmetros:
Sem parâmetros.

## Retorno:
Float

## Exemplos

No exemplo, será atribuído à variável "ask" o valor do topo(melhor oferta de venda) do livro.

# Função AskSize

## Descrição:
A função AskSize retorna a quantidade da melhor oferta de venda.

Atenção: Ao utilizar o modo de CrossOrder na automação, o AskSize irá retornar a quantidade do AskSize da seríe histórica, e não no ativo de negociação.

## Sintaxe:
AskSize

## Parâmetros:
Sem parâmetros.

## Retorno:
Float

## Exemplos

No exemplo, será atribuído à variável "qtdAsk" a quantidade do topo(melhor oferta de venda) do livro.

# Função BidPrice

## Descrição:
A função BidPrice retorna o preço da melhor oferta de compra.

## Sintaxe:
BidPrice

## Parâmetros:
Sem parâmetros.

## Retorno:
Float

## Exemplos

No exemplo, será atribuído à variável "bid" o valor do topo(melhor oferta de compra) do livro.

# Função BidSize

## Descrição:
A função BidSize retorna a quantidade da melhor oferta de compra.

Atenção: Ao utilizar o modo de CrossOrder na automação, o BidSize irá retornar a quantidade do BidSize da seríe histórica, e não no ativo de negociação.

## Sintaxe:
BidSize

## Parâmetros:
Sem parâmetros.

## Retorno:
Float

## Exemplos

No exemplo, será atribuído à variável "qtdBid" a quantidade do topo(melhor oferta de compra) do livro.

```
qtdBid := BidSize;
```

# Função BookSpread

## Descrição:
A função BookSpread retorna a diferença entre os melhores preços de compra e venda, no topo do livro.

## Sintaxe:
BookSpread

## Parâmetros:
Sem parâmetros.

## Retorno:
Float

## Exemplos

No exemplo, será atribuído à variável "spread" a diferença entre os valores das melhores ofertas de compra e venda.

```
spread := BookSpread;
```

# Função BuyOfferCount

## Descrição:
A função BuyOfferCount retorna as Ofertas de Compra do Ativo

## Sintaxe:
BuyOfferCount(Asset : Ativo = ''; Níveis Considerados : Integer = 1)

## Parâmetros:
Asset: Parâmetro Opcional declarado a partir do recurso Asset, valor padrão é ''

Níveis Considerados : Parâmetro opcional inteiro que indica a quantidade de níveis considerados do livro de ofertas. Caso 1, retorna a qtd de ofertas do primeiro nível de compra do livro de ofertas. Caso 2, retorna a Qtd de ofertas do primeiro e segundo níveis de compra do livro de ofertas, e assim sucessivamente.

## Retorno:
Integer

## Exemplos

Ambos  os  exemplos  atribuem  a  quantidade  de  ofertas  de  compra  para  a  variável  'buy\_count',  o Exemplo  02  se  diferencia  do  Exemplo  01  por  especificar  o  ativo  que  deseja  obter  a  contagem  de ofertas de compra, no caso PETR4.

## Exemplo 01:

```
var buy_count : Integer; begin buy_count := BuyOfferCount; end;
```

## Exemplo 02:

```
var buy_count : Integer; begin buy_count := BuyOfferCount(PETR4); end;
```

# Função GetAsset

## Descrição:
A  função GetAsset retorna  o  ticker  do  ativo,  onde  a  chamada  pode  ser  efetuada  realizando  a passagem do parâmetro opcional, para retornar o ticker de determinado Asset, ou declarar a função sem parametrização, onde será retornado o ticker do gráfico selecionado.

Para retornar o ticker (String) do Asset declarado, basta acessar de forma análoga às séries de dados: A1.GetAsset.

## Sintaxe:
GetAsset(Asset : Ativo = '')

## Parâmetros:
Variação 01: Asset: Variação 02: Sem parâmetros

Constante declarada a partir do recurso Asset

## Retorno:
String

## Exemplos

No primeiro exemplo, para o último candle, será visualizado o nome do ativo selecionado no gráfico, com os preços de bid e ask.

Para o segundo exemplo, a distinção está na especificação do Asset que será exibido (WDOFUT), independentemente do ativo selecionado no gráfico.

## Exemplo 01 (Variação 01):

```
begin
  Print("Ativo: " + GetAsset + " Bid: " + NumToStr(BidPrice, 2) + " Ask: " + NumToStr(AskPrice, 2));
end;
```

## Exemplo 02 (Variação 02):

```
begin
  Print("Ativo: " + GetAsset(WDOFUT) + " Bid: " + NumToStr(BidPrice, 2) + " Ask: " + NumToStr(AskPrice, 2));
end;
```

# Função GetFeed

## Descrição:
A função GetFeed retorna o código textual do Feed do ativo.

A parametrização é opcional, caso não seja determinado o Asset, será retornado o ticker do gráfico selecionado.

Para retornar a bolsa relacionada (String) do Asset específico, pode-se acessar de forma análoga às séries de dados: A1.GetFeed.

## Sintaxe:
GetFeed(Asset : Ativo = '')

## Parâmetros:
Variação 01: Asset: Variação 02: Sem parâmetros

Constante declarada a partir do recurso Asset

## Retorno:
String

## Exemplos

No primeiro exemplo, para o último candle, será visualizado o nome do ativo selecionado no gráfico, a bolsa a qual pertence, e o spread do book.

No segundo, será identificada a bolsa (F) vinculada ao Asset definido (WDO), independentemente do ativo selecionado.

## Exemplo 01 (Variação 01):

```
begin
  Print("Ativo: " + GetAsset + " Bolsa: " + GetFeed + " Spread: " + NumToStr(BookSpread, 2));
end;
```

## Exemplo 02 (Variação 02):

```
begin
  Print("Bolsa: " + GetFeed(WDO));
end;
```

# Função IsBMF

## Descrição:
A função IsBMF retorna se o ativo pertence ao segmento BMF.

## Sintaxe:
IsBMF

## Parâmetros:
Sem parâmetros.

## Retorno:
Boolean

## Exemplos

No exemplo, caso o ativo pertença ao BMF, será plotado o preço da melhor oferta de venda.

```
if(IsBMF) then
  Plot(AskPrice);
```

# Função Lote

## Descrição:
A função Lote retorna a quantidade mínima de contratos referente ao lote do ativo.

Atenção: Ao utilizar o modo de CrossOrder na automação, o Lote irá retornar a quantidade do Lote da seríe histórica, e não no ativo de negociação.

## Sintaxe:
Lote

## Parâmetros:
Sem parâmetros.

## Retorno:
Float

## Exemplos

No exemplo, será atribuído à variável "qtd" a quantidade do lote.

```
qtd := Lote;
```

# Função MinPriceIncrement

## Descrição:
A função MinPriceIncrement retorna o incremento mínimo do preço do ativo.

## Sintaxe:
MinPriceIncrement

## Parâmetros:
Sem parâmetros.

## Retorno:
Float

## Exemplos

No exemplo, será atribuído à variável "incMin" o valor do incremento mínimo.

```
incMin := MinPriceIncrement;
```

# Função SellOfferCount

## Descrição:
A função SellOfferCount retorna as Ofertas de Venda do Ativo

## Sintaxe:
SellOfferCount(Asset : Ativo = ''; Níveis Considerados : Integer = 1)

## Parâmetros:
Asset: Parâmetro Opcional declarado a partir do recurso Asset, valor padrão é ''

Níveis Considerados : Parâmetro opcional inteiro que indica a quantidade de níveis considerados do livro de ofertas. Caso 1, retorna a qtd de ofertas do primeiro nível de venda do livro de ofertas. Caso 2, retorna a Qtd de ofertas do primeiro e segundo níveis de venda do livro de ofertas, e assim sucessivamente.

## Retorno:
Integer

## Exemplos
Ambos  os  exemplos  atribuem  a  quantidade  de  ofertas  de  venda  para  a  variável  'sell\_count',  o Exemplo  02  se  diferencia  do  Exemplo  01  por  especificar  o  ativo  que  deseja  obter  a  contagem  de ofertas de venda, no caso PETR4.

## Exemplo 01:

```
var sell_count : Integer; 
begin 
  sell_count := SellOfferCount; 
end;
```

## Exemplo 02:

```
var sell_count : Integer; 
begin 
  sell_count := SellOfferCount(PETR4); 
end;
```

# Função TotalBuyQtd

## Descrição:
A função TotalBuyQtd retorna a quantidade de Compras do Ativo.

## Sintaxe:
TotalBuyQtd(Asset : Ativo = ''; Níveis Considerados : Integer = 1)

## Parâmetros:
Asset: Parâmetro Opcional declarado a partir do recurso Asset, valor padrão é ''

Níveis Considerados : Parâmetro opcional inteiro que indica a quantidade de níveis considerados do livro de ofertas. Caso 1, retorna o total da Qtd do primeiro nível de compra do livro de ofertas. Caso 2, retorna o total da Qtd do primeiro e segundo níveis de compra do livro de ofertas, e assim sucessivamente.

## Retorno:
Integer

## Exemplos
Ambos os exemplos atribuem a quantidade de compras para a variável 'buy\_qtd', o Exemplo 02 se diferencia do Exemplo 01 por especificar o ativo que deseja obter a quantidade de compras, no caso PETR4.

## Exemplo 01:

```
var buy_qtd : Integer; 
begin 
  buy_qtd := TotalBuyQtd; 
end;
```

## Exemplo 02:

```
var buy_qtd : Integer; 
begin 
  buy_qtd := TotalBuyQtd(PETR4); 
end;
```

# Função TotalSellQtd

## Descrição:
A função TotalSellQtd retorna a quantidade de Vendas do Ativo.

## Sintaxe:
TotalSellQtd(Asset : Ativo = ''; Níveis Considerados : Integer = 1)

## Parâmetros:
Asset: Parâmetro Opcional declarado a partir do recurso Asset, valor padrão é ''

Níveis Considerados : Parâmetro opcional inteiro que indica a quantidade de níveis considerados do livro de ofertas. Caso 1, retorna o total da Qtd do primeiro nível de venda do livro de ofertas. Caso 2, retorna o total da Qtd do primeiro e segundo níveis de venda do livro de ofertas, e assim sucessivamente.

## Retorno:
Integer

## Exemplos
Ambos os exemplos atribuem a quantidade de vendas para a variável 'sell\_qtd', o Exemplo 02 se diferencia do Exemplo 01 por especificar o ativo que deseja obter a quantidade de vendas, no caso PETR4.

## Exemplo 01:

```
var sell_qtd : Integer; 
begin 
  sell_qtd := TotalSellQtd; 
end;
```

## Exemplo 02:

```
var sell_qtd : Integer; 
begin 
  sell_qtd := TotalSellQtd(PETR4); 
end;
```

## Matemáticas

# Função ABS

## Descrição:
A função ABS retorna o valor absoluto de um número ponto flutuante.

## Sintaxe:
ABS(Valor : Float)

## Parâmetros:
Valor: Valor ou variável para obter o módulo.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "n" irá receber o módulo(4) do valor -4.

```
n := ABS(-4);
```

# Função Arctangent

## Descrição:
A função Arctangent retorna o arcotangente(em graus) de determinado número.

## Sintaxe:
Arctangent(Numero : Float)

## Parâmetros:
Numero: Número que será convertido.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "arc" irá receber o arcotangente, em graus, do número 12.

```
arc := Arctangent(12);
```

# Função Ceiling

## Descrição:
A função Ceiling efetua um arredondamento, retornando o menor inteiro maior que um número específico.

## Sintaxe:
Ceiling(Numero : Float)

## Parâmetros:
Numero: Número que será arredondado.

## Retorno:
Integer

## Exemplos:
No exemplo abaixo, usamos a função Ceiling para retornar o menor inteiro maior que o valor 2,3(Retorno: 3).

```
aux := Ceiling(2.3);
```

# Função Combination

## Descrição:
A função Combination calcula o número de grupos com combinação única, considerando um conjunto específico de números.

## Sintaxe:
Combination(Numero : Integer, QtdGrupos : Integer)

## Parâmetros:
Numero: Total de números, ou itens, a serem considerados; QtdGrupos: Número de itens únicos em cada grupo.

## Retorno:
Integer

## Exemplos:
No exemplo, será atribuído à variável "nComb" o número de grupos da combinação(4,2), onde o resultado será 6, conforme o cálculo: (1,2), (1,3), (1,4), (2,3), (2,4) e (3,4).

```
nComb := Combination(4,2);
```

# Função Cos

## Descrição:
A função Cos tem como objetivo retornar ao usuário o Cosseno de um valor em radianos.

## Sintaxe:
Cos(Valor : Float)

## Parâmetros:
Valor: Valor ou variável para obter o Cosseno.

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será atribuído à variável "nCos" o Cosseno do valor 180 em radianos(-0,60).

```
nCos := Cos(180);
```

# Função Cosine

## Descrição:
A função Cosine tem como objetivo retornar ao usuário o Cosseno de um valor em graus.

## Sintaxe:
Cosine(Valor : Float)

## Parâmetros:
Valor: Valor ou variável para obter o Cosseno.

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será atribuído à variável "nCos" o Cosseno do valor 45 em graus(0,71).

```
nCos := Cosine(45);
```

# Função Cotangent

## Descrição:
A função Cotangent tem como objetivo retornar ao usuário a Cotangente de um valor em graus.

## Sintaxe:
Cotangent(Valor : Float)

## Parâmetros:
Valor: Valor ou variável para obter a Cotangente.

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será atribuído à variável "nCo" a Cotangente do valor 30 em graus.

```
nCo := Cotangent(30);
```

# Função Cum

## Descrição:
A função Cum acumula o valor de uma série de dados, desde a primeira barra até a atual.

## Sintaxe:
Cum(SerieDeDados : Serie)

## Parâmetros:
SerieDeDados: Série para efetuar o somatório.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "aux" irá receber o somatório da diferença entre as séries Close e Open.

```
aux := Cum(Close - Open);
```

# Função Exp

## Descrição:
A função Exp tem como objetivo retornar ao usuário a enésima potência do número de Euler.

## Sintaxe:
Exp(Valor : Float)

## Parâmetros:
Valor: Valor ou uma variável para obter a enésima potência(Euler).

## Retorno:
Float

## Exemplos:
No seguinte exemplo, a função Exp recebe o valor de "2" e irá retornar o valor "7,39".

```
n := Exp(2);
```

# Função ExpValue

## Descrição:
A função ExpValue possui como finalidade retornar o valor exponencial de um determinado número(e^x).

## Sintaxe:
ExpValue(Valor : Float)

## Parâmetros:
Valor: Valor ou uma variável para obter o valor exponencial(e^x).

## Retorno:
Float

## Exemplos:
No seguinte exemplo, a função ExpValue recebe o valor de "2" e irá retornar o valor "7,39".

```
n := ExpValue(2);
```

# Função ExtremePriceRatio

## Descrição:
A função ExtremePriceRatio retorna o ratio das extremidades(divide o maior valor no periodo pelo menor valor) de um número determinado de barras.

## Sintaxe:
ExtremePriceRatio(Length : Integer, UseLog : Boolean)

## Parâmetros:
Length: O número de barras que serão considerados no cálculo.

UseLog: Deterna se o logaritmo de 10 do resultado da divisão será aplicado.

True Não é calculado o LOG

False É calculado o LOG

## Retorno:
Float

## Exemplos:
No exemplo, será atrubuído à variável "pRatio" o retorno da função, considerando 300 períodos para a divisão.

```
pRatio := ExtremePriceRatio(300, True);
```

# Função Factorial

## Descrição:
A função Factorial tem como finalidade efetuar o cálculo fatorial(n!) de um número natural n.

## Sintaxe:
Factorial(Valor : Float)

## Parâmetros:
Valor: Número natural para o cálculo do factorial.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "nFatorial" irá receber o fatorial do número 4.

```
nFatorial := Factorial(4);
```

# Função FastD

## Descrição:
A função FastD retorna o valor de FastD do Oscilador Estocástico, de acordo com o período desejado.

## Sintaxe:
FastD(Periodo : Integer)

## Parâmetros:
Periodo: Período utilizado no momento do cálculo do indicador.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "d" irá receber o retorno da função FastD, considerando 14 períodos para o cálculo.

```
d := FastD(14);
```

# Função FastK

## Descrição:
A função FastK retorna o valor de FastK do Oscilador Estocástico, de acordo com o período desejado.

## Sintaxe:
FastK(Periodo : Integer)

## Parâmetros:
Periodo: Período utilizado no momento do cálculo do indicador.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "k" irá receber o retorno da função FastK, considerando 14 períodos para o cálculo.

```
k := FastK(14);
```

# Função FastKCustom

## Descrição:
A função FastKCustom retorna o valor de FastK do Oscilador Estocástico, de acordo com os preços determinados por parâmetro, e período desejado.

## Sintaxe:
FastKCustom(PrecoH : Serie, PrecoL : Serie, PrecoC : Serie, Periodo : Integer)

## Parâmetros:
PrecoH: Série de referência para a máxima.

PrecoL: Série de referência para a mínima.

PrecoC: Série de referência para o fechamento.

Periodo: Período utilizado no momento do cálculo do indicador.

## Retorno:
Float

## Exemplos:
No exemplo, será atribuído à variável "KCustom" o retorno da função FastKCustom, considerando as séries de máxima(PrecoH), mínima(PrecoL), fechamento(PrecoC), e 14 períodos para o cálculo.

```
KCustom := FastKCustom(High, Low, Close, 14);
```

# Função Floor

## Descrição:
A função Floor possui como finalidade retornar o maior valor inteiro menor que um número determinado.

## Sintaxe:
Floor(Valor : Float)

## Parâmetros:
Valor: Valor de referência para obter o dado específico.

## Retorno:
Integer

## Exemplos:
Nos exemplos, serão atribuídos, às variáveis "m" e "n", os valores -7 e 6, respectivamente.

```
m := Floor(-6.1);
n := Floor(6.1);
```

# Função FracPortion

## Descrição:
A função FracPortion tem como recurso retornar a parte fracionário de determinado número.

## Sintaxe:
FracPortion(Valor : Float)

## Parâmetros:
Valor: Número para obter a parte fracionária.

## Retorno:
Float

## Exemplos:
No exemplo, será atribuído à variável "dec" o valor -0.59.

```
dec := FracPortion(-6.59);
```

# Função GCD

## Descrição:
A função GCD retorna o maior denominador comum entre dois números

## Sintaxe:
GCD(Valor1 : Float, Valor2 : Float)

## Parâmetros:
Valor1: Primeiro valor a ser analisado;

Valor2: Segundo valor a ser analisado.

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será atribuído à variável "nDem" o maior denominador comum entre 12 e 9.

```
nDem := GCD(12, 9);
```

# Função HarmonicMean

## Descrição:
A função HarmonicMean calcula a média harmônica de uma série de dados, baseada em um determinado período.

## Sintaxe:
HarmonicMean(SerieDados  : Serie, Periodo : Integer)

## Parâmetros:
SerieDados: Série utilizada para o cálculo. Periodo: Período utilizado no momento do cálculo.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "aux" irá receber o retorno da função HarmonicMean, considerando a máxima(Close) e 20(Períodos) para o cálculo.

```
aux := HarmonicMean(High, 20);
```

## Funcão Highest

## Descrição:
A função Highest tem como funcionalidade retornar ao usuário o maior valor da série estipulada por ele, dentro de um período determinado.

## Sintaxe:
Highest(SerieDeDados : Serie, Periodo : Integer)

## Parâmetros:
SerieDeDados: Série de dados desejada, podendo ser a abertura, máxima, mínima, fechamento, ou até mesmo indicadores.

Periodo: Determina o período que será considerado para a pesquisa.

## Retorno:
Float

## Exemplos:
No exemplo abaixo, usamos a função Highest para retornar a maior abertura dentro de 9 períodos.

```
Plot(Highest(Open, 9)) ;
```

## Funcão HighestBar

## Descrição:
A função HighestBar tem como funcionalidade retornar ao usuário o índice do maior valor da série estipulada por ele, dentro de um período determinado.

## Sintaxe:
HighestBar(SerieDeDados
: Serie, Periodo : Integer)

## Parâmetros:
SerieDeDados: Série de dados desejada, podendo ser a abertura, máxima, mínima, fechamento, ou até mesmo indicadores.

Periodo: Determina o período que será considerado para a pesquisa.

## Retorno:
Float

## Exemplos:
No exemplo abaixo, usamos a função HighestBar para retornar o índice da maior mínima dentro de 20 períodos.

```
mMinima := HighestBar(Open, 9);
```

# Função IntPortion

## Descrição:
A função IntPortion tem como recurso retornar a parte inteira de determinado número.

## Sintaxe:
IntPortion(Valor : Float)

## Parâmetros:
Valor:

Número para obter a parte inteira.

```
aux := IntPortion(7.52);
```

# Função Log

## vLn := Log(5);

## Retorno:
Float

## Exemplos:
No exemplo, será atribuído à variável "aux" o valor 7.

## Descrição:
A função Log retorna o logaritmo natural(ln) de um número.

## Sintaxe:
Log(Valor : Float)

## Parâmetros:
Log: Número para o logaritmo natural(ln).

## Retorno:
Float

## Exemplos:
No exemplo, será atribuído à variável "vLn" o ln de 5(1,6).

```
vLn := Log(5);
```

# Função Lowest

## Descrição:
A função Lowest tem como funcionalidade retornar ao usuário o menor valor da série estipulada por ele, dentro de um período determinado.

## Sintaxe:
Lowest(SerieDeDados : Serie, Periodo : Integer)

## Parâmetros:
SerieDeDados: Série de dados desejada, podendo ser a abertura, máxima, mínima, fechamento, ou até mesmo indicadores.

Periodo: Determina o período que será considerado para a pesquisa.

## Retorno:
Float

## Exemplos:
No exemplo abaixo, usamos a função Lowest para retornar o menor fechamento dentro de 50 períodos.

```
Plot(Lowest(Close, 50)) ;
```

# Função LowestBar

## Descrição:
A função LowestBar tem como funcionalidade retornar ao usuário o índice do menor valor da série estipulada por ele, dentro de um período determinado.

## Sintaxe:
LowestBar(SerieDeDados : Serie, Periodo : Integer)

## Parâmetros:
SerieDeDados: Série de dados desejada, podendo ser a abertura, máxima, mínima, fechamento, ou até mesmo indicadores.

Periodo: Determina o período que será considerado para a pesquisa.

## Retorno:
Float

## Exemplos:
No exemplo abaixo, usamos a função LowestBar para retornar o índice da menor mínima dentro de 26 períodos.

```
mMinima := LowestBar(Low, 26);
```

# Função Max

## Descrição:
A função Max retorna o maior valor entre dois números.

## Sintaxe:
Max(Valor1 : Float, Valor2 : Float)

## Parâmetros:
Valor1: Primeiro número da comparação

Valor2: Segundo número da comparação.

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será atribuído à variável "dMax" valor 20.0, que é o maior valor entre 10 e 20.

```
dMax := Max(10.0, 20);
```

# Função MidPoint

## Descrição:
A função MidPoint retorna a média entre o maior e o menor valor encontrados no período.

## Sintaxe:
MidPoint(SerieDados : Serie, Periodo : Integer)

## Parâmetros:
SerieDados:

Série de referência.

Periodo: Período utilizado no momento do cálculo.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "midP" irá receber o valor da função MidPoint, considerando o fechamento(SerieDados) e 15(Períodos) para o cálculo.

```
midP := MidPoint(Close, 15);
```

# Função Min

## Descrição:
A função Min retorna o menor valor entre dois números.

## Sintaxe:
Min(Valor1 : Float, Valor2 : Float)

## Parâmetros:
Valor1:

Primeiro número da comparação

Valor2: Segundo número da comparação.

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será atribuído à variável "dMin" valor 10.0, que é o menor valor entre 10 e 20.

```
dMin := Min(10.0, 20);
```

# Função MinutesIntoWeek

## Descrição:
A função MinutesIntoWeek retorna o número de minutos entre domingo(Dia: 0 - Hora: 0h00) até o dia e hora determinados por parâmetro.

## Sintaxe:
MinutesIntoWeek(DiaLimite  : Integer, HoraLimite : Integer)

## Parâmetros:
DiaLimite: Dia de limite para a conversão em minutos.

Referência de dias da semana:

- 0 - Domingo
- 1 - Segunda
- 2 - Terça
- 3 - Quarta
- 4 - Quinta
- 5 - Sexta
- 6 - Sábado

HoraLimite: Hora de limite para a conversão.

## Retorno:
Integer

## Exemplos:
No exemplo a seguir, será atribuído à variável "tMin" o total de minutos(8.640) entre domingo(Dia: 0 - Hora: 0h00) e sábado(Dia: 6 - Hora: 0h00).

```
tMin := MinutesIntoWeek(6, 0000);
```

# Função MinutesToTime

## Descrição:
A função MinutesToTime retorna a conversão de minutos em hora militar(contagem iniciada à meia noite).

## Sintaxe:
MinutesToTime(Minutos
: Integer)

## Parâmetros:
Minutos: Minutos para a conversão em horas.

## Retorno:
Integer

## Exemplos:
No exemplo a seguir, a variável "nHora" irá receber a conversão de 600 minutos em horas, ou seja, será retornado o valor 1000, representando 10h.

```
nHora := MinutestoTime(600);
```

# Função Mod

## Descrição:
A função Mod possui como finalidade retornar o resto da divisão entre dois números inteiros.

## Sintaxe:
Mod(Dividendo : Integer, Divisor : Integer)

## Parâmetros:
Dividendo: Número referente ao Dividendo.

Divisor: Número que será o divisor.

```
res := Mod(10, 3);
```

# Função Neg

# Função Neg retorna o valor negativo de um determinado número.

## Sintaxe:
Neg(Numero : Float)

## Parâmetros:
Numero: Valor para obter seu número negativo.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "nNeg" irá receber o retorno(-5) da função.

```
nNeg := Neg(5);
```

# Função NumUnits

## Descrição:
A função NumUnits retorna o número de contratos/ações de um certo investimento.

## Sintaxe:
NumUnits(Amnt : Integer, MinLot : Integer)

## Parâmetros:
Amnt: Valor total de investimento, em reais, por trade. MinLot: Tamanho mínimo desejado de lote por transação.

## Retorno:
Integer

## Exemplos:
No exemplo, assumindo que a ação selecionada está com preço de 65,00 por ação, se quiser investir 15500 em 100 ações, você poderia comprar 200 ações(NumUnits(15500, 100) = 200).

```
numU := NumUnits(15500, 100);
```

# Função PercentChange

## Descrição:
A função PercentChange calcula a alteração percentual no preço do candle atual sobre determinado descolcamento.

## Sintaxe:
PercentChange(SerieDados  : Serie, Periodo : Integer)

## Parâmetros:
SerieDados:

Série base de referência.

Periodo: Período anterior para a comparação com o dado da série atual.

## Retorno:
Float

## Exemplos:
No exemplo, será atribuído à variável "pc" o retorno da função PercentChange, considerando a série de fechamento(Série de dados) e 2 períodos para a comparação.

```
pc := PercentChange(Close, 2);
```

# Função PercentR

## Descrição:
A função PercentR retorna uma porcentagem de onde o preço atual está, relacionado com a faixa de negociação avaliada.

## Sintaxe:
PercentR(Comprimento : Integer)

## Parâmetros:
Comprimento: Comprimento considerado para o cálculo.

## Retorno:
Float

## Exemplos:
Será atribuído à variável "PercentR" o retorno da função PercentR, considerando 2 como comprimento.

```
vPercentR := PercentR(2);
```

# Função Permutation

## Descrição:
A função Permutation calcula o número de permutações para um determinado número de objetos.

## Sintaxe:
Permutation(Numero : Integer, NumeroObjetos : Integer)

## Parâmetros:
Numero: Determina o número de candles a serem analisados.

NumeroObjetos: Define o número de objetos dentro do intervalo de candles que podem ser selecionados.

## Retorno:
Integer

## Exemplos:
A variável "n" irá receber a combinação, considerando 4(Número de candle) e 2(Número de objetos).

```
n := Permutation(4,2);
```

# Função Pos

## Descrição:
A função Pos retorna o valor absoluto de um número ponto flutuante.

## Sintaxe:
Pos(Valor : Float)

## Parâmetros:
Valor: Valor ou variável para obter o módulo.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "n" irá receber o módulo(4) do valor -4.

```
n := Pos(-4);
```

# Função Power

## Descrição:
A função Power tem como finalidade retornar a enésima potência de um valor.

## Sintaxe:
Power(Base : Float, Expoente : Integer)

## Parâmetros:
Base:

Valor para a base da potênciação;

Expoente: Valor no qual a base será elevada.

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será atribuído à variável "x" a potência da operação(2^3).

```
x := Power(2, 3);
```

# Função PriceOscillator

## Descrição:
A função PriceOscillator retorna o valor do indicador Price Oscillator , de acordo com os parâmetros desejados.

## Sintaxe:
PriceOscillator(SerieDados  : Serie, ComprimentoRapido : Integer, ComprimentoLento : Integer)

## Parâmetros:
SerieDados: Série utilizada para o cálculo do indicador. ComprimentoRapido: Referente ao parâmetro FastLength. ComprimentoLento: Referente ao parâmetro SlowLength.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "pOsc" irá receber o valor do indicador Price Oscillator, considerando a série de máxima(SerieDados), 9(ComprimentoRapido) e 18(ComprimentoLento) para o cálculo.

```
pOsc := PriceOscillator(High, 9, 18);
```

# Função Random

## Descrição:
Com a função Random , o usuário poderá gerar um número aleatório(Inteiro), dentro de um intervalo(iniciado em zero) que possui como limite o valor determinado por parâmetro.

## Sintaxe:
Random(Limite : Integer)

## Parâmetros:
Limite: Recebe um valor ou uma variável para determinar o limite do intervalo, para geração do número.

## Retorno:
Integer

## Exemplos:
No exemplo a seguir, a função Random irá gerar números aleatórios entre 0 até 5, os quais serão atribuídos à variável "aux".

```
aux := Random(5);
```

# Função RateOfChange

## Descrição:
A função RateOfChange retorna a variação percentual de uma série de dados.

## Sintaxe:
RateOfChange(SerieDados : Serie, Periodo : Integer)

## Parâmetros:
SerieDados:

Série base de referência.

Periodo: Índice do dado para a comparação com o último valor da série.

## Retorno:
Float

## Exemplos:
No exemplo, será atribuído à variável "rc" o retorno da função RateOfChange, considerando a série de máxima(Série de dados), e o candle anterior para calcular a variação.

```
rc := RateOfChange(High, 1);
```

# Função Round

## Descrição:
A função Round possui como finalidade efetuar o arredondamento de um número ponto flutuante.

## Sintaxe:
Round(Valor : Float)

## Parâmetros:
Valor: Número(variável ou constante) com casas decimais.

## Retorno:
Integer

## Exemplos:
Conforme no exemplo a seguir, será atribuído à variável "aux" o valor arredondado de 2.6, ao utilizar a função Round.

```
aux := Round(2.6);
```

# Função Round2Fraction

## Descrição:
A função Round2Fraction efetua o arredondamento de um número, para o valor mais próximo de um múltiplo do incremento mínimo de um ativo.

## Sintaxe:
Round2Fraction(Valor : Float)

## Parâmetros:
Valor: Valor desejado para o arredondamento de acordo com o incremento mínimo do ativo.

## Retorno:
Float

## Exemplos:
No exemplo abaixo(ativos Bovespa), ao aplicar a função para o valor 27.626, será atribuído o valor 27,63 para a variável "nRound2".

```
nRound2 := Round2Fraction(27.626);
```

# Função Sign

## Descrição:
A função Sign possui como definição retornar um número inteiro, baseado no sinal de um número.

## Sintaxe:
Sign(Valor : Float)

## Parâmetros:
- Valor: Número para obter seu sinal.

## Retorno:
Float: Determina qual linha será obtida: Resultados possíveis:
- -1 Número com sinal negativo.
- 0 -Sem sinal (zero).
- 1 Número com sinal positivo.

## Exemplos:
No exemplo, será atribuído à variável "nSinal" o valor -1, tendo em vista o valor(-205) passado por parâmetro.

```
nSinal := Sign(-205);
```

# Função Sin

## Descrição:
A função Sin tem como objetivo retornar o Seno de um valor em radianos.

## Sintaxe:
Sin(Valor : Float)

## Parâmetros:
- Valor: Valor para obter o Seno.

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será atribuído à variável "sSeno" o Seno do valor 180 em radianos(-0,80).

```
nSeno := Sin(180);
```

# Função Sine

## Descrição:
A função Sine tem como objetivo retornar o Seno de um valor em graus.

## Sintaxe:
Sine(Valor : Float)

## Parâmetros:
- Valor: Valor para obter o Seno.

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será atribuído à variável "sSeno" o Seno do valor 45 em graus(0,71).

```
nSeno := Sine(45);
```

# Função SlowD

## Descrição:
A função SlowD retorna o valor do SlowD (Oscilador Estocástico), de acordo com o período desejado.

## Sintaxe:
SlowD(Periodo : Integer)

## Parâmetros:
- Periodo: Período utilizado no momento do cálculo do indicador.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "sd" irá receber o valor do indicador SlowD, considerando 14 períodos para o cálculo.

```
sd := SlowD(14);
```

# Função SlowK

## Descrição:
A função SlowK retorna o valor do SlowK (Oscilador Estocástico), de acordo com o período desejado.

## Sintaxe:
SlowK(Periodo : Integer)

## Parâmetros:
- Periodo: Período utilizado no momento do cálculo do indicador.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "sk" irá receber o valor do indicador SlowK, considerando 14 períodos para o cálculo.

```
sk := SlowK(14);
```

# Função Sqrt

## Descrição:
A função Sqrt tem como funcionalidade retornar ao usuário o valor da raiz quadrada de um número.

## Sintaxe:
Sqrt(Valor : Float)

## Parâmetros:
- Valor: Valor para obter a raiz quadrada.

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será atribuído à variável "nRaiz", a raiz quadrada do valor 25.

```
nRaiz := Sqrt(25);
```

# Função Square

## Descrição:
A função Square tem como funcionalidade retornar ao usuário o valor de um determinado número ao quadrado.

## Sintaxe:
Square(Valor : Float)

## Parâmetros:
- Valor: Valor para elevar ao quadrado.

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será atribuído à variável "n", o valor ao quadrado do número 5.

```
n := Square(5);
```

# Função StdDevs

## Descrição:
A função StdDevs retorna o desvio padrão de uma série de dados, em um determinado período.

## Sintaxe:
StdDevs(SerieDados : Serie, Periodo : Integer)

## Parâmetros:
- SerieDados: Série utilizada para o cálculo.
- Periodo: Período utilizado no momento do cálculo.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "sd" irá receber o retorno da função StdDevs, considerando o fechamento(Close) e 20(Períodos) para o cálculo.

```
sd := StdDevs(Close, 20);
```

# Função Summation

## Descrição:
A função Summation efetua o somatório do valor do preço de um determinado número de barras.

## Sintaxe:
Summation(SerieDados : Serie, Periodo : Integer)

## Parâmetros:
- SerieDados: Série utilizada para o cálculo.
- Periodo: Período utilizado no momento do cálculo.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "s" irá receber o retorno da função Summation, considerando o fechamento(Close) e 10(Períodos) para o cálculo.

```
s := Summation(Close, 10);
```

# Função Tangent

## Descrição:
A função Tangent tem como objetivo retornar ao usuário a Tangente de um valor em graus.

## Sintaxe:
Tangent(Valor : Float)

## Parâmetros:
Valor: Valor ou variável para obter a Tangente.

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será atribuído à variável "nTan" a Tangente do valor 30 em graus(0,58).

```
nTan := Tangent(30);
```

# Função TriAverage

## Descrição:
A função TriAverage efetua a média triangular de uma série de dados, dentro de um determinado período.

## Sintaxe:
TriAverage(SerieDados : Serie, Periodo : Integer)

## Parâmetros:
- SerieDados: Série utilizada para o cálculo.
- Periodo: Período utilizado no momento do cálculo.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "aux" irá receber o retorno da função TriAverage, considerando a máxima(Close) e 20(Períodos) para o cálculo.

```
aux := TriAverage(High, 20);
```

# Função UlcerIndex

## Descrição:
A função UlcerIndex mede o nível de estresse de acordo com as condições do mercado.

## Sintaxe:
UlcerIndex(SerieDados : Serie, Periodo : Integer)

## Parâmetros:
- SerieDados: Série utilizada para o cálculo.
- Periodo: Período utilizado no momento do cálculo.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "aux" irá receber o retorno da função UlcerIndex, considerando a máxima(Close) e 3(Períodos) para o cálculo.

```
aux := UlcerIndex(High, 3);
```

# Função Volatility

## Descrição:
A função Volatility retorna a volatilidade de determinado período.

## Sintaxe:
Volatility(Periodo : Integer)

## Parâmetros:
Periodo: Período para cálculo do indicador.

## Retorno:
Float

## Exemplos:
No exemplo, será atribuído à variável "vol" o retorno da função, considerando 10 períodos.

```
vol := Volatilidade(10);
```

# Função VolumeOsc

## Descrição:
A função VolumeOsc retorna a diferença entre a média aritmética rápida e a média aritmética lenta da série de Volume (financeiro).

## Sintaxe:
VolumeOsc(PeriodoMediaRapida : Integer, PeriodoMediaLenta : Integer)

## Parâmetros:
PeriodoMediaRapida: Período utilizado para a média aritmética rápida. PeriodoMediaLenta: Período utilizado para a média aritmética lenta.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "difVol" irá receber o valor do indicador VolumeOsc, considerando 9(Média Rápida) e 21(Média Lenta) períodos para o cálculo.

```
difVol := VolumeOsc(9, 21);
```

# Função VolumeROC

## Descrição:
A função VolumeROC retorna o VolumeROC baseado em um número de barras.

## Sintaxe:
VolumeROC(Periodo : Integer)

## Parâmetros:
Periodo: Período utilizado para a cálculo.

## Retorno:
Float

## Exemplos:
No exemplo, será atribuído à variável "VolR" o retorno da função VolumeROC, considerando 5(Períodos).

```
VolR := VolumeROC(5);
```

# Utils

# Função BoolToString

## Descrição:
A função BoolToString transforma uma variável booleana em uma string..

## Sintaxe:
BoolToString(bValue : Boolean)

## Parâmetros:
bValue : Valor booleano para ser transformado em string

## Retorno:
Retorna o valor booleano em forma de String

## Exemplos:
No exemplo, será impresso os dias e as variações do WDOFUT em que teve variação de mais de 4%.

```
begin
  BoolToString(True);
end;
```

# Função CompareFloat

## Descrição:
A função CompareFloat compara 2 números de ponto flutuante, com base na precisão especificada, por padrão, essa precisão é configurada como 9 dígitos.

## Sintaxe:
CompareFloat(dValor1, dValor2, nPrecisionDigits);

## Parâmetros:
- dValor1: Valor float a ser comparado com o segundo valor informado
- dValor2: Valor float a ser comparado com o primeiro valor informado

## Retorno:
Retorna um valor inteiro com o resultado da comparação. Retorna 1 se o Valor1 for maior, 0 se os valores forem iguais e -1 caso o Valor1 seja menor. Também é possível utilizar constantes de comparação para facilitar as comparações.

```
if CompareFloat(dMedia1, dMedia2, 4) = 1 then dResult1 := dMedia1;

if CompareFloat(dMedia2, dMedia1, 5) = GreaterThanValue then dResult2 := dMedia2;
```

# Opções

# Função Delta

## Descrição:
A função Delta mede a variação do preço da opção com o preço da ação.

## Sintaxe:
Delta(DaysLeft  :  Integer,  StrikePr  :  Float,  AssetPr  :  Float,  Rate100  :  Float,  Volty100  :  Float,  PutCall  : Integer)

## Parâmetros:
- DaysLeft: Dias uteis até o vencimento da opção
- StrikePr: Preço do exercício da opção
- AssetPr: Preço da ação
- Rate100: Taxa de juros em %
- Volty100: Volatilidade em %
- PutCall: Indica se é uma put ou uma call
- optPut -  Opção de venda
- optCall - Opção de compra

## Retorno:
Float

## Exemplos:
No  exemplo,  a  variável  "opD"  irá  receber  a  variação,  considerando  13  dias  para  o vencimento, 16.47 como Strike, 17.25 como preço da ação, 0.1 para taxa de juros e 0.25 para volatilidade, aplicados para uma Call.

```
opD := Delta(13, 16.47, 17.25, 0.1, 0.25, optCall);
```

# Função Gamma

## Descrição:
A função Gamma mede a variação do delta em relação ao preço da ação.

## Sintaxe:
Gamma(DaysLeft : Integer, StrikePr : Float, AssetPr : Float, Rate100 : Float, Volty100 : Float, PutCall : Integer)

## Parâmetros:
- DaysLeft: Dias uteis até o vencimento da opção
- StrikePr: Preço do exercício da opção
- AssetPr: Preço da ação
- Rate100: Taxa de juros em %
- Volty100: Volatilidade em %
- PutCall: Indica se é uma put ou uma call
- optPut - Opção de venda
- optCall - Opção de compra

## Retorno:
Float

## Exemplos:
No  exemplo,  será  atribuido  à  variável  "opG",  a  variação,  considerando  9  dias  para  o vencimento, 11.08 como Strike, 11.94 como preço da ação, 0.2 para taxa de juros e 0.3 para volatilidade, aplicados sobre uma Call.

```
opG := Gamma(9, 11.08, 11.94, 0.2, 0.3, optCall);
```

# Função Rho
A função Rho retorna a variação da opção em relação à taxa de juros.

## Sintaxe:
Rho(DaysLeft : Integer, StrikePr : Float, AssetPr : Float, Rate100 : Float, Volty100 : Float, PutCall : Integer)

## Parâmetros:
- DaysLeft: Dias uteis até o vencimento da opção
- StrikePr: Preço do exercício da opção
- AssetPr: Preço da ação
- Rate100: Taxa de juros em %
- Volty100: Volatilidade em %
- PutCall: Indica se é uma put ou uma call
- optPut - Opção de venda
- optCall - Opção de compra

## Retorno:
Float

## Exemplos:
No  exemplo,  será  atribuido  à  variável  "opR",  a  variação,  considerando  9  dias  para  o vencimento,  11.00  como Strike, 12.92 como preço da ação, 0.2 para taxa de juros e 0.3 para volatilidade, aplicados para uma Call.

```
opR := Rho(9, 11.00, 12.92, 0.2, 0.3, optCall);
```

# Função Theta

## Descrição:
A função Theta retorna a variação do preço da opção com o tempo.

## Sintaxe:
Theta(DaysLeft : Integer, StrikePr : Float, AssetPr : Float, Rate100 : Float, Volty100 : Float, PutCall : Integer)

## Parâmetros:
- DaysLeft: Dias uteis até o vencimento da opção
- StrikePr: Preço do exercício da opção
- AssetPr: Preço da ação
- Rate100: Taxa de juros em %
- Volty100: Volatilidade em %
- PutCall: Indica se é uma put ou uma call
- optPut - Opção de venda
- optCall - Opção de compra

## Retorno:
Float

## Exemplos:
No  exemplo,  será  atribuido  à  variável  "opT",  a  variação,  considerando  9  dias  para  o vencimento, 17.22 como Strike, 11.94 como preço da ação, 0.1 para taxa de juros e  0.32 para volatilidade, aplicados sobre uma Put.

```
opT := Theta(9, 17.22, 17.94, 0.1, 0.32, optPut);
```

# Função Vega

## Descrição:
A função Vega retorna a variação da opção em relação à volatilidade.

## Sintaxe:
Vega(DaysLeft : Integer, StrikePr : Float, AssetPr : Float, Rate100 : Float, Volty100 : Float, PutCall : Integer)

## Parâmetros:
- DaysLeft: Dias uteis até o vencimento da opção
- StrikePr: Preço do exercício da opção
- AssetPr: Preço da ação Rate100: Taxa de juros em % Volty100: Volatilidade em % 
- PutCall: Indica se é uma put ou uma call 
- optPut - Opção de venda
- optCall - Opção de compra

## Retorno:
Float

## Exemplos:
No exemplo, será considerado 28 dias para o vencimento, 11.08 como Strike, 11.94 como preço da ação, 0.2 para taxa de juros e 0.36 para volatilidade, aplicados para uma Put.

```
opV := Vega(28, 11.08, 11.94, 0.2, 0.36, optPut);
```

# Screening

# Função Select

## Descrição:
A  função Select ,  apesar de estar disponível na linguagem, não possui recursos para utilização do usuário, sua implementação é específica para uso do sistema, a fim de habilitação do Screening.

## Sintaxe:
Select

## Parâmetros:
Sem parâmetros.

## Retorno:
Void: Sem retorno.

# Anexo

## Exemplos de funcionamento de estratégias
- 1 Nenhuma ordem será criada, já que existe um cancelamento de ordens.

```
Begin
  BuyAtMarket;
  CancelPendingOrders;
End; //Fim do fluxo de execução
```

- 2 Nenhuma ordem será criada, pois o ClosePosition vai cancelar a ordem BuyAtMarket.

```
Begin
  BuyAtMarket;
  ClosePosition;
End; //Fim do fluxo de execução
```

- 3 Nenhuma ordem será criada, pois o ReversePosition vai cancelar a ordem SellShortAtMarket.

```
Begin
  SellShortAtMarket;
  ReversePosition;
End; //Fim do fluxo de execução
```

- 4 Nenhuma ordem será criada, pois é realizada o agrupamento de ordens AtMarket que estão dentro do mesmo fluxo de execução.

```
Begin
  BuyAtMarket;
  SellShortAtMarket;
End; //Fim do fluxo de execução

```

- 5 O código abaixo não abre ordens covers. Pois ao passar pela linha BuyAtMarket não é gerada uma posição, pois não há execução da ordem. Desta maneira, a posição não é alterada e o SellToCover não será criado já que não há posição.

```
Begin
  If not HasPosition then
    begin
      BuyAtMarket;
      SellToCoverLimit(Close + 10 * MinPriceIncrement);
      SellToCoverStop(Close - 10 * MinPriceIncrement);
    end;
End; //Fim do fluxo de execução
```

Como alternativa, é aconselhável usar o código abaixo. Desta forma quando existir posição as ordens covers serão enviadas.

```
Begin
  If not HasPosition then
    begin
      BuyAtMarket;
    end
  else
    begin
      SellToCoverLimit(Close + 10 * MinPriceIncrement);
      SellToCoverStop(Close - 10 * MinPriceIncrement);
    end;
End; //Fim do fluxo de execução
```

- 6 O código abaixo irá atualizar o valor do nCandle cada vez que processar o fluxo de execução do candle. Logo, após a posição ser alterada, será feito o reprocessamento do candle, o valor do nCandle irá receber o valor do candle anterior e como tem posição o valor do nCandle não será alterado e se manterá igual ao valor do candle anterior.

```
Begin
  nCandle := nCandle[1];
  If not HasPosition then
    begin
      nCandle := CurrentBar;
      BuyAtMarket;
    end;
  if CurrentBar > nCandle + 5 then
    ClosePosition;
End; //Fim do fluxo de execução

```

Para zerar a posição após 5 candles, use o código abaixo como exemplo.

```
Begin
    if not hasposition then
    begin
      buyatmarket;
      nCandle[1] := 0;
    end
  else
    begin
      nCandle := nCandle[1] + 1;
      if nCandle > 5 then
      ClosePosition;
    end;
End; //Fim do fluxo de execução
```