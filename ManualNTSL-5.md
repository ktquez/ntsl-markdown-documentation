# Função AgressionVolBalance

## Descrição:
A função AgressionVolBalance retorna o valor do indicador TR - Volume de Agressão - Saldo.

## Sintaxe:
AgressionVolBalance

## Parâmetros:
Sem parâmetros.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "avb" irá receber o valor do indicador TR - Acúmulo de Agressão - Saldo.

```
avb := AgressionVolBalance;
```

# Função AgressionVolBuy

## Descrição:
A função AgressionVolBuy retorna o valor do indicador TR - Volume de Agressão - Compra.

## Sintaxe:
AgressionVolBuy

## Parâmetros:
Sem parâmetros.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "avb" irá receber o valor do indicador TR - Volume de Agressão - Compra.

```
avb := AgressionVolBuy;
```

# Função AgressionVolSell

## Descrição:
A função AgressionVolSell retorna o valor do indicador TR - Volume de Agressão - Venda.

## Sintaxe:
AgressionVolSell

## Parâmetros:
Sem parâmetros.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "avs" irá receber o valor do indicador AgressionVolSell.

```
avs := AgressionVolSell;
```

# Função ArmsEaseOfMov

## Descrição:
A função ArmsEaseOfMov retorna o valor do indicador Arms Ease of Movement, de acordo com o período e tipo de média desejados.

## Sintaxe:
ArmsEaseOfMov(Media : Integer, TipoMedia : Integer)

## Parâmetros:
- Media: Período da média utilizada no momento do cálculo do indicador.
- TipoMedia: Determina o tipo da média utilizada:
  - 0 - Aritmética
  - 1 - Exponencial
  - 2 - Welles Wilder
  - 3 - Ponderada

## Retorno:
Float

## Exemplos:
No exemplo, a variável "nATR" irá receber o valor do indicador Arms Ease of Movement, considerando 9 períodos para o tipo de média exponencial.

```
nATR := ArmsEaseOfMov(9, 1);
```

# Função AroonLin

## Descrição:
A função AroonLin retorna o valor do indicador Aroon Linha, de acordo com o período desejado.

## Sintaxe:
AroonLin(Periodo : Integer)|Linha : Integer|

## Parâmetros:
- Periodo: Período utilizado no momento do cálculo do indicador.
- Linha: Determina qual linha será obtida:
  - 0 - Aroon Up
  - 1 - Aroon Down

## Retorno:
Float

## Exemplos:
No exemplo, a variável "fAroon" irá receber o valor da linha "Aroon Down", considerando 9 períodos para o cálculo.

```
fAroon := AroonLin(9)|1|;
```

# Função AroonOsc

## Descrição:
A função AroonOsc retorna o valor do indicador Aroon Oscilador, de acordo com o período desejado.

## Sintaxe:
AroonOsc(Periodo : Integer)

## Parâmetros:
- Periodo: Período utilizado no momento do cálculo do indicador.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "fAroonOsc" irá receber o valor do indicador Aroon Oscilador, considerando 9 períodos para o cálculo.

```
fAroonOsc := AroonOsc(9);
```

# Função AutoFibonacci

## Descrição:
A função AutoFibonacci retorna o valor do indicador AutoFibonacci, de acordo com os parâmetros desejados.

## Sintaxe:
AutoFibonacci(Período : Integer, Níveis: Integer)|Nível : Integer|

## Parâmetros:
- Período: Período utilizado no momento do cálculo do indicador.
- Níveis: Determina quantos níveis serão gerados para o indicador, limitado em 8, e seguindo a ordem: (0%, 23.6%, 38.2%, 50%, 61.8%, 78.6%, 100%, 161.8%).

## Retorno:
Float

## Exemplos:
No exemplo, será atribuído à variável "aux" o retorno do indicador, considerando um período de 144 candles, e gerando oito níveis. Ao não especificar o nível desejado, o padrão será sempre retornar o nível 0 (0%).

```
aux := AutoFibonacci(144, 8);
```

Também é possível escolher qual o nível desejado passando como parâmetro no final da chamada. No exemplo, será atribuído à variável "aux" o retorno do indicador, considerando um período de 144 candles, gerando oito níveis e retornando o valor do nível 4 (50%).

```
aux := AutoFibonacci(144, 8)|3|;
```

# Função AutoFibonacciCustom

## Descrição:
A função AutoFibonacciCustom retorna o valor do indicador Auto Fibonacci, de acordo com os parâmetros desejados.

## Sintaxe:
AutoFibonacciCustom(Período : Integer, Valor do Nível: Float)

## Parâmetros:
- Período: Período utilizado no momento do cálculo do indicador.
- Valor do Nível: Determina qual o valor do nível utilizado para o cálculo do indicador.

## Retorno:
Float

## Exemplos:
No exemplo, será atribuído à variável "aux" o retorno do indicador, considerando um periodo de 144 candles, e o valor do nível em 75.5%.

```
aux := AutoFibonacciCustom(144, 75.5);
```

# Função AvgAgent

## Descrição:
A função AvgAgent retorna o preço médio filtrado por agente. Retorna os dados em tempo real, não executando em backtest.

*Exclusivo Profit Ultra

## Sintaxe:
AvgAgent(AgentID : Integer, Período : Integer)

## Parâmetros:
- AgentID: ID do agente na B3.
- Período: Determina qual tipo de cálculo do preço médio será obtido:
  - 0 - Retorna o preço médio diário, não importando o tempo gráfico onde está executando.
  - 1 - Retorna o preço médio candle a candle.

## Retorno:
Float

## Exemplos:
No exemplo, será atribuído à variável "aux" o retorno da função, a constante AgentID terá como filtro o agente 3 e o preço médio será diário.

```
const
  AgentID = 3;
var
  aux : Float;
begin
  aux := AvgAgent(AgentID, 0);
end;
```

# Função AvgAgrBuySell

## Descrição:
A função AvgAgrBuySell retorna o valor do indicador TR - Agressão Média - Compra e Venda, de acordo com os parâmetros desejados.

## Sintaxe:
AvgAgrBuySell(AlertaVariacoes : Integer, TipoVolume : Integer, TipoDesenho : Integer)|Linha : Integer|

## Parâmetros:
- AlertaVariacoes: Número de variações.
- TipoVolume: Determina qual tipo de volume será obtido:
  - 0 - Financeiro
  - 1 - Quantidade
- TipoDesenho: Relação entre compra e venda:
  - 0 - Compra e Venda
  - 1 - Compra/Venda
  - 2 - Compra-Venda

## Retorno:
Float

## Exemplos:
No exemplo, será atribuído à variável "aux" o retorno do indicador, considerando 3 variações, a quantidade e tipo de desenho.

```
aux := AvgAgrBuySell(3, 1, 0);
```

# Função AvgAgrTotal

## Descrição:
A função AvgAgrTotal retorna o valor do indicador TR - Agressão Média - Total, de acordo com os parâmetros específicos.

## Sintaxe:
AvgAgrTotal(AlertaVariacoes: Integer, TipoVolume : Integer, TipoDesenho : Integer)|Linha : Integer|

## Parâmetros:
- AlertaVariacoes: Número de variações.
- TipoVolume: Determina qual tipo de volume será obtido:
  - 0 - Financeiro
  - 1 - Quantidade
- TipoDesenho: Relação entre compra e venda:
  - 0 - Compra e Venda
  - 1 - Compra/Venda
  - 2 - Compra-Venda
- Linha: Determina qual linha será obtida:
  - 0 - Volume indicador
  - 1 - Avaliar

## Retorno:
Float

## Exemplos:
No exemplo, a variável "n" irá receber o valor da função AvgAgrTotal.

```
n := AvgAgrTotal(3, 1, 0);
```

# Função AvgSeparation

## Descrição:
A função AvgSeparation retorna o valor do indicador Afastamento Médio, de acordo com o período e tipo de média desejados.

## Sintaxe:
AvgSeparation(Periodo : Integer, TipoMedia : Integer)

## Parâmetros:
- Periodo: Período utilizado no momento do cálculo do indicador.
- TipoMedia: Determina qual média será considerada:
  - 0 - Aritmética
  - 1 - Exponencial
  - 2 - Welles Wilder
  - 3 - Ponderada

## Retorno:
Float

## Exemplos:
No exemplo, a variável "avgSep" irá receber o valor do indicador Afastamento Médio, considerando 21 períodos e tipo exponencial para o cálculo.

```
avgSep := AvgSeparation(21, 1);
```

# Função AvgTrueRange

## Descrição:
A função AvgTrueRange retorna o valor do indicador True Range, de acordo com o período e tipo de média desejados.

## Sintaxe:
AvgTrueRange(Periodo : Integer, TipoMedia : Integer)

## Parâmetros:
- Periodo: Período utilizado no momento do cálculo do indicador.
- TipoMedia: Determina qual média será considerada:
  - 0 - Aritmética
  - 1 - Exponencial
  - 2 - Welles Wilder
  - 3 - Ponderada

## Retorno:
Float

## Exemplos:
No exemplo, a variável "nATR" irá receber o valor do indicador True Range, considerando 5 períodos, e tipo de média ponderada para o cálculo.

```
nATR := AvgTrueRange(5, 3);
```

# Função BalanceAgent

## Descrição:
A função BalanceAgent retorna o saldo financeiro filtrado por agente. Retorna os dados em tempo real, não executando em backtest.

*Exclusivo Profit Ultra

## Sintaxe:
BalanceAgent(AgentID : Integer, Período : Integer)

## Parâmetros:
- AgentID: ID do agente na B3.
- Período: Determina qual tipo de cálculo do saldo será obtido:
  - 0 - Retorna o saldo diário, não importando o tempo gráfico onde está executando.
  - 1 - Retorna o saldo candle a candle.

## Retorno:
Float

## Exemplos:
No exemplo, será atribuído à variável "aux" o retorno da função, a constante AgentID terá como filtro o agente 3 e o saldo será diário.

```
const
  AgentID = 3;
var
  aux : Float;
begin
  aux := BalanceAgent(AgentID, 0);
end;
```

# Função BalanceOfPower

## Descrição:
A função BalanceOfPower retorna o valor do indicador Balança do Poder, de acordo com o período desejado.

## Sintaxe:
BalanceOfPower(Media : Integer, TipoMedia : Integer)

## Parâmetros:
- Media: Período utilizado no momento do cálculo do indicador.
- TipoMedia: Determina o tipo da média utilizada:
  - 0 - Aritmética
  - 1 - Exponencial
  - 2 - Welles Wilder
  - 3 - Ponderada

## Retorno:
Float

## Exemplos:
No exemplo, a variável "nBalance" irá receber o valor do indicador Balança do Poder, considerando 14 períodos, e o tipo de média exponencial para o cálculo.

```
nBalance := BalanceOfPower(14,1);
```

# Função BearPower

## Descrição:
A função BearPower retorna o valor do indicador Bear Power, conforme o período desejado.

## Sintaxe:
BearPower(Periodo : Integer)

## Parâmetros:
- Periodo: Período utilizado no momento do cálculo do indicador.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "nBear" irá receber o dado do indicador Bear Power, considerando 13 períodos.

```
nBear := BearPower(13);
```

# Função BollingerBands

## Descrição:
A função BollingerBands retorna o valor do indicador Bandas de Bollinger, de acordo com o período e tipo de média desejados.

## Sintaxe:
BollingerBands(Desvio : Float, Media : Integer, TipoMedia : Integer)|Linha : Integer|

## Parâmetros:
- Desvio: Desvio utilizado no momento do cálculo do indicador.
- Media: Período da média utilizada no momento do cálculo do indicador.
- TipoMedia: Determina o tipo da média utilizada:
  - 0 - Aritmética
  - 1 - Exponencial
  - 2 - Welles Wilder
  - 3 - Ponderada
- Linha: Determina qual linha será obtida:
  - 0 - Superior
  - 1 - Inferior

## Retorno:
Float

## Exemplos:
No exemplo, a variável "fBool" irá receber o valor da linha inferior do indicador Bandas de Bollinger, considerando 2.0 como desvio, 20 períodos e tipo de média aritmética.

```
fBool := BollingerBands(2.0, 20, 0)|1|;
```

# Função BollingerBandW

## Descrição:
A função BollingerBandW retorna o valor do indicador Bollinger Band Width, de acordo com o período e tipo de média desejados.

## Sintaxe:
BollingerBandW(Desvio : Float, Media : Integer, TipoMedia : Integer)

## Parâmetros:
- Desvio: Desvio utilizado no momento do cálculo do indicador.
- Media: Período da média utilizada no momento do cálculo do indicador.
- TipoMedia: Determina o tipo da média utilizada:
  - 0 - Aritmética
  - 1 - Exponencial
  - 2 - Welles Wilder
  - 3 - Ponderada

## Retorno:
Float

## Exemplos:
No exemplo, a variável "fBoolinBW" irá receber o valor do indicador Bollinger Band Width, considerando 2.0 como desvio, 20 períodos e tipo de média exponencial.

```
fBoolinBW := BollingerBandW(2.0,20,1);
```

# Função BollingerBPerc

## Descrição:
A função BollingerBPerc retorna o valor do indicador Bollinger b%, de acordo com o período e tipo de média desejados.

## Sintaxe:
BollingerBPerc(Desvio : Float, Media : Integer, TipoMedia : Integer)

## Parâmetros:
- Desvio: Desvio utilizado no momento do cálculo do indicador.
- Media: Período da média utilizada no momento do cálculo do indicador.
- TipoMedia: Determina o tipo da média utilizada:
  - 0 - Aritmética
  - 1 - Exponencial
  - 2 - Welles Wilder
  - 3 - Ponderada

## Retorno:
Float

## Exemplos:
No exemplo, a variável "fBool" irá receber o valor do indicador Bollinger Band Width, considerando 2.0 como desvio, 20 períodos e tipo de média Ponderada.

```
fBool := BollingerBPerc(2.0,20,3);
```

# Função BullPower

## Descrição:
A função BullPower retorna o valor do indicador Bull Power, de acordo com o período e tipo de média desejados.

## Sintaxe:
BullPower(Periodo : Integer, PeriodoMedia : Integer, TipoMedia : Integer)

## Parâmetros:
- Periodo: Período utilizado no momento do cálculo do indicador
- PeriodoMedia: Período utilizado no momento do cálculo da média utilizada no indicador.
- TipoMedia: Determina o tipo da média utilizada:
  - 0 - Aritmética
  - 1 - Exponencial
  - 2 - Welles Wilder
  - 3 - Ponderada

## Retorno:
Float

## Exemplos:
No exemplo, a variável "nBull" irá receber o valor do indicador Bull Power, considerando 21 períodos, e 9 períodos para a média aritmética.

```
nBull := BullPower(21,9,0)
```

# Função CCI

## Descrição:
A função CCI retorna o valor do indicador CCI, de acordo com o período desejado.

## Sintaxe:
CCI(Periodo : Integer)

## Parâmetros:
- Periodo: Período utilizado no momento do cálculo do indicador.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "nCCI" irá receber o valor do indicador CCI, considerando 14 períodos para o cálculo.

```
nCCI := CCI(14);
```

# Função ChaikinMoneyFlow

## Descrição:
A função ChaikinMoneyFlow retorna o valor do indicador Chaikin Money Flow, de acordo com o período desejado.

## Sintaxe:
ChaikinMoneyFlow(Periodo : Integer)

## Parâmetros:
- Periodo: Período utilizado no momento do cálculo do indicador.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "nCMF" irá receber o valor do indicador Chaikin Money Flow, considerando 21 período para o cálculo.

```
nCMF := ChaikinMoneyFlow(21);
```

# Função ChaikinOsc

## Descrição:
A função ChaikinOsc retorna o valor do indicador Oscilador Chaikin, de acordo com as médias desejadas.

## Sintaxe:
ChaikinOsc(MediaLonga : Integer, MediaCurta : Integer)

## Parâmetros:
- MediaLonga: Determina o período da Média Longa para formação do cálculo.
- MediaCurta: Determina o período da Média Curta.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "nCo" irá receber o valor do indicador Oscilador Chaikin, considerando 10 períodos para a média longa, e 3 para a curta.

```
nCo := ChaikinOsc(10, 3);
```

# Função ChainSetup

## Descrição:
A função ChainSetup retorna o valor do indicador ChainSetup.

## Sintaxe:
ChainSetup

## Parâmetros:
Sem parâmetros.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "cs" irá receber o dado do indicador ChainSetup.

```
cs := ChainSetup;
```

# Função CohenPriceWave

## Descrição:
A função CohenPriceWave retorna o dado do indicador Cohen - Price Wave (desenvolvido por Rodrigo Cohen e equipe).

## Sintaxe:
CohenPriceWave(Ticks : Integer)|Histograma : Integer|

## Parâmetros:
- Ticks: Níveis de preço.
- Histograma: Determina o dado do histograma:
  - 1 - Compra
  - 2 - Venda

## Retorno:
Float

## Exemplos:
No exemplo, será atribuído à variável "cPriceWave", o retorno do indicador, considerando 15 ticks para o cálculo.

```
cPriceWave := CohenPriceWave(15)|1|;
```

# Função CohenWeisWave

## Descrição:
A função CohenWeisWave retorna o dado do indicador Cohen - Weis Wave (desenvolvido por Rodrigo Cohen e equipe).

## Sintaxe:
CohenWeisWave(Ticks : Integer)

## Parâmetros:
- Ticks: Relacionado ao valor de entrada do indicador.

## Retorno:
Float

## Exemplos:
No exemplo, será atribuído à variável "cWeisWave", o retorno do indicador, considerando 15 ticks para o cálculo.

```
cWeisWave:= CohenWeisWave(15);
```

# Função ContadorDeCandle

## Descrição:
A função ContadorDeCandle contabiliza e sinaliza de forma numérica e organizada no gráfico o número de cada candle.

## Sintaxe:
ContadorDeCandle

## Parâmetros:
Sem parâmetros

## Retorno:
Float

## Exemplos:
No exemplo, será atribuído à variável 'nCandle' o número do candle atual.

```
nCandle:= ContadorDeCandle;
```

# Função DarvasBox

## Descrição:
A função DarvasBox retorna o valor do indicador Darvas Box.

## Sintaxe:
DarvasBox|Linha : Integer|

## Parâmetros:
- Linha: Determina qual dado(Compra ou Venda) será obtido:
  - 0 - Compra
  - 1 - Venda

## Retorno:
Float

## Exemplos:
No exemplo, a variável "nDB" irá receber os valores(Dado: Venda) do indicador Darvas Box.

```
nDB := DarvasBox|1|;
```

# Função DecisionPoints

## Descrição:
A função DecisionPoints retorna o valor do indicador Pontos de Decisão.

## Sintaxe:
DecisionPoints(Tipo : Integer, Linha : Integer)

## Parâmetros:
- Tipo: Determina o tipo: Preço, Volume, Faixas de Volume e Variação:
  - 0 - Tipo Preço:
    - Linha: Dado da série que será obtido
      - 0 - Abertura
      - 1 - Máxima
      - 2 - Mínima
      - 3 - Fechamento
      - 4 - Ajuste
  - 1 - Tipo Volume:
    - Linha: Três maiores volumes dos períodos
      - 0 - Dado volume
      - 1 - Dado volume
      - 2 - Dado volume
  - 2 - Tipo Faixas de Volume:
    - Linha:
      - 0 - Retorna o dado específico ao tipo
  - 3 - Tipo Variação:
    - Linha:
      - 0 - Dado variação linha inferior (-2%)
      - 1 - Dado variação linha inferior (-1%)
      - 2 - Dado variação linha superior (1%)
      - 3 - Dado variação linha superior (2%)

## Retorno:
Float

## Exemplos:
No exemplo, a variável "DecisionP" irá receber o dado referente à máxima.

```
DecisionP := DecisionPoints(0, 1);
```

# Função DiDiIndex

## Descrição:
A função DiDiIndex retorna o valor do indicador Didi Index, de acordo com o período e tipos de médias desejados.

## Sintaxe:
DiDiIndex(MediaReferencia : Integer, TipoMediaReferencia : Integer, Media1 : Integer, TipoMedia1 : Integer, Media2 : Integer, TipoMedia2 : Integer)|Linha : Integer|

## Parâmetros:
- MediaReferencia: Parâmetro para o período utilizado no cálculo da média de referência do indicador.
- TipoMediaReferencia: Determina qual média será considerada:
  - 0 - Aritmética
  - 1 - Exponencial
  - 2 - Welles Wilder
  - 3 - Ponderada
- Media1: Período utilizado no cálculo da média1 do indicador.
- TipoMedia1: Determina qual média será considerada:
  - 0 - Aritmética
  - 1 - Exponencial
  - 2 - Welles Wilder
  - 3 - Ponderada
- Media2: Período utilizado no cálculo da média1 do indicador.
- TipoMedia2: Determina qual média será considerada:
  - 0 - Aritmética
  - 1 - Exponencial
  - 2 - Welles Wilder
  - 3 - Ponderada
- Linha: Determina qual linha será obtida:
  - 0 - Linha
  - 1 - Linha 2

## Retorno:
Float

## Exemplos:
No exemplo, a variável "fdIndex" irá receber o valor da "linha 2", considerando 8(Média de Referência), 3(Média 1) e 20(Média 1) períodos, aplicando o tipo de média aritmética para o cálculo.

```
fdIndex := DidiIndex(8,0,3,0,20,0)|1|;
```

# Função DiPDiM

## Descrição:
A função DiPDiM retorna o valor do indicador DI+/DI, de acordo com o período desejado.

## Sintaxe:
DiPDiM(Periodo : Integer)|Linha : Integer|

## Parâmetros:
- Periodo: Período utilizado no momento do cálculo do indicador.
- Linha: Determina qual linha será obtida:
  - 0 - DI+
  - 1 - DI-

## Retorno:
Float

## Exemplos:
No exemplo, a variável "aux" irá receber o valor DI- do indicador DI+/DI-, considerando 14 período para o cálculo.

```
aux := DiPDiM(14)|1|;
```

# Função DivergenceDetector

## Descrição:
A função DivergenceDetector retorna os pontos de alta ou baixa (PH ou PL) do ativo de acordo com o número de pivôs à esquerda e direita definidos nos parâmetros ou retorna a quantidade de indicadores considerados naquele candle relacionados aos indicadores considerados na divergência. Esse indicador retorna os pontos identificados pelo indicador Detector de Divergências.

## Sintaxe:
DivergenceDetector(LeftPivot : Integer, RightPivot : Integer, MACD : Boolean = 0, MACDHistogram : Boolean = 0, RSI : Boolean = 0, Stochastic: Boolean = 0, CCI: Boolean = 0, Momentum: Boolean = 0, OBV: Boolean = 0, Diosc: Boolean = 0, VWmacd: Boolean = 0, ChaikinMoneyFlow: Boolean = 0, MoneyFlowIndex: Boolean = 0)|Index : Integer|

## Parâmetros:
- LeftPivot: Número de candles à considerar como pivô à esquerda (apenas influencia cálculo de PH e PL)
- RightPivot: Número de candles à considerar como pivô à direita (apenas influencia cálculo de PH e PL)
- MACD: Parâmetro opcional que indica se deve considerar o indicador MACD para cálculo de divergência dos indicadores
- MACDHistogram: Parâmetro opcional que indica se deve considerar o indicador MACD Histograma para cálculo de divergência dos indicadores
- RSI: Parâmetro opcional que indica se deve considerar o indicador RSI para cálculo de divergência dos indicadores
- Stochastic: Parâmetro opcional que indica se deve considerar o indicador Estocástico para cálculo de divergência dos indicadores
- CCI: Parâmetro opcional que indica se deve considerar o indicador CCI para cálculo de divergência dos indicadores
- Momentum: Parâmetro opcional que indica se deve considerar o indicador Momentum para cálculo de divergência dos indicadores
- OBV: Parâmetro opcional que indica se deve considerar o indicador OBV para cálculo de divergência dos indicadores
- Diosc: Parâmetro opcional que indica se deve considerar o indicador Diosc para cálculo de divergência dos indicadores
- VWmacd: Parâmetro opcional que indica se deve considerar o indicador VWmacd para cálculo de divergência dos indicadores
- ChaikinMoneyFlow: Parâmetro opcional que indica se deve considerar o indicador Chaikin Money Flow para cálculo de divergência dos indicadores
- MoneyFlowIndex: Parâmetro opcional que indica se deve considerar o indicador MoneyFlowIndex para cálculo de divergência dos indicadores
- Index: Determina qual tipo de cálculo será obtido:
  - 0 - Retorna os valores de PH e PL para o ativo, onde os resultados são da seguinte forma:
    - -1 caso o candle analisado seja PL
    - 0 caso não seja nem PL nem PH
    - 1 caso o candle analisado seja PH
  - 1 - Retorna os valores relacionados à divergência dos indicadores definidos da seguinte forma:
    - Soma a quantidade de indicadores que indicam divergência naquele candle e retorna o valor positivo caso seja um candle positivo ou negativo caso seja um candle negativo

## Retorno:
Float

## Exemplos:
No exemplo, a variável x irá receber o valor relacionado a PH/PL do candle a ser analisado considerando os valores passados para o LeftPivot e RightPivot (note que esse valor é independente dos indicadores passados opcionalmente por parâmetro)

```
x := DivergenceDetector(5, 5)|0|;
```

No exemplo abaixo, a variável x irá receber o valor relacionado à soma dos indicadores que detectaram alguma divergência, ou nenhuma, no candle analisado. Nesse exemplo abaixo, estamos considerando apenas os indicadores MACD MACD Histograma, e RSI para o cálculo.

```
x := DivergenceDetector(5, 5, True, True, True)|1|;
```

# Função DonchianCH

## Descrição:
A função DonchianCh retorna o valor do indicador Canal Donchian, de acordo com o período desejado.

## Sintaxe:
DonchianCh(Periodo : Integer)|Linha : Integer|

## Parâmetros:
- Periodo: Período utilizado no momento do cálculo do indicador.
- Linha: Determina qual linha será obtida:
  - 0 - Média
  - 1 - Superior
  - 2 - Inferior

## Retorno:
Float

## Exemplos:
No exemplo, a variável "nDC" irá receber o valor da linha inferior do indicador Canal Donchian, considerando 20 períodos para o cálculo.

```
nDC := DonchianCh(20)|2|;
```

# Função DTOscillator

## Descrição:
A função DTOscillator retorna o valor do indicador DT Oscillator, conforme os parâmetros desejados.

## Sintaxe:
DTOscillator(PeriodoEstocastico : Integer, PeriodoSK : Integer, TipoSK : Integer, PeriodoSD : Integer, TipoSD : Integer)|Linha : Integer|

## Parâmetros:
- PeriodoEstocastico: Período utilizado no momento do cálculo do indicador.
- PeriodoSK: Período referente ao parâmetro "Período SK".
- TipoSK: Determina qual média será considerada:
  - 0 - Aritmética
  - 1 - Exponencial
  - 2 - Welles Wilder
  - 3 - Ponderada
- PeriodoSD: Período referente ao parâmetro "Período SD".
- TipoSD: Determina qual média será considerada:
  - 0 - Aritmética
  - 1 - Exponencial
  - 2 - Welles Wilder
  - 3 - Ponderada
- Linha: Determina qual linha será obtida:
  - 0 - Linha 1
  - 1 - Linha 2

## Retorno:
Float

## Exemplos:
No exemplo, a variável "dtOsc" irá receber o valor do indicador DT Oscillator, considerando 12(PeriodoEstocastico), 8(PeriodoSK), 5(PeriodoSD) períodos, e tipo aritmétia para o cálculo.

```
dtOsc := DTOscillator(12, 8, 0, 5, 0)|1|;
```

# Função Envelope

## Descrição:
A função Envelope retorna o valor do indicador Envelope, de acordo com o período e média desejados.

## Sintaxe:
Envelope(Percentual : Float, PeriodoMedia : Integer, TipoMedia : Integer)|Linha : Integer|

## Parâmetros:
- Percentual: Percentual utilizado no momento do cálculo do indicador.
- PeriodoMedia: Período utilizado para o cálculo da média.
- TipoMedia: Determina qual média será considerada:
  - 0 - Aritmética
  - 1 - Exponencial
  - 2 - Welles Wilder
  - 3 - Ponderada
- Linha: Determina qual linha será obtida:
  - 0 - Ponto médio
  - 1 - Superior
  - 2 - Inferior

## Retorno:
Float

## Exemplos:
No exemplo, será atribuído à variável "nEnv" o dado da linha superior do indicador Envelope, considerando 5.0 como percentual, 20 períodos e tipo de média aritmética para o cálculo.

```
nEnv := Envelope(5.0, 20, 0)|1|;
```

# Função Euroinvest

## Descrição:
A função Euroinvest retorna o valor do indicador Euroinvest, conforme os parâmetros determinados.

## Sintaxe:
Euroinvest(Risco: Integer, ModoCalculo : Integer, Periodo : Integer, Desvio : Float, UsarVWAP : Boolean, UsarAtr : Boolean)

## Parâmetros:
- Risco: Determina o tipo de perfil:
  - 0 - Zero
  - 1 - Um
  - 2 - Dois
  - 3 - Três
- ModoCalculo: Tipo de média:
  - 0 - Aritmética
  - 1 - Exponencial
  - 2 - Welles Wilder
  - 3 - Ponderada
- Periodo: Período considerado para o cálculo da média.
- Desvio: Desvio da média.
- UsarVWAP: Determina se o VWAP será utiizado.
- UsarAtr: Determina a habilitação do StopATR.

## Retorno:
Float

## Exemplos:
No exemplo, será atribuído à variável "fEuro" o retorno da função, considerando o perfil Zero, tipo de média aritmética, 21 períodos, com 2 de desvio, onde o VWAP e StopAtr estão habilitados.

```
fEuro := Euroinvest(0, 0, 21, 2.0, True, True);
```

# Função FastStochastic

## Descrição:
A função FastStochastic retorna o valor do indicador Estocástico Rápido, de acordo com o período desejado.

Observação: Os parâmetros PeriodoMedia e TipoMedia são opcionais, caso não sejam determinados, serão utilizados os valores 14 e 1 respectivamente.

## Sintaxe:
FastStochastic(Periodo : Integer, PeriodoMedia : Integer, TipoMedia : Integer)

## Parâmetros:
- Período: Período utilizado no momento do cálculo do indicador.
- PeriodoMedia: Período utilizado no momento do cálculo da média.
- TipoMedia: Tipo da média a ser calculada pelo indicador:
  - 0 - Aritmética
  - 1 - Exponencial
  - 2 - Welles Wilder
  - 3 - Ponderada

## Retorno:
Float

## Exemplos:
No exemplo, a variável "nEstRap" irá receber o valor do indicador Estocástico Rápido, considerando 14 períodos para o cálculo.

```
nEstRap := FastStochastic(14);
```

# Função FinancialVol

## Descrição:
A função FinancialVol retorna o valor do indicador Volume Financeiro, podendo-se incluir ou desconsiderar os dados: "volume projetado" e "leilão e trades diretos".

Observação: O parâmetro Agressores só será considerado para o cálculo do indicador caso o seja assinado o Opcional 'Plugin Tape Reading'. Caso não possua o opcional o indicador será sempre calculado como False, independente do que for inserido no campo.

## Sintaxe:
FinancialVol(VolumeProjetado : Boolean, Agressores : Boolean)

## Parâmetros:
- VolumeProjetado: Determina se o volume irá considerar o dado projetado.
- Agressores: Determina se o volume irá desconsiderar o leilão e trades diretos.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "vFinanceiro" irá receber o valor do indicador Volume Financeiro, desconsiderando os dados de "volume projetado" e "leilão e trades diretos".

```
vFinanceiro := FinancialVol(False, False);
```

# Função ForceIndex

## Descrição:
A função ForceIndex retorna o valor do indicador Force Index, de acordo com o período e tipo de média desejados.

## Sintaxe:
ForceIndex(Periodo : Integer, TipoMedia : Integer)

## Parâmetros:
- Periodo: Período utilizado no momento do cálculo do indicador.
- TipoMedia: Determina qual média será considerada:
  - 0 - Aritmética
  - 1 - Exponencial
  - 2 - Welles Wilder
  - 3 - Ponderada

## Retorno:
Float

## Exemplos:
No exemplo, será atribuído à variável "nForce" o valor do indicador Force Index, considerando 13 períodos e tipo de média exponencial.

```
nForce := ForceIndex(13, 1);
```

# Função FrassonATR

## Descrição:
A função FrassonATR retorna o valor do indicador Frasson ATR, de acordo com o fator e períodos desejados.

## Sintaxe:
FrassonATR(Fator : Float, PeriodoMaxMin : Integer, PeriodoATR : Integer)|Linha : Integer|

## Parâmetros:
- Fator: Fator de multiplicação do ATR utilizado no momento do cálculo do indicador.
- PeriodoMaxMin: Determina o período de Máxima de Miníma.
- PeriodoATR: Determina o período do cálculo do ATR.
- Linha: Determina qual linha será obtida:
  - 0 - Superior
  - 1 - Inferior

## Retorno:
Float

## Exemplos:
No exemplo, a variável "nFrasson" irá receber o valor da linha inferior do indicador Frasson ATR, considerando 0,03(Fator), 15(Período Máxima/Mínima) e 50(Período ATR) para o cálculo.

```
nFrasson := FrassonATR(0.03, 15, 50)|1|;
```

# Função FrassonVH

## Descrição:
A função FrassonVH retorna o valor do indicador Frasson VH, de acordo com o fator e períodos desejados.

## Sintaxe:
FrassonVH(Fator : Float, PeriodoMaxMin : Integer, PeriodoVH : Integer)|Linha : Integer|

## Parâmetros:
- Fator: Fator de multiplicação do ATR utilizado no momento do cálculo do indicador.
- PeriodoMaxMin: Determina o período de Máxima de Miníma.
- PeriodoVH: Determina o período do cálculo do VH.
- Linha: Determina qual linha será obtida:
  - 0 - Superior
  - 1 - Inferior

## Retorno:
Float

## Exemplos:
No exemplo, a variável "nFrasson" irá receber o valor da linha superior do indicador Frasson VH, considerando 0,03(Fator), 15(Período Máxima/Mínima) e 50(Período VH) para o cálculo.

```
nFrasson := FrassonVH(0.03, 15, 50);
```

# Função FullStochastic

## Descrição:
A função FullStochastic retorna o valor do indicador Estocástico Pleno, de acordo com o período desejado.

## Sintaxe:
FullStochastic(Periodo : Integer)

## Parâmetros:
- Periodo: Período utilizado no momento do cálculo do indicador.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "nPlen" irá receber o valor do indicador Estocástico Pleno, considerando 14 períodos para o cálculo.

```
nPlen := FullStochastic(14);
```

# Função FuraChao

## Descrição:
A função FuraChao retorna o valor do indicador Fura-Chão, de acordo com o coeficiente e deslocamento desejados.

## Sintaxe:
FuraChao(Coeficiente : Float, Deslocamento : Integer)

## Parâmetros:
- Coeficiente: Coeficiente utilizado no momento do cálculo do indicador.
- Deslocamento: Determina quantos períodos anteriores serão utilizados como base no indicador.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "fChao" irá receber o valor do indicador Fura-Chão, considerando 0.14(Coeficiente) e 1 período(Deslocamento) para o cálculo.

```
fChao := FuraChao(0.14, 1);
```

# Função FuraTeto

## Descrição:
A função FuraTeto retorna o valor do indicador Fura-Teto, de acordo com o coeficiente e deslocamento desejados.

## Sintaxe:
FuraTeto(Coeficiente : Float, Deslocamento : Integer)

## Parâmetros:
- Coeficiente: Coeficiente utilizado no momento do cálculo do indicador.
- Deslocamento: Determina quantos períodos anteriores serão utilizados como base no indicador.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "fTeto" irá receber o valor do indicador Fura-Teto, considerando 0.14(Coeficiente) e 1 período(Deslocamento) para o cálculo.

```
fTeto := FuraTeto(0.14, 1);
```

# Função HeikinAshi

## Descrição:
A função HeikinAshi retorna o valor do indicador Heikin Ashi, de acordo com o período e tipo de média desejados.

## Sintaxe:
HeikinAshi(Media : Integer, TipoMedia : Integer)|Dado : Integer|

## Parâmetros:
- Media: Media utilizado no momento do cálculo do indicador.
- TipoMedia: Determina qual média será considerada:
  - 0 - Aritmética
  - 1 - Exponencial
  - 2 - Welles Wilder
  - 3 - Ponderada
- Linha: Determina qual dado será obtido:
  - 0 - Abertura
  - 1 - Fechamento
  - 2 - Máxima
  - 3 - Mínima

## Retorno:
Float

## Exemplos:
No exemplo, a variável "HeikinAshi" irá receber o valor de fechamento do indicador Heikin Ashi, considerando 1(Período) e 0(Aritmética) para o cálculo.

```
nHA := HeikinAshi(1, 0)|1|;
```

# Função HiLoActivator

## Descrição:
A função HiloActivator retorna o valor do indicador HiLo Activator, de acordo com o período desejado.

## Sintaxe:
HiloActivator(Periodo : Integer)|Linha : Integer|

## Parâmetros:
- Periodo: Período utilizado no momento do cálculo do indicador.
- Linha: Determina qual linha será obtida:
  - 0 - Valor Indicador
  - 1 - Tendência
    - Retorno para identificação da tendência:
      - 0 - Baixa
      - 1 - Alta

## Retorno:
Float

## Exemplos:
No exemplo, a variável "nHiLo" irá receber o valor do indicador HiLo Activator, considerando 3 períodos para o cálculo.

```
nHiLo := HiloActivator(3);
```

# Função HistVolatility

## Descrição:
A função HistVolatility retorna o valor do indicador Volatilidade Histórica, de acordo com o período e tipo de média desejados.

## Sintaxe:
HistVolatility(Periodo : Integer, TipoMedia : Integer)

## Parâmetros:
- Periodo: Período utilizado no momento do cálculo do indicador.
- TipoMedia: Determina qual média será considerada:
  - 0 - Aritmética
  - 1 - Exponencial
  - 2 - Welles Wilder

## Retorno:
Float

## Exemplos:
No exemplo, a variável "nVH" irá receber o valor do indicador Volatilidade Histórica, considerando 22(Períodos) e tipo de média exponencial.

```
nVH := HistVolatility(22, 2);
```

# Função HSI

## Descrição:
A função HSI retorna o dado do indicador IFH Índice de Força Harmônico (HSI), conforme o período desejado.

## Sintaxe:
HSI

## Parâmetros:
Sem parâmetros.

## Retorno:
Float

## Exemplos:
No exemplo, será atribuído à variável "vHSI" o retorno da função.

```
vHSI := HSi();
```

# Função HullMovingAverage

## Descrição:
A função HullMovingAverage retorna o valor do indicador Hull Moving Average, de acordo com o período desejado.

## Sintaxe:
HullMovingAverage(Periodo : Integer)

## Parâmetros:
- Periodo: Período utilizado no momento do cálculo do indicador.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "vHMV" irá receber o valor do indicador Hull Moving Average, considerando 8 períodos para o cálculo.

```
vHMV := HullMovingAverage(8);
```

# Função IchimokuCloud

## Descrição:
A função IchimokuCloud retorna o valor do indicador Ichimoku Cloud, de acordo com os parâmetros desejados.

## Sintaxe:
IchimokuCloud(TenkanSen : Integer, KijunSen : Integer, SenkouSpanB : Integer)|Linha : Integer|

## Parâmetros:
- TenkanSen: Utilizado no momento do cálculo do indicador.
- KijunSen: Utilizado no momento do cálculo do indicador.
- SenkouSpanB: Utilizado no momento do cálculo do indicador.
- Linha: Determina qual linha será obtida:
  - 0 - Tenkan-Sen
  - 1 - Kijun-Sen
  - 2 - Chikou Span
  - 3 - Senkou Span A
  - 4 - Senkou Span B

## Retorno:
Float

## Exemplos:
No exemplo, a variável "nIchimoku" irá receber o valor da linha "Senkou Span B" do indicador Ichimoku Cloud, considerando 9(Tenkan-Sen), 26(Kijun-Sen) e 52(Senkou Span B) para o cálculo.

```
nIchimoku := IchimokuCloud(9, 26, 52)|4|;
```

# Função ImpliedVolatility

## Descrição:
A função ImpliedVolatility retorna o valor do indicador Volatilidade Implícita, utilizado para calcular Volatilidade Implícita de derivativos (opções), de acordo com o período desejado.

## Sintaxe:
ImpliedVolatility(ModeloTeorico : Boolean, TipoOpcao : Boolean)

## Parâmetros:
- ModeloTeorico: Determina o modelo para o cálculo:
  - True - Black & Scholes
  - False - Binomial
- TipoOpcao: Determina o tipo da opção:
  - True - Americana
  - False - Européia

## Retorno:
Float

## Exemplos:
No exemplo, a variável "nIV" irá receber o valor do indicador Volatilidade Implícita, utilizando o modelo Black & Scholes.

```
nIV := ImpliedVolatility(True, False);
```

# Função KeltnerCH

## Descrição:
A função KeltnerCH retorna o valor do indicador Keltner Channels, de acordo com o período e tipo de média desejados.

## Sintaxe:
KeltnerCH(Desvio : Float, Periodo : Integer, TipoMedia : Integer)|Linha : Integer|

## Parâmetros:
- Desvio: Desvio utilizado no momento do cálculo do indicador.
- Periodo: Período utilizado para o cálculo do indicador.
- TipoMedia: Determina qual média será considerada:
  - 0 - Aritmética
  - 1 - Exponencial
  - 2 - Welles Wilder
  - 3 - Ponderada
- Linha: Determina qual linha será obtida:
  - 0 - Superior
  - 1 - Inferior

## Retorno:
Float

## Exemplos:
No exemplo, será atribuído à variável "nCh" o valor da linha inferior do indicador Keltner Channels, considerando 2.0(Desvio), 20(Períodos) e tipo de média exponencial.

```
nCh := KeltnerCH(2.0, 20, 1)|1|;
``` 