# Função KVO

## Descrição:
A função KVO retorna o valor do indicador KVO, de acordo com os períodos desejados.

## Sintaxe:
KVO(MediaLonga : Integer, MediaCurta : Integer, Sinal : Integer)|Dado : Integer|

## Parâmetros:
- MediaLonga: Determina o período da Média Longa para formação do cálculo.
- MediaCurta: Determina o período da Média Curta.
- Sinal: Determina o sinal para a formação do cálculo.
- Linha: Determina qual linha será obtida:
  - 0 - Linha
  - 1 - Histograma

## Retorno:
Float

## Exemplos:
No exemplo, a variável "n" irá receber o valor do histograma do indicador KVO, considerando 55(Média Longa), 34(Média Curta), 13(Sinal) para o cálculo.

```
n := KVO(55, 34, 13)|1|;
```

# Função LinearRegressionChannel

## Descrição:
A função LinearRegressionChannel retorna os dados do indicador Canal de Regressão Linear.

## Sintaxe:
LinearRegressionChannel(Periodo : Integer; UsarDesvioSuperior : Boolean; DesvioSuperior : Float; UsarDesvioInferior : Boolean; DesvioInferior : Float)|Linha : Integer|

## Parâmetros:
- Periodo: Total de candles considerados.
- UsarDesvioSuperior: Define se o desvio superior será utilizado.
- DesvioSuperior: Desvio superior considerado.
- UsarDesvioInferior: Define se o desvio inferior será utilizado.
- DesvioInferior: Desvio inferior considerado.
- Linha: Determina qual linha será obtida:
  - 0 - Centra
  - 1 - Superior
  - 2 - Inferior

## Retorno:
Float

## Exemplos:
No exemplo, será plotada a linha central

## Plot(LinearRegressionChannel(100, true, 2, true, 2));

## Função LSVolatilityIndex

## Descrição:

A função LSVolatilityIndex retorna o valor do indicador L&amp;S Volatility Index .

## Sintaxe:

LSVolatilityIndex

## Parâmetros:

Sem parâmetros.

## Retorno:

Float

## Exemplos:

No exemplo, a variável "vLSV" irá receber o valor do indicador L&amp;S Volatility Index.

## vLSV := LSVolatilityIndex;

## Função MACD

## Descrição:

A função MACD retorna o valor do indicador MACD Linha e Histograma , de acordo com os períodos desejados.

## Sintaxe:

MACD(MediaLonga : Integer, MediaCurta : Integer, Sinal : Integer)|Dado : Integer|

## Parâmetros:

MediaLonga:

Determina o período da Média Longa para formação do cálculo.

MediaCurta: Determina o período da Média Curta.

Sinal: Determina o sinal para a formação do cálculo.

Linha: Determina qual linha será obtida:

0 - Linha

1 - Histograma

## Retorno:

Float

## Exemplos:

No exemplo, a variável "fMACD" irá receber o valor do histograma, considerando 26(Média Longa), 12(Média Curta), 9(Sinal).

## fMACD := MACD(26, 12, 9)|1|;

## Função MFI

## Descrição:

A função MFI retorna o valor do indicador Market Facilitation Index .

## Sintaxe:

MFI

## Parâmetros:

Sem parâmetros.

## Retorno:

Float

## Exemplos:

No exemplo, a variável "nMFI" irá receber o valor do indicador MFI.

nMFI := MFI;

## Função MIMA

## Descrição:

A função MIMA possui como característica retornar o dado do indicador PhiCube - MIMA.

## Sintaxe:

MIMA(Periodo : Integer)

## Parâmetros:

Periodo: Período utilizado no momento do cálculo do indicador.

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "vMIMA" o valor do indicador MIMA, considerando 10 períodos para o cálculo.

vMIMA := MIMA(10);

## Função MIMAROC

## Descrição:

Criado por Bo Williams, este indicador oscilador mede a inclinação (Rate Of Change) do PhiCube MIMA. Um valor acima de zero indica subida. Um valor abaixo de zero indica queda.

## Sintaxe:

MIMAROC(Periodo : Integer)

## Parâmetros:

Periodo: Período utilizado no momento do cálculo do indicador.

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "vMIMAROC" o valor do indicador MIMAROC, considerando 10 períodos para o cálculo.

## vMIMAROC := MIMAROC(10);

## Função Momentum

## Descrição:

A função Momentum retorna o valor do indicador Momentum , de acordo com o período e tipo de média desejados.

## Sintaxe:

Momentum(Periodo : Integer, Media : Integer, TipoMedia : Integer)

## Parâmetros:

Periodo: Período utilizado no momento do cálculo do indicador. Media: Média utilizada no momento do cálculo do indicador.

TipoMedia: Determina qual média será considerada:

0 - Aritmética

- 1 - Exponencial
- 2 - Welles Wilder
- 3 - Ponderada

## Retorno:

Float

## Exemplos:

No exemplo, a variável "nMomentum" irá receber o valor do indicador Momentum, considerando 10(Períodos), 3(Média) e tipo de média exponencial para o cálculo.

nMomentum := Momentum(10, 3, 1);

## Função MomentumStochastic

## Descrição:

A função MomentumStochastic retorna o valor do indicador Momento Estocástico , de acordo com o período desejado.

## Sintaxe:

MomentumStochastic(Periodo : Integer)

## Parâmetros:

Periodo: Período utilizado no momento do cálculo do indicador.

## Retorno:

Float

## Exemplos:

No exemplo, a variável "nMS" irá receber o valor do indicador Momento Estocástico, considerando 14 período para o cálculo.

## nMS := MomentumStochastic(14);

## Função MoneyFlow

nMoney := MoneyFlow;

## Função MoneyFlowIndex

## Descrição:

A função MoneyFlow retorna o valor do indicador Money Flow .

## Sintaxe:

MoneyFlow

## Parâmetros:

Sem parâmetros.

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "nMoney" o valor do indicador Money Flow.

## Descrição:

A função MoneyFlowIndex retorna o valor do indicador Money Flow Index , de acordo com o período desejado.

## Sintaxe:

MoneyFlowIndex(Periodo : Integer)

## Parâmetros:

Periodo: Período utilizado no momento do cálculo do indicador.

## Retorno:

Float

## Exemplos:

No exemplo, a variável "nMoneyF" irá receber o valor do indicador Money Flow Index, considerando 14 período para o cálculo.

## nMoneyF := MoneyFlowIndex(14);

## Função NelogicaBottomFinder

## Descrição:

A função NelogicaBottomFinder retorna o valor do indicador Nelogica Bottom Finder , conforme o dado desejado(linha e histograma).

## Sintaxe:

NelogicaBottomFinder|Dado : Integer|

## Parâmetros:

Dado: Determina qual dado será obtido:

- 0 - Linha
- 1 - Histograma

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "nBF" o dado do histograma.

## nBF := NelogicaBottomFinder|1|;

## Função NelogicaPullBackFinder

## Descrição:

A função NelogicaPullBackFinder retorna o valor do indicador Nelogica Pullback Finder , conforme o dado desejado(linha e histograma).

## Sintaxe:

NelogicaPullBackFinder|Dado : Integer|

## Parâmetros:

Dado: Determina qual dado será obtido:

- 0 - Linha
- 1 - Histograma

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "nPF" o dado do histograma.

## nPF := NelogicaPullBackFinder|1|;

## Função NelogicaWeisWave

## Descrição:

A função NelogicaWeisWave retorna o valor do indicador Nelogica Weis Wave , de acordo com o período desejado.

## Sintaxe:

NelogicaWeisWave(Periodo  : Integer)

## Parâmetros:

Periodo: Determina o período para o cálculo do indicador.

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "nWW" o retorno da função, considerando 3 períodos para o cálculo.

## nWW := NelogicaWeisWave(3);

## Função OBV

## Descrição:

A função OBV retorna o valor do indicador OBV .

## Sintaxe:

OBV

## Parâmetros:

Sem parâmetros.

## Retorno:

Float

## Exemplos:

No exemplo, a variável "nOBV" irá receber o valor do indicador OBV.

nOBV := OBV;

## Função OBVAvg

## Descrição:

A função OBVAvg retorna o valor do indicador OBV Ponderado .

## Sintaxe:

OBVAvg(Periodo : Integer, TipoMedia : Integer)

## Parâmetros:

Periodo: Período utilizado no momento do cálculo do indicador.

TipoMedia : Determina qual média será considerada:

0 - Aritmética

1 - Exponencial

2 - Welles Wilder

3 - Ponderada

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "nOBV" o retorno da função OBVAvg, considerando 10(Períodos) e tipo de média ponderada(3).

## Descrição:

A função OnBalanceTR retorna o valor do indicador On-Balance True Range

## Sintaxe:

OnBalanceTR

## Parâmetros:

Sem parâmetros.

## Retorno:

Float

## Exemplos:

No exemplo, a variável "nOBTR" irá receber o valor do indicador On-Balance True Range.

## Função OpenDaily

## Descrição:

A função OpenDaily retorna o dado de abertura, conforme o deslocamento especificado.

## Sintaxe:

OpenDaily(DaysBack : Integer)

## Parâmetros:

DaysBack: Número de dias para o deslocamento.

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "vOpenDaily", a abertura do dia anterior.

## vOpenDaily:=OpenDaily(1);

## Função OpenInterest

## Descrição:

A função OpenInterest retorna o valor do indicador Contratos em Aberto .

## Sintaxe:

OpenInterest

## Parâmetros:

Sem parâmetros.

## Retorno:

Float

## Exemplos:

No exemplo, será atribuída à variável "nOpen" o dado do indicador.

## nOpen := OpenInterest;

## Função ParabolicSAR

## Descrição:

A função ParabolicSAR retorna o valor do indicador SAR Parabólico , de acordo com os parâmetros desejados.

## Sintaxe:

ParabolicSAR(Fator : Float, Limite : Float)

## Parâmetros:

Fator: Determina o Fator de Aceleração para formação do cálculo. Limite: Determina o Limite de Aceleração.

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "nSAR" o valor do indicador SAR Parabólico, considerando 0.02(Fator) e 0.2(Limite) para o cálculo.

## nSAR := ParabolicSAR(0.02, 0.2);

## Função Phibo

## Descrição:

A função Phibo retorna o valor do indicador PhiCube - Phibo Line .

## Sintaxe:

Phibo(Periodo : Integer)

## Parâmetros:

Periodo: Período utilizado no momento do cálculo do indicador.

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "vPhibo" o retorno da função, considerando 17(Períodos) para o cálculo.

## vPhibo := Phibo(17);

## Função Pivot

## Descrição:

A função Pivot retorna o valor do indicador Pivot , de acordo com os parâmetros específicos desejados.

## Sintaxe:

Pivot(Normal : Boolean, TresLinhas : Boolean)|Linha : Integer|

## Parâmetros:

Normal: Determina o tipo de cálculo que será efetuado para o Pivot:

True - (Máxima + Mínima + Fechamento) / 3

False - (Abertura + Máxima + Mínima + Fechamento) / 4

TresLinhas: Determina quantas linhas serão consideradas:

True - Três Linhas

False - Duas Linhas

Linha: Determina qual linha será obtida:

True(Três Linhas):

0 - Pivot

1 - R3

2 - S3

3 - R2

4 - S2

5 - R1

6 - S1

False(Duas Linhas):

0 - Pivot

1 - R2

2 - S2

3 - R1

4 - S1

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "aux" a linha S3, considerando para o Pivot o tipo de cálculo: (Máxima + Mínima + Fechamento) / 3.

## aux := Pivot(True, True)|2|;

## Função PowerMeter

## Descrição:

A função PowerMeter retorna os dados do indicador PowerMeter(Medidor de Pressão) informa a quantidade do Agressor Comprador ou do Agressor Vendedor, dependendo dos parâmetros fornecidos.

## Sintaxe:

PowerMeter(Side : Integer, Minutes : Integer = 0, InitialDate : Integer = 0, EndDate : Integer = 0)

## Parâmetros:

Side: Parâmetro do tipo inteiro, informa o lado de ordem que considera para devolver os valores, passando a constante osBuy para valores de Compra e a constante osSell para valores de Venda.

Minutes:

Informa a janela de tempo, em minutos, que o indicador deve considerar, dos últimos X minutos.

Quando não informado considera valores diários.

InitialDate: Utilizado para informar períodos customizados de análise, data inicial da janela de análise.

EndDate: Utilizado para informar períodos customizados de análise, data final da janela de análise.

## dPower := PowerMeter(osBuy);

## Função PriceNery

vPriceNery:=PriceNery;

## Função PriceOsc

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "dPower" o retorno da chamada, considerando o lado de Compra para o valor diário sem utilizar um período customizado.

## Descrição:

A função PriceNery retorna os dados do indicador PriceNery .

## Sintaxe:

PriceNery

## Parâmetros:

Sem parâmetros

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "vPriceNery" o retorno da chamada.

Descrição:

A função PriceOsc retorna o valor do indicador Oscilador de Preços , de acordo com os períodos e tipos de médias desejados.

## Sintaxe:

PriceOsc(Media1 : Integer, TipoMedia1 : Integer, Media2 : Integer, TipoMedia2 : Integer)

## Parâmetros:

Media1: Período utilizado para a média 1.

TipoMedia1 : Determina qual média será considerada:

- 0 - Aritmética
- 1 - Exponencial
- 2 - Welles Wilder
- 3 - Ponderada

Media2 : Período utilizado para a média 2.

TipoMedia2 : Determina qual média será considerada:

- 0 - Aritmética
- 1 - Exponencial
- 2 - Welles Wilder
- 3 - Ponderada

## Retorno:

Float

## Exemplos:

No exemplo, a variável "nPrice" irá receber o valor do indicador Oscilador de Preços, considerando 12(Média 1) e 21(Média 2) períodos, e tipo exponencial para o cálculo.

## nPrice := PriceOsc(12, 1, 21, 1);

## Função PriceVolumeTrend

## Descrição:

A função PriceVolumeTrend retorna o valor do indicador Tendência Preço/Volume .

## Sintaxe:

PriceVolumeTrend

## Parâmetros:

Sem parâmetros.

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "nVolTrend" o dado do indicador Tendência Preço/Volume.

## nVolTrend := PriceVolumeTrend;

## Função PriorCote

## Descrição:

A função PriorCote retorna o valor do indicador Prior Cote , de acordo com o dado desejado.

## Sintaxe:

PriorCote(Dado : Integer)

## Parâmetros:

Dado: Determina o dado que será obtido:

- 0 - Fechamento
- 1 - Abertura
- 2 - Máxima
- 3 - Mínima
- 4 - Ajuste

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "nPrior" o valor de fechamento do período anterior.

## nPrior := PriorCote(0);

## Função PTAX

## Descrição:

A função PTAX retorna os dados do indicador TR - PTAX .

## Sintaxe:

PTAX[Dado : Integer]

## Parâmetros:

Dado: Obtém o dado desejado do indicador:

0 - Oficial

1 - P4

2 - P3

3 - P2

4 - P1

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "vPTAX" a PTAX oficial.

## vPTAX := PTAX;

## Função PTAXFuturo

## Descrição:

A função PTAXFuturo retorna os dados do indicador TR - PTAX Futuro .

## Sintaxe:

PTAXFuturo[Dado : Integer]

## Parâmetros:

Dado: Obtém o dado desejado do indicador:

0 - Oficial

1 - P4

2 - P3

3 - P2

4 - P1

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "vPTAX" a PTAXF oficial.

## vPTAXF := PTAXFuturo;

## Função QuantityVol

## Descrição:

A função QuantityVol retorna o valor do indicador Volume Quantidade , podendo-se incluir ou desconsiderar os dados: "volume projetado" e "leilão e trades diretos".

Observação: O parâmetro Agressores só será considerado para o cálculo do indicador caso o seja assinado o Opcional ' Plugin Tape Reading '. Caso não possua o opcional o indicador será sempre calculado como False, independente do que for inserido no campo.

## Sintaxe:

QuantityVol(VolumeProjetado : Boolean, Agressores : Boolean)

## Parâmetros:

VolumeProjetado: Determina se o volume irá considerar o dado projetado. Agressores: Determina se o volume irá desconsiderar o leilão e trades diretos.

## Retorno:

Float

vQuantidade := QuantityVol(False, False);

## Função Rafi

## nRafi := Rafi;

## Função Ravi

## Exemplos:

No exemplo, a variável "vQuantidade" irá receber o valor do indicador Volume Quantidade, desconsiderando os dados de "volume projetado" e "leilão e trades diretos".

## Descrição:

A função Rafi retorna o valor do indicador Rafi .

## Sintaxe:

Rafi

## Parâmetros:

Sem parâmetros.

## Retorno:

Float

## Exemplos:

No exemplo, a variável "nRafi" irá receber o dado do indicador específico.

## Descrição:

A função Ravi retorna o valor do indicador Ravi , de acordo com os períodos desejados.

## Sintaxe:

Ravi(MediaLonga : Integer, MediaCurta: Integer)

## Parâmetros:

MediaCurta: Período utilizado na média curta para o cálculo do indicador. MediaLonga: Período utilizado na média longa.

## Retorno:

Float

## Exemplos:

No exemplo, a variável "nRavi" irá receber o valor do indicador Ravi, considerando 7(Média Curta) e 65(Média Longa) períodos para o cálculo.

## nRavi := Ravi(65, 7);

## Função RBG

## Descrição:

A função RBG retorna os dados do indicador RBG .

## Sintaxe:

RBG

## Parâmetros:

Sem parâmetros

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "nRBG", o retorno da chamada de função.

## nRBG:= RBG;

## Função RenkoVTwo

## Descrição:

A função RenkoVTwo retorna o valor do indicador RenkoV2 , de acordo com os parâmetros desejados.

## Sintaxe:

RenkoVTwo(Periodo : Integer, Abertura : Float, Deslocamento : Integer)|Linha : Integer|

## Parâmetros:

Período: Período utilizado no momento do cálculo do indicador.

Abertura: Referente ao parâmetro "Abertura" do indicador.

Deslocamento: Relacionado ao parâmetro "Deslocamento" do indicador.

Linha: Determina qual linha será obtida:

0 - Linha RenkoV2+

1 - Linha RenkoV2-

## Retorno:

Float

## Exemplos:

No exemplo, a variável "renkoV" irá receber o valor da linha RenkoV2- do indicador RenkoV2, considerando 20(Período), 1.5(Abertura) e 0(Deslocamento) para o cálculo

## renkoV := RenkoVTwo(20, 1.5, 0)|1|;

## Função ROC

## Descrição:

A função ROC retorna o valor do indicador ROC , de acordo com os períodos e tipo de média desejados.

## Sintaxe:

ROC(Periodo : Integer, Media : Integer, TipoMedia : Integer)

## Parâmetros:

Periodo: Período utilizado no momento do cálculo do indicador.

Media: Período da média utilizada.

TipoMedia: Determina qual média será considerada:

- 0 - Aritmética
- 1 - Exponencial
- 2 - Welles Wilder
- 3 - Ponderada

## Retorno:

Float

## Exemplos:

No exemplo, a variável "nRoc" irá receber o valor do indicador ROC, considerando 3(Período), 9(Média) e tipo de aritmética.

## nRoc := ROC(3, 9, 0);

## Função RSI

## Descrição:

A função RSI retorna o valor do indicador IFR(RSI) , de acordo com o período e tipo desejados.

## Sintaxe:

RSI(Periodo : Integer, Tipo : Integer)

## Parâmetros:

Periodo: Período utilizado no momento do cálculo do indicador.

Tipo: Tipo de cálculo aplicado:

0 - Clássico

- 1 - Simples

## Retorno:

Float

## Exemplos:

No exemplo, a variável "aux" irá receber o valor do indicador IFR(RSI), considerando 2 períodos e tipo clássico para o cálculo.

aux := RSI(2, 0);

## Função RsiStochastic

## Descrição:

A função RsiStochastic retorna o valor do indicador IFR Estocástico , de acordo com o período desejado.

## Sintaxe:

RsiStochastic(Periodo : Integer)

## Parâmetros:

Periodo: Período utilizado no momento do cálculo do indicador.

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "nRS" o valor do indicador IFR Estocástico, considerando 2 períodos para o cálculo.

## nRS := RsiStochastic(2);

## Função SafeZoneDownTrend

## Descrição:

A função SafeZoneDownTrend retorna o valor do indicador Stop SafeZone DownTrend , de acordo com os parâmetros desejados .

## Sintaxe:

SafeZoneDownTrend(Multiplicador  : Float, Periodo : Integer, Deslocamento : Integer)

## Parâmetros:

Multiplicador: : Valor de Multiplicador utilizado no cálculo do indicador.

Periodo: Período considerado.

Deslocamento: Deslocamento de períodos.

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "aux" o dado do indicador Stop SafeZone DownTrend, considerando 2.0(Multiplicador), 10(Período) e 0(Deslocamento) para o cálculo.

## aux := SafeZoneDownTrend(2.0, 10, 0);

## Função SafeZoneUpTrend

## Descrição:

A função SafeZoneUpTrend retorna o valor do indicador Stop SafeZone UpTrend , de acordo com os parâmetros desejados .

## Sintaxe:

SafeZoneUpTrend(Multiplicador : Float, Periodo : Integer, Deslocamento : Integer)

## Parâmetros:

Multiplicador: : Valor de Multiplicador utilizado no cálculo do indicador. Periodo: Período considerado.

Deslocamento: Deslocamento de períodos

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "aux" o dado do indicador Stop SafeZone UpTrend, considerando 2.0(Multiplicador), 10(Período) e 0(Deslocamento) para o cálculo.

## aux := SafeZoneUpTrend(2.0, 10, 0);

## Função Santo

## Descrição:

A função Santo retorna o valor do indicador PhiCube - Santo , de acordo com o período desejado.

## Sintaxe:

Santo(Periodo : Integer)|Linha : Integer|

## Parâmetros:

Periodo: Período utilizado no momento do cálculo do indicador.

Linha: Determina qual linha será obtida:

0 - Dado referente à linha Santo.

1 - Dado relacionado ao Sinal.

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "vSanto" o dado do sinal, considerando 72(Períodos) para o cálculo.

## vSanto := Santo(72)|1|;

## Função SlowStochastic

## Descrição:

A função SlowStochastic retorna o valor do indicador Estocástico Lento , de acordo com o período desejado.

Observação: Os parâmetros PeriodoMedia e TipoMedia são opcionais, caso não sejam determinados, serão utilizados os valores 14 e 1 respectivamente.

## Sintaxe:

SlowStochastic(Periodo : Integer, PeriodoMedia : Integer, TipoMedia : Integer)

## Parâmetros:

Periodo: Período utilizado no momento do cálculo do indicador.

PeriodoMedia: Período utilizado no momento do cálculo da média.

TipoMedia: Tipo da média a ser calculada pelo indicador:

- 0 - Aritmética
- 1 - Exponencial
- 2 - Welles Wilder
- 3 - Ponderada

## Retorno:

Float

## Exemplos:

No exemplo, a variável "nEstLen" irá receber o valor do indicador Estocástico Lento, considerando 14 períodos para o cálculo.

## nEstLen := SlowStochastic(14);

## Função SOMOSRENKOTRENDMPONTO

## Descrição:

É um indicador que auxilia no envio de ordens. O indicador tem a função de sinalizar 0,5 ponto acima ou abaixo do fechamento do último box, indicando o ponto exato de onde o Trader deve colocar sua ordens de compra ou venda, caso entenda que o último fechamento é um ponto de entrada relevante.

## Sintaxe:

SOMOSRENKOTRENDMPONTO |Linha : Integer|

## Parâmetros:

Linha: Determina qual linha será obtida:

1 - Linha 1

2 - Linha 2

## Retorno:

Float

## Exemplos:

No exemplo, a variável "nSRENKO" irá receber o valor do indicador SOMOSRENKOTRENDMPONTO.

## nSRENKO := SOMOSRENKOTRENDMPONTO|1|;

## Função StopATR

## Descrição:

A função StopATR retorna o valor do indicador Stop ATR , de acordo com os parâmetros desejados.

## Sintaxe:

StopATR(Desvio : Float, Periodo : Integer, TipoMedia : Integer)|Dado : Integer|

## Parâmetros:

Desvio: Desvio utilizado para o cálculo do indicador.

Periodo: Período que será considerado.

TipoMedia: Determina qual média será considerada:

- 0 - Aritmética
- 1 - Exponencial
- 2 - Welles Wilder
- 3 - Ponderada

Dado: Determina o dado que será obtido:

- 0 - Valor indicador.
- 1 - Flag para informar a ocorrência(retorno):
- 0 - ATR+
- 1 - ATR

## Retorno:

Float

## Exemplos:

No exemplo, a variável "aux" irá receber o valor do indicador Stop ATR, considerando 2.0(Desvio), 20(Períodos) para o cálculo.

## aux := StopATR(2.0, 20, 0);

## Função TendencyTracker

## Descrição:

A função TendencyTracker retorna o valor do indicador Rastreador de Tendências , conforme o período desejado.

## Sintaxe:

TendencyTracker(Dias : Integer) |linha : integer|

## Parâmetros:

Linha: Determina qual linha será obtida:

1 - Linha 1

2 - Linha 2

3 - Linha 3

4 - Linha 4

5 - Linha 5

6 - Linha 6

Dias: Período considerado.

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "nTendencyTracker", o retorno da linha 1 do indicador, considerando 5 períodos para o cálculo.

## nTendencyTracker:= TendencyTracker(5)|1|;

## Função Tilson

## Descrição:

A função Tilson retorna o valor do indicador Tillson's T3 Moving Average , de acordo com os parâmetros desejados.

## Sintaxe:

Tilson(Fator : Float, Media : Integer)

## Parâmetros:

Fator: Determina o Fator para formação do cálculo. Media: Período utilizado no momento do cálculo do indicador.

## Retorno:

Float

## Exemplos:

No exemplo, a variável "nTilson" irá receber o valor do indicador Tillson's T3 Moving Average, considerando 0.7(Fator) e 3(Media) para o cálculo.

## nTilson := Tilson(0.7, 3);

## Função TimeAgrBuySell

## Descrição:

A função TimeAgrBuySell retorna o valor do indicador TR - Tempo Agressão - Compra .

## Sintaxe:

TimeAgrBuySell(AlertaVariacoes : Integer)

## Parâmetros:

AlertaVariacoes: Quantidade de variações que serão consideradas.

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "alertV" o retorno da função, considerando 3 variações.

## alertV := TimeAgrBuySell(3);

## Função TimeAgrTotal

## Descrição:

A função TimeAgrTotal retorna o valor do indicador TR - Tempo Agressão - Total .

## Sintaxe:

TimeAgrTotal(AlertaVariacoes : Integer)

## Parâmetros:

AlertaVariacoes: Quantidade de variações que serão consideradas.

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "alertT" o retorno da função, considerando 3 variações.

## alertT := TimeAgrTotal(3);

## Função TopBottomDetector

## Descrição:

A função TopBottomDetector retorna o valor do indicador Detector de Topos e Fundos, de acordo com o período desejado.

## TBD := TopBottomDetector(2);

## Função Trades

## Sintaxe:

TopBottomDetector(Periodo : Integer)

## Parâmetros:

Periodo: Período utilizado no momento do cálculo do indicador.

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "TBD" o valor do indicador Detector de Topos e Fundos, considerando 2 período para o cálculo.

## Descrição:

A função Trades retorna o valor do indicador Negócios .

## Sintaxe:

Trades

## Parâmetros:

Sem parâmetros.

## Retorno:

Float

## Exemplos:

No exemplo, a variável "n" irá receber o dado do indicador Negócios.

## n := Trades;

## Função TrendCloud

## Descrição:

A função TrendCloud retorna o valor do indicador TrendCloud , de acordo com os parâmetros desejados.

## Sintaxe:

TrendCloud (DiasRetroativos : Integer; CorCompra : Integer; VWAP : Integer; CorVenda : Integer)

## Parâmetros:

DiasRetroativos: Período utilizado no momento do cálculo do indicador.

CorCompra : Determina qual média será considerada

- 1 - Verde
- 2 - Azul

VWAP : Utilização de VWAP.

- 1 - Ligado
- 2 - Desligado

CorVenda :

Determina qual média será considerada

- 1 - Vermelho
- 2 - Fucsia

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "nTrendCloud", o retorno do indicador.

## nTrendCloud:= nTrendCloud(7, 2, 2, 3);

## Função TrendSniper

## Descrição:

A função TrendSniper retorna o valor do indicador TrendSniper , de acordo com os parâmetros desejados.

## Sintaxe:

TrendSniper(DiasRetroativos : Integer; VWAP : Integer; CorCompra : Integer; CorVenda : Integer; Reversao : Integer)

## Parâmetros:

DiasRetroativos: Período utilizado no momento do cálculo do indicador.

VWAP :

- Utilização de VWAP.
- 1 - Ligado
- 2 - Desligado

CorCompra : Determina qual média será considerada

- 1 - Verde
- 2 - Azul

CorVenda : Determina qual média será considerada

- 1 - Vermelho
- 2 - Fucsia

Reversao : Determina qual média será considerada

- 1 - Ligado
- 2 - Desligado

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "nTrendSniper", o retorno do indicador.

## nTrendSniper := TrendSniper(7, 2, 2, 3, 2);

## Função TRIX

## Descrição:

A função TRIX retorna o valor do indicador TRIX , de acordo com o período e tipo de média desejados.

## Sintaxe:

TRIX(Media : Integer, TipoMedia : Integer)

## Parâmetros:

Media: Período utilizado no momento do cálculo do indicador.

TipoMedia: Determina qual média será considerada:

- 0 - Aritmética
- 1 - Exponencial
- 2 - Welles Wilder
- 3 - Ponderada

## Retorno:

Float

## Exemplos:

No exemplo, a variável "nTrix" irá receber o valor do indicador TRIX, considerando 9(Média) períodos e tipo exponecial para o cálculo.

## nTrix := TRIX(9, 1);

## Função TRIXM

## Descrição:

A função TRIXM retorna o valor do indicador TRIXM , de acordo com o período e tipo de média desejados.

## Sintaxe:

TRIXM(Media : Integer, TipoMedia : Integer)

## Parâmetros:

Media: Período utilizado no momento do cálculo do indicador.

TipoMedia: Determina qual média será considerada:

- 0 - Aritmética
- 1 - Exponencial
- 2 - Welles Wilder
- 3 - Ponderada

## Retorno:

Float

## Exemplos:

## nTrixm := TRIXM(9, 1);

## 2mvAgressao := TwoMVAggression;

No exemplo, a variável "nTrixm" irá receber o valor do indicador TRIXM, considerando 9(Média) períodos e tipo exponecial para o cálculo.

## Função TwoMVAggression

## Descrição:

A função TwoMVAggression retorna o dado do indicador 2MV Agressão .

## Sintaxe:

TwoMVAggression

## Parâmetros:

Sem parâmetros

## Retorno:

Float(Dado Obtido):

## Exemplos:

No exemplo, será atribuído o retorno da função na variável "2mvAgressao".

## Função TwoMVPower

## Descrição:

A função TwoMVPower retorna o valor do indicador 2MV Power , de acordo com os parâmetros desejados.

## Sintaxe:

TwoMVPower(Periodo1 : Integer, Periodo2 : Integer, Periodo3 : Integer, Media : Integer)

## Parâmetros:

Periodo1: Período em minutos utilizado no momento do cálculo do indicador.

Periodo2: Período em minutos.

Periodo3: Período em minutos.

Media: Período determinado para a média.

## Retorno:

## Float(Dado Obtido):

-1 - Baixa

0 - Neutro

1 - Alta

## Exemplos:

No exemplo, caso ocorra a flag de alta, será aplicada uma coloração(verde).

if(TwoMVPower(2, 5, 15, 20) = 1) then

PaintBar(clGreen)

;

## Função TwoMvVolatility

## Descrição:

Indicador criado para auxiliar na visualização do funcionamento do modo volatilidade do robô 2MV.

## Sintaxe:

TwoMvVolatility(Factorpos : Float; Factorneg : Float; Aggr : Integer)

## Parâmetros:

Factorpos: Parâmetro relacionado ao campo factorpos do indicador. Factorneg :  Parâmetro relacionado ao campo factorneg do indicador. Aggr: Relacionado ao campo aggr do indicador.

## Retorno:

## Float

## Exemplos:

## Função UltimateOscillator

## Descrição:

A função UltimateOscillator retorna o valor do Ultimate Oscillator desenvolvido por Larry Williams.

## Sintaxe:

UltimateOscillator(PeriodoCurto

: Integer, PeriodoMedio : Integer, PeriodoLongo : Integer)

## Parâmetros:

PeriodoCurto: Período curto utilizado no momento do cálculo.

PeriodoMedio: Período médio para o cálculo.

PeriodoLongo: Período longo para o cálculo.

## Retorno:

Float

## Exemplos:

No exemplo, a variável "aux" irá receber o retorno da função UltimateOscillator, considerando 5(PeriodoCurto), 8(PeriodoMedio) e 12(PeriodoLongo) para o cálculo.

## aux := UltimateOscillator(5, 8, 12);

## Função Valerie

## Descrição:

A função Valerie retorna o valor do indicador Valerie , conforme os parâmetros desejados.

## Sintaxe:

Valerie(Periodo : Integer; Offset : Integer)

## Parâmetros:

Periodo: Período utilizado no cálculo do indicador. Offset : Offset considerado.

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "nValerie", o retorno da chamada, considerando 45 períodos, e 5 para o Offset.

## nValerie:= Valerie(45, 5);

## Função VolumeAgent

## Descrição:

A função VolumeAgent retorna o volume financeiro filtrado por agente . Retorna os dados em tempo real, não executando em backtest.

*Exclusivo Profit Ultra

## Sintaxe:

VolumeAgent(AgentID : Integer, Período : Integer )

## Parâmetros:

AgentID: ID do agente na B3.

Período: Determina qual tipo de cálculo do volume será obtido:

- 0 - Retorna o volume diário, não importando o tempo gráfico onde está executando.
- 1 - Retorna o volume candle a candle.

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "aux" o retorno da função, a constante AgentID terá como filtro o agente 3 e o volume será diário.

const

AgentID = 3;

var

aux : Float;

begin

aux := VolumeAgent(AgentID, 0);

end;

## Função VSS

## Descrição:

A função VSS retorna o valor do indicador VSS , de acordo com os parâmetros desejados.

## Sintaxe:

VSS(Multiplicador : Float, Media : Integer, Deslocamento : Integer)

## Parâmetros:

Multiplicador: : Valor de Multiplicador utilizado no cálculo do indicador.

Media: Período da média utilizada.

Deslocamento: Deslocamento de períodos.

## Retorno:

Float

## Exemplos:

No exemplo, a variável "nVSS" irá receber o valor do indicador VSS, considerando 1.5(Multiplicador), 5(Média) períodos e 0(Deslocamento) para o cálculo.

## nVSS := VSS(1.5, 5, 0);
