# Função ELDate_Consol

## Descrição:
A função ELDate_Consol possui como finalidade converter uma data YYYYMMDD em EasyLanguage format(YYYMMDD).

## Sintaxe:
ELDate_Consol(Data : Integer)

## Parâmetros:
- Data: Data no formato YYYYMMDD.

## Retorno:
Integer

## Exemplos:
No exemplo, será atribuído à variável "nData" a data de 2018/11/13 no formato: 1181113.

```
nData := ELDate_Consol(20181113);
```

# Função FindBar

## Descrição:
A função FindBar retorna o índice de uma barra através de uma data e hora, onde a contagem é iniciada a partir do candle atual(índice 0).

Observações:

Representação de datas: 1AnoMêsDia.

Datas são representadas pelo tipo de dado "Integer", no formato:

Representação de horas: Horas são representadas pelo tipo de dado "Integer", no formato: HHMM.

## Sintaxe:
FindBar(Data : Integer, Hora : Integer)

## Parâmetros:
- Data: Data do candle.
- Hora: Hora do candle específico.

## Retorno:
Integer

## Exemplos:
No exemplo, a variável "n" irá receber o índice do candle relacionado com o horário 11h10 do dia atual.

```
n := FindBar(CurrentDate, 1110);
```

# Função Friday

## Descrição:
A função Friday retorna o número 5, representando o dia da semana: sexta-feira.

## Sintaxe:
Friday

## Parâmetros:
Sem parâmetros.

## Retorno:
Integer

## Exemplos:
No exemplo, a variável "nDia" irá receber número 5, referente ao dia específico da semana.

```
nDia := Friday;
```

# Função HighestVolume

## Descrição:
A função HighestVolume Retorna o maior volume de acordo com o tipo.

* Disponível apenas para clientes Profit Ultra. Os dados do Volume Profile não fornecem um histórico de dados extenso, fazendo com que o backtest de estratégias utilizando essa função seja limitado.

## Sintaxe:
HighestVolume (Interval : Integer; Offset : Integer = 1; Type : Integer = 0; Standard : Boolean = True; Auction : Boolean = True; Cross : Boolean = True)|Rank : Integer|:

## Parâmetros:
- Interval: Intervalo de tempo utilizado para o cálculo do volume. Pode ser:
  - itDaily: Utiliza o intervalo diário. (No período Diário é apenas permitido Offset 1)
  - itMinute: Utiliza o intervalo em minutos.
- Offset: Determina a quantidade de períodos (dias ou minutos, dependendo do Interval) a partir do qual o cálculo será feito. Aceita valores entre 0 e 720. Um valor de 0 indica o período atual, enquanto valores maiores indicam períodos passados.
- Type: Define o tipo de volume a ser considerado no cálculo. Pode ser:
  - vtFinancial: Volume financeiro.
  - vtQuantity: Volume em quantidade de ações ou contratos.
  - vtTrade: Número de negócios realizados.
- Standard: Variável booleana que permite puxar os trades padrão. Valor padrão é True.
- Auction: Variável booleana que define se o volume de leilões será incluído no cálculo. Valor padrão é True.
- Cross: Variável booleana que indica se o volume de operações cruzadas (cross trades) será considerado. Valor padrão é True.
- Rank: Deve ser definido ao final da função entre barras verticais: |RANK|. O primeiro (0) será o maior volume da lista.

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será retornado o maior volume financeiro dos últimos 60 minutos.

```
HighestVolume(itMinute, 60, vtFinancial)|0|
```

# Função HighestVolumePrice

## Descrição:
A função HighestVolumePrice Retorna o preço do maior volume de acordo com o tipo.

* Disponível apenas para clientes Profit Ultra. Os dados do Volume Profile não fornecem um histórico de dados extenso, fazendo com que o backtest de estratégias utilizando essa função seja limitado.

## Sintaxe:
HighestVolumePrice (Interval : Integer; Offset : Integer = 1; Type : Integer = 0; Standard : Boolean = True; Auction : Boolean = True; Cross : Boolean = True)|Rank : Integer|:

## Parâmetros:
- Interval: Intervalo de tempo utilizado para o cálculo do volume. Pode ser:
  - itDaily: Utiliza o intervalo diário. (No período Diário é apenas permitido Offset 1)
  - itMinute: Utiliza o intervalo em minutos.
- Offset: Determina a quantidade de períodos (dias ou minutos, dependendo do Interval) a partir do qual o cálculo será feito. Aceita valores entre 0 e 720. Um valor de 0 indica o período atual, enquanto valores maiores indicam períodos passados.
- Type: Define o tipo de volume a ser considerado no cálculo. Pode ser:
  - vtFinanceiro: Volume financeiro.
  - vtQuantidade: Volume em quantidade de ações ou contratos.
  - vtTrade: Número de negócios realizados.
- Standard: Variável booleana que permite puxar os trades padrão. Valor padrão é True.
- Auction: Variável booleana que define se o volume de leilões será incluído no cálculo. Valor padrão é True.
- Cross: Variável booleana que indica se o volume de operações cruzadas (cross trades) será considerado. Valor padrão é True.
- Rank: Deve ser definido ao final da função entre barras verticais: |RANK|. O primeiro (0) será o maior volume da lista.

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será retornado o preço do maior volume em quantidade nos últimos 5 minutos.

```
HighestVolumePrice(itMinute, 5, vtQuantity)|0|
```

# Função HighD

## Descrição:
A função HighD tem como finalidade retornar o valor de máxima de um número determinado de dias atrás. Atualmente a função não é compatível com ativo diferente do selecionado no backtest, como ativos coletados usando a função asset por exemplo.

## Sintaxe:
HighD(QuantidadeDiasAnteriores : Integer)

## Parâmetros:
- QuantidadeDiasAnteriores: Determina a quantidade desejada de dias anteriores.

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será atribuído à variável "dMaxima" o valor de máxima de dois dias anteriores ao dia atual.

```
dMaxima := HighD(2);
```

# Função HighM

## Descrição:
A função HighM tem como finalidade retornar o valor de máxima de um número determinado de meses atrás.

## Sintaxe:
HighM(QuantidadeMesesAnteriores : Integer)

## Parâmetros:
- QuantidadeMesesAnteriores: Determina a quantidade desejada de meses anteriores.

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será atribuído à variável "mMaxima" o valor de máxima de cinco meses anteriores ao mês atual.

```
mMaxima := HighM(5);
```

# Função HighW

## Descrição:
A função HighW tem como finalidade retornar o valor de máxima de um número determinado de semanas atrás.

## Sintaxe:
HighW(QuantidadeSemanasAnteriores : Integer)

## Parâmetros:
- QuantidadeSemanasAnteriores: Determina a quantidade desejada de semanas anteriores.

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será atribuído à variável "wMaxima" o valor de máxima de sete semanas anteriores à semana atual.

```
wMaxima := HighW(7);
```

# Função HighY

## Descrição:
A função HighY tem como finalidade retornar o valor de máxima de um número determinado de anos atrás.

## Sintaxe:
HighY(QuantidadeAnosAnteriores : Integer)

## Parâmetros:
- QuantidadeAnosAnteriores: Determina a quantidade desejada de anos anteriores.

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será atribuído à variável "yMaxima" o valor de máxima de dois anos anteriores ao atual.

```
yMaxima := HighY(2);
```

# Função LastCalcDate

## Descrição:
A função LastCalcDate retorna a data do último candle completo formado dentro do gráfico.

Observação: Datas são representadas pelo tipo de dado "Integer", no formato: 1AnoMêsDia.

## Sintaxe:
LastCalcDate

## Parâmetros:
Sem parâmetros.

## Retorno:
Integer

## Exemplos:
No exemplo abaixo, será colocado diretamente no gráfico a data dos candles de acordo com o andamento do mercado.

```
Plot(LastCalcDate);
```

# Função LastCalcTime

## Descrição:
A função LastCalcTime retorna a hora do último candle completo formado dentro do gráfico, no formato 24h(HHMM).

## Sintaxe:
LastCalcTime

## Parâmetros:
Sem parâmetros.

## Retorno:
Integer

## Exemplos:
No exemplo abaixo, será colocado diretamente no gráfico a hora de fechamento dos candles, de acordo com o andamento do mercado.

```
Plot(LastCalcTime);
```

# Função LastDayOfMonth

## Descrição:
A função LastDayOfMoth retorna o último dia do mês de referência.

## Sintaxe:
LastDayOfMonth(MesReferencia : Integer)

## Parâmetros:
- MesReferencia: Determina o mês de referência, de Janeiro(1) a Dezembro(12).

## Retorno:
Integer

## Exemplos:
No exemplo abaixo, será atribuído à variável "nDia" o último dia(30) do mês de Setembro.

```
nDia := LastDayOfMonth(9);
```

# Função LowD

## Descrição:
A função LowD tem como finalidade retornar o valor de mínima de um número determinado de dias atrás.

## Sintaxe:
LowD(QuantidadeDiasAnteriores : Integer)

## Parâmetros:
- QuantidadeDiasAnteriores: Determina a quantidade desejada de dias anteriores.

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será atribuído à variável "dMinima" o valor de mínima de três dias anteriores ao dia atual.

```
dMinima := LowD(3);
```

# Função LowM

## Descrição:
A função LowM tem como finalidade retornar o valor de mínima de um número determinado de meses atrás.

## Sintaxe:
LowM(QuantidadeMesesAnteriores : Integer)

## Parâmetros:
- QuantidadeMesesAnteriores: Determina a quantidade desejada de meses anteriores.

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será atribuído à variável "mMinima" o valor de mínima do mês anterior.

```
mMinima := LowM(1);
```

# Função LowW

## Descrição:
A função LowW tem como finalidade retornar o valor de mínima de um número determinado de semanas atrás.

## Sintaxe:
LowW(QuantidadeSemanasAnteriores : Integer)

## Parâmetros:
- QuantidadeSemanasAnteriores: Determina a quantidade desejada de semanas anteriores.

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será atribuído à variável "wMinima" o valor de mínima de sete semanas anteriores à semana atual.

```
wMinima := LowM(7);
```

# Função LowY

## Descrição:
A função LowY tem como finalidade retornar o valor de mínima de um número determinado de anos atrás.

## Sintaxe:
LowY(QuantidadeAnosAnteriores : Integer)

## Parâmetros:
- QuantidadeAnosAnteriores: Determina a quantidade desejada de anos anteriores.

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será atribuído à variável "yMinima" o valor de mínima de dois anos anteriores ao atual.

```
yMinima := LowY(2);
```

# Função Monday

## Descrição:
A função Monday retorna o número 1, representando o dia da semana: segunda-feira.

## Sintaxe:
Monday

## Parâmetros:
Sem parâmetros.

## Retorno:
Integer

## Exemplos:
No exemplo, a variável "nDia" irá receber número 1, referente ao dia específico da semana.

```
nDia := Monday;
```

# Função Month

## Descrição:
A função Month retorna o mês de uma data específica.

Observação: Datas são representadas pelo tipo de dado "Integer", no formato: 1AnoMêsDia.

## Sintaxe:
Month(Data : Integer)

## Parâmetros:
- Data: Data para obter o mês.

## Retorno:
Integer

## Exemplos:
No exemplo, a variável "mAtual" irá receber o mês atual.

```
mAtual := Month(CurrentDate);
```

# Função Next3rdFriday

## Descrição:
A função Next3rdFriday retorna a quantidade de dias úteis restantes até a terceira sexta-feira de determinado mês subsequente.

## Sintaxe:
Next3rdFriday(Mes : Integer)

## Parâmetros:
- Mes: Determina o mês que se deseja a informação, onde a contagem inicia-se a partir do mês atual(0).

## Retorno:
Integer

## Exemplos:
No exemplo abaixo, a variável "nSexta" irá receber a quantidade de dias úteis até a terceira sexta-feira do mês seguinte.

```
nSexta := Next3rdFriday(1);
```

# Função OpenD

## Descrição:
A função OpenD tem como finalidade retornar o valor de abertura de um número determinado de dias atrás.

## Sintaxe:
OpenD(QuantidadeDiasAnteriores : Integer)

## Parâmetros:
- QuantidadeDiasAnteriores: Determina a quantidade desejada de dias anteriores.

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será atribuído à variável "dAbertura" o valor de abertura de seis dias anteriores ao dia atual.

```
dAbertura := OpenD(6);
```

# Função OpenM

## Descrição:
A função OpenM tem como finalidade retornar o valor de abertura de um número determinado de meses atrás.

## Sintaxe:
OpenM(QuantidadeMesesAnteriores : Integer)

## Parâmetros:
- QuantidadeMesesAnteriores: Determina a quantidade desejada de meses anteriores.

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será atribuído à variável "mAbertura" o valor de abertura do mês anterior ao atual.

```
mAbertura := OpenM(1);
```

# Função OpenW

## Descrição:
A função OpenW tem como finalidade retornar o valor de abertura de um número determinado de semanas atrás.

## Sintaxe:
OpenW(QuantidadeSemanasAnteriores : Integer)

## Parâmetros:
- QuantidadeSemanasAnteriores: Determina a quantidade desejada de semanas anteriores.

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será atribuído à variável "wAbertura" o valor de abertura de cinco semanas anteriores à semana atual.

```
wAbertura := OpenW(5);
```

# Função OpenY

## Descrição:
A função OpenY tem como finalidade retornar o valor de abertura de um número determinado de anos atrás.

## Sintaxe:
OpenY(QuantidadeAnosAnteriores : Integer)

## Parâmetros:
- QuantidadeAnosAnteriores: Determina a quantidade desejada de anos anteriores.

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será atribuído à variável "yAbertura" o valor de abertura do ano anterior ao atual.

```
yAbertura := OpenY(1);
```

# Função RS_BarsPerDay

## Descrição:
A função RS_BarsPerDay retorna o número estimado de barras de determinada periodicidade(em minutos). Caso o periodo seja diário, será obtido 1 como retorno, e, para períodos em minutos, ocorrerá a divisão do número total de minutos em um dia(1440) pela periodicidade selecionada.

## Sintaxe:
RS_BarsPerDay

## Parâmetros:
Sem parâmetros.

## Retorno:
Inteiro

## Exemplos:
No exemplo, será atribuído à variável "n" o retorno da chamada de função.

```
n := RS_BarsPerDay;
```

# Função Saturday

## Descrição:
A função Saturday retorna o número 6, representando o dia da semana: sábado.

## Sintaxe:
Saturday

## Parâmetros:
Sem parâmetros.

## Retorno:
Integer

## Exemplos:
No exemplo, a variável "nDia" irá receber número 6, referente ao dia específico da semana.

```
nDia := Saturday;
```

# Função Sunday

## Descrição:
A função Sunday retorna o número 0, representando o dia da semana: domingo.

## Sintaxe:
Sunday

## Parâmetros:
Sem parâmetros.

## Retorno:
Integer

## Exemplos:
No exemplo, a variável "nDia" irá receber número 0, referente ao dia específico da semana.

```
nDia := Sunday;
```

# Função Thursday

## Descrição:
A função Thursday retorna o número 4, representando o dia da semana: quinta-feira.

## Sintaxe:
Thursday

## Parâmetros:
Sem parâmetros.

## Retorno:
Integer

## Exemplos:
No exemplo, a variável "nDia" irá receber número 4, referente ao dia específico da semana.

```
nDia := Thursday;
```

# Função Time

## Descrição:
A função Time possui como finalidade retornar a hora de abertura do candle analisado.

Observação: Horas são representadas pelo tipo de dado "Integer", no formato: HHMM.

## Sintaxe:
Time

## Parâmetros:
Sem parâmetros.

## Retorno:
Integer

## Exemplos:
No exemplo, será atribuído à variável "nHora", a hora de abertura do candle.

```
nHora := Time;
```

# Função TimeToMinutes

## Descrição:
A função TimeToMinutes possui como finalidade efetuar a conversão de um horário em minutos.

## Sintaxe:
TimeToMinutes(Hora : Integer)

## Parâmetros:
- Hora: Hora para a conversão.

## Retorno:
Integer

## Exemplos:
No exemplo, a variável "minutos" irá receber a conversão em minutos(750) da hora: 12h30.

```
minutos := TimeToMinutes(1230);
```

# Função Today

## Descrição:
A função Today possui como finalidade retornar a data atual do sistema.

Observação: Datas são representadas pelo tipo de dado "Integer", no formato: 1AnoMêsDia.

## Sintaxe:
Today

## Parâmetros:
Sem parâmetros.

## Retorno:
Integer

## Exemplos:
No exemplo, será atribuído à variável "nData" a data do dia atual.

```
nData := Today;
```

# Função Tuesday

## Descrição:
A função Tuesday retorna o número 2, representando o dia da semana: terça-feira.

## Sintaxe:
Tuesday

## Parâmetros:
Sem parâmetros.

## Retorno:
Integer

## Exemplos:
No exemplo, a variável "nDia" irá receber número 2, referente ao dia específico da semana.

```
nDia := Tuesday;
```

# Função VolumeAtPrice

## Descrição:
A função VolumeAtPrice Retorna o volume no preço selecionado para o intervalo.

* Disponível apenas para clientes Profit Ultra. Os dados do Volume Profile não fornecem um histórico de dados extenso, fazendo com que o backtest de estratégias utilizando essa função seja limitado.

## Sintaxe:
VolumeAtPrice(Interval : Integer; Offset : Integer = 1; Type : Integer = 0; Standard : Boolean = True; Auction : Boolean = True; Cross : Boolean = True)|Price : Float|

## Parâmetros:
- Interval: Intervalo de tempo utilizado para o cálculo do volume. Pode ser:
  - itDaily: Utiliza o intervalo diário.
  - itMinute: Utiliza o intervalo em minutos.
- Offset: Determina a quantidade de períodos (dias ou minutos, dependendo do Interval) a partir do qual o cálculo será feito. Aceita valores entre 0 e 720. Um valor de 0 indica o período atual, enquanto valores maiores indicam períodos passados.
- Type: Define o tipo de volume a ser considerado no cálculo. Pode ser:
  - vtFinancial: Volume financeiro.
  - vtQuantity: Volume em quantidade de ações ou contratos.
  - vtTrade: Número de negócios realizados.
- Standard: Variável booleana que permite puxar os trades padrão. Valor padrão é True.
- Auction: Variável booleana que define se o volume de leilões será incluído no cálculo. Valor padrão é True.
- Cross: Variável booleana que indica se o volume de operações cruzadas (cross trades) será considerado. Valor padrão é True.
- Price: Preço em float do qual se deseja saber o volume.

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será atribuído à variável "dVolumeAtPrice" o volume no preço 38.60 para os últimos 60 minutos.

```
var dVolumeAtPrice: Float;
begin
  dVolumeAtPrice := VolumeAtPrice(itMinute, 60, vtTrade, True, True, True)|38.60|;
end;
```

# Função VolumeD

## Descrição:
A função VolumeD tem como finalidade retornar o volume financeiro de um número determinado de dias atrás.

## Sintaxe:
VolumeD(QuantidadeDiasAnteriores : Integer)

## Parâmetros:
- QuantidadeDiasAnteriores: Determina a quantidade desejada de dias anteriores.

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será atribuído à variável "dVolume" o volume de seis dias anteriores ao dia atual.

```
dVolume := VolumeD(6);
```

# Função VolumeM

## Descrição:
A função VolumeM tem como finalidade retornar o volume financeiro de um número determinado de meses atrás.

## Sintaxe:
VolumeM(QuantidadeMesesAnteriores : Integer)

## Parâmetros:
- QuantidadeMesesAnteriores: Determina a quantidade desejada de meses anteriores.

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será atribuído à variável "mAbertura" o volume do mês anterior ao atual.

```
mVolume := VolumeM(1);
```

# Função VolumeW

## Descrição:
A função VolumeW tem como finalidade retornar o volume financeiro de um número determinado de semanas atrás.

## Sintaxe:
VolumeW(QuantidadeSemanasAnteriores : Integer)

## Parâmetros:
- QuantidadeSemanasAnteriores: Determina a quantidade desejada de semanas anteriores.

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será atribuído à variável "wVolume" o valor volume de cinco semanas anteriores à semana atual.

```
wVolume := VolumeW(5);
```

# Função VolumeY

## Descrição:
A função VolumeY tem como finalidade retornar o volume financeiro de um número determinado de anos atrás.

## Sintaxe:
VolumeY(QuantidadeAnosAnteriores : Integer)

## Parâmetros:
- QuantidadeAnosAnteriores: Determina a quantidade desejada de anos anteriores.

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será atribuído à variável "yVolume" o volume do ano anterior ao atual.

```
yVolume := VolumeY(1);
```

# Função Wednesday

## Descrição:
A função Wednesday retorna o número 3, representando o dia da semana: quarta-feira.

## Sintaxe:
Wednesday

## Parâmetros:
Sem parâmetros.

## Retorno:
Integer

## Exemplos:
No exemplo, a variável "nDia" irá receber número 3, referente ao dia específico da semana.

```
nDia := Wednesday;
```

# Função Year

## Descrição:
A função Year retorna o ano de uma data específica.

Observação: Datas são representadas pelo tipo de dado "Integer", no formato: 1AnoMêsDia.

## Sintaxe:
Year(Data : Integer)

## Parâmetros:
- Data: Data para obter o ano.

## Retorno:
Integer

## Exemplos:
No exemplo, a variável "yAtual" irá receber o ano atual.

```
yAtual := Year(CurrentDate);
```

# Função Yesterday

## Descrição:
A função Yesterday retorna a data do dia de ontem.

Observação: Datas são representadas pelo tipo de dado "Integer", no formato: 1AnoMêsDia.

## Sintaxe:
Yesterday

## Parâmetros:
Sem parâmetro

## Retorno:
Integer

## Exemplos:
No exemplo, a variável "nYesterday" irá receber a data de ontem.

```
nYesterday := Yesterday;
```

# Função TimeExchange

## Descrição:
A função TimeExchange retorna o tempo do candle de acordo com o timezone da bolsa.

## Sintaxe:
TimeExchange

## Parâmetros:
Sem parâmetro

## Retorno:
Integer

## Exemplos:
No exemplo, a variável "nTimeExchange" irá receber a data de acordo com o timezone da bolsa.

```
nYesterday := nTimeExchange;
```

# Função C_3WhSolds_3BlkCrows

## Descrição:
A função C_3WhSolds_3BlkCrows identifica a ocorrência de dois tipos de candles: 3 White Soldiers e 3 Black Crows.

## Sintaxe:
C_3WhSolds_3BlkCrows(Comprimento : Integer, Fator : Integer, var o3WhiteSoldiers : Integer, var o3BlackCrows : Integer)

## Parâmetros:
- Comprimento: Tamanho utilizado para calcular a média do corpo do candle.
- Fator: Determina quantas vezes a sombra do candle deve ser maior que o seu corpo.
- o3WhiteSoldiers: Variável para identificação de padrão(3 White Soldiers).
- o3BlackCrows: Variável para identificação de padrão(3 Black Crows).

## Retorno:
Integer:
- Identificação(retorno função):
  - 0 - Algum dos padrões foi identificado.
  - 1 - Nenhuma padrão identificado.

Identificação(retorno variável: o3WhiteSoldiers):
- 0 - Padrão 3 White Soldiers não foi identificado.
- 1 - Padrão 3 White Soldiers identificado.

Identificação(retorno variável: o3BlackCrows):
- 0 - Padrão 3 Black Crows não foi identificado.
- 1 - Padrão 3 Black Crows identificado.

## Exemplos:
No exemplo, caso seja identificado algum dos padrões(3 White Soldiers ou 3 Black Crows), considerando 9(Comprimento) e 2(Fator), será aplicada uma coloração(vermelha).

```
aux := C_3WhSolds_3BlkCrows(9, 2, o3WhiteSoldiers, o3BlackCrows);
if (o3WhiteSoldiers = 1) or (o3BlackCrows = 1) then
  PaintBar(clRed);
```

# Função C_BullEng_BearEng

## Descrição:
A função C_BullEng_BearEng identifica a ocorrência de dois tipos de candles: Bullish Engulfing e Bearish Engulfing.

## Sintaxe:
C_BullEng_BearEng(Comprimento : Integer, var oBullishEngulfing : Integer, var oBearishEngulfing : Integer)

## Parâmetros:
- Comprimento: Tamanho utilizado para calcular a média do corpo do candle.
- oBullishEngulfing: Variável para identificação de padrão(Bullish Engulfing).
- oBearishEngulfing: Variável para identificação de padrão(Bearish Engulfing).

## Retorno:
Integer:
- Identificação(retorno função):
  - 0 - Algum dos padrões foi identificado.
  - 1 - Nenhuma padrão identificado.

Identificação(retorno variável: oBullishEngulfing):
- 0 - Padrão Bullish Engulfing não foi identificado.
- 1 - Padrão Bullish Engulfing identificado.

Identificação(retorno variável: oBearishEngulfing):
- 0 - Padrão Bearish Engulfing não foi identificado.
- 1 - Padrão Bearish Engulfing identificado.

## Exemplos:
No exemplo, caso o padrão Bullish Engulfing seja identificado, considerando 13(Comprimento), será aplicada uma coloração(amarela).

```
aux := C_BullEng_BearEng(13, oBullishEngulfing, oBearishEngulfing);
if (oBullishEngulfing = 1) then
  PaintBar(clYellow);
```

# Função C_Doji

## Descrição:
A função C_Doji identifica a ocorrência de um candle tipo Doji.

## Sintaxe:
C_Doji(Percentual : Integer)

## Parâmetros:
- Percentual: Limiar para(Abertura - Fechamento) que seria uma percentagem do intervalo do candle.

## Retorno:
Integer:
- Identificação:
  - 0 - Padrão não identificado.
  - 1 - Padrão identificado.

## Exemplos:
No exemplo, caso o padrão seja identificado, considerando percentual de 5%, será aplicada uma coloração(verde).

```
if(C_Doji(5) = 1) then
  PaintBar(clGreen);
```

# Função C_Hammer_HangingMan

## Descrição:
A função C_Hammer_HangingMan identifica a ocorrência de dois tipos de candles: Hammer e Hanging Man.

## Sintaxe:
C_Hammer_HangingMan(Comprimento : Integer, Fator : Integer, var oHammer : Integer, var oHangingMan : Integer)

## Parâmetros:
- Comprimento: Tamanho utilizado para calcular a média do corpo do candle.
- Fator: Determina quantas vezes a sombra do candle deve ser maior que o seu corpo.
- oHammer: Variável para identificação de padrão(Hammer).
- oHangingMan: Variável para identificação de padrão(Hanging Man).

## Retorno:
Integer:
- Identificação(retorno função):
  - 0 - Nenhum padrão identificado.
  - 1 - Algum dos padrões foi identificado.

Identificação(retorno variável: oHammer):
- 0 - Padrão Morning Hammer não foi identificado.
- 1 - Padrão Morning Hammer identificado.

Identificação(retorno variável: oHangingMan):
- 0 - Padrão Hanging Man não foi identificado.
- 1 - Padrão Hanging Man identificado.

## Exemplos:
No exemplo, caso seja identificado algum dos padrões(Hammer ou Hanging Man), considerando 14(Comprimento) e 2(Fator), será aplicada uma coloração(amarela).

```
aux := C_Hammer_HangingMan(14, 2, oHammer, oHangingMan);
if (oHammer = 1) or (oHangingMan = 1) then
  PaintBar(clYellow);
```

# Função C_MornDoji_EveDoji

## Descrição:
A função C_MornDoji_EveDoji identifica a ocorrência de dois tipos de candles: Morning Doji Star e Evening Doji Star.

## Sintaxe:
C_MornDoji_EveDoji(Comprimento : Integer, Percentual : Float, var oMorningDojiStar : Integer, var oEveningDojiStar : Integer)

## Parâmetros:
- Comprimento: Tamanho utilizado para calcular a média do corpo do candle.
- Percentual: Doji limiar para o (abrir - fechar) como uma percentagem do intervalo da barra.
- oMorningDojiStar: Variável para identificação de padrão(Morning Doji Star).
- oEveningDojiStar: Variável para identificação de padrão(Evening Doji Star).

## Retorno:
Integer:
- Identificação(retorno função):
  - 0 - Algum dos padrões foi identificado.
  - 1 - Nenhuma padrão identificado.

Identificação(retorno variável: oMorningDojiStar):
- 0 - Padrão Morning Doji Star não foi identificado.
- 1 - Padrão Morning Doji Star identificado.

Identificação(retorno variável: oEveningDojiStar):
- 0 - Padrão Evening Doji Star não foi identificado.
- 1 - Padrão Evening Doji Star identificado.

## Exemplos:
No exemplo, caso seja identificado algum dos padrões(Morning Doji Star ou Evening Doji Star), considerando 9(Comprimento) e 3(Percentual), será aplicada uma coloração(branca).

```
aux := C_MornDoji_EveDoji(9, 3, oMorningDojiStar, oEveningDojiStar);
if (oMorningDojiStar = 1) or (oEveningDojiStar = 1) then
  PaintBar(clWhite);
```

# Função C_MornStar_EveStar

## Descrição:
A função C_MornStar_EveStar identifica a ocorrência de dois tipos de candles: Morning Star e Evening Star.

## Sintaxe:
C_MornStar_EveStar(Comprimento : Integer, var oMorningStar : Integer, var oEveningStar : Integer)

## Parâmetros:
- Comprimento: Tamanho utilizado para calcular a média do corpo do candle.
- oMorningStar: Variável para identificação de padrão(Morning Star).
- oEveningStar: Variável para identificação de padrão(Evening Star).

## Retorno:
Integer:
- Identificação(retorno função):
  - 0 - Algum dos padrões foi identificado.
  - 1 - Nenhuma padrão identificado.

Identificação(retorno variável: oMorningStar):
- 0 - Padrão Morning Star não foi identificado.
- 1 - Padrão Morning Star identificado.

Identificação(retorno variável: oEveningStar):
- 0 - Padrão Evening Star não foi identificado.
- 1 - Padrão Evening Star identificado.

## Exemplos:
No exemplo, caso o padrão Evening Star seja identificado, considerando 6(Comprimento), será aplicada uma coloração(verde).

```
aux := C_MornStar_EveStar(6, oMorningStar, oEveningStar);
if (oEveningStar = 1) then
  PaintBar(clGreen);
```

# Função C_PierceLine_DkCloud

## Descrição:
A função C_PierceLine_DkCloud identifica a ocorrência de dois tipos de candles: Piercing Line e Dark Cloud.

## Sintaxe:
C_PierceLine_DkCloud(Comprimento : Integer, var oPiercingLine : Ingeter, var oDarkCloud : Ingeter)

## Parâmetros:
- Comprimento: Tamanho utilizado para calcular a média do corpo do candle.
- oPiercingLine: Variável para identificação de padrão(Piercing Line).
- oDarkCloud: Variável para identificação de padrão(Dark Cloud).

## Retorno:
Integer:
- Identificação(retorno função):
  - 0 - Algum dos padrões foi identificado.
  - 1 - Nenhuma padrão identificado.

Identificação(retorno variável: oPiercingLine):
- 0 - Padrão Piercing Line não foi identificado.
- 1 - Padrão Piercing Line identificado.

Identificação(retorno variável: oDarkCloud):
- 0 - Padrão Dark Cloud não foi identificado.
- 1 - Padrão Dark Cloud identificado.

## Exemplos:
No exemplo, caso o padrão Dark Cloud seja identificado, considerando 5(Comprimento), será aplicada uma coloração(amarela).

```
aux := C_PierceLine_DkCloud(5, oPiercingLine, oDarkCloud);
if (oDarkCloud = 1) then
  PaintBar(clYellow);
```

# Função C_ShootingStar

## Descrição:
A função C_ShootingStar identifica a ocorrência de candles tipo Shooting Star.

## Sintaxe:
C_ShootingStar(Comprimento : Integer, Fator : Integer)

## Parâmetros:
- Comprimento: Tamanho utilizado para calcular a média do corpo do candle.
- Fator: Determina quantas vezes a sombra do candle deve ser maior que o seu corpo.

## Retorno:
Integer:
- Identificação:
  - 0 - Padrão não identificado.
  - 1 - Padrão identificado.

## Exemplos:
No exemplo, caso o padrão seja identificado, considerando 10(Comprimento) e 2(Fator), será aplicada uma coloração(verde).

```
if (C_ShootingStar(10, 2) = 1) then
  PaintBar(clVerde);
```