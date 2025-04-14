# Lista de Funções
A seguir de forma descritiva, segue a lista de funções presentes nas plataformas da Nelogica:

## Alarme

### Alert(Cor : Integer)
Dispara uma notificação de alarme.

## Back-Testing

### BuyAtMarket
Realiza envio de ordem de compra a mercado.

### BuyLimit(Preco : Float; Quantidade : Float= '')
Realiza envio de uma ordem limite de compra.

### BuyPosition
Retorna o tamanho da posição da compra.

### BuyPrice
Retorna o preço de compra da posição.

### BuyStop(Stop : Float; Limite : Float; Quantidade : Float = '')
Realiza envio de ordem de compra stop.

### BuyToCoverAtMarket
Realiza o fechamento de uma operação de venda.

### BuyToCoverLimit(Preco : Float; Quantidade : Float = '')
Envia uma ordem de compra limite para fechar a operação.

### BuyToCoverStop(Stop : Float; Limite : Float; Quantidade : Float = '')
Realiza o envio de ordem de compra stop para fechar posição.

### CancelPendingOrders
Cancela as ordens pendentes.

### ClosePosition
Envia ordens para encerrar todas as posições.

### HasPendingOrders
Retorna verdadeiro (True) caso existam ordens pendentes.

### HasPosition
Retorna verdadeiro se a posição não é zero.

### IsBought
Retorna verdadeiro (True) caso exista posição de compra.

### IsSold
Retorna verdadeiro (True) caso exista posição de venda.

### MyPrice
Retorna a média entre a máxima, mínima e fechamento.

### Position
Retorna o tamanho da posição, positivo para compra e negativo para venda.

### Price
Retorna o preço de compra ou venda da posição, dependendo se estiver comprado ou vendido.

### ReversePosition
Envia ordens para inverter a posição.

### SellPosition
Retorna o tamanho da posição de venda.

### SellPrice
Retorna o preço de venda da posição.

### SellShortAtMarket
Envia ordem de venda a mercado para abrir posição.

### SellShortLimit(Preco : Float; Quantidade : Float = '')
Envia ordem de venda do tipo limite.

### SellShortStop(Stop : Float, Limite : Float; Quantidade : Float = '')
Abre uma posição de venda enviando uma ordem do tipo Stop.

### SellToCoverAtMarket
Realiza uma ordem de venda a mercado caso exista uma posição de compra.

### SellToCoverLimit(Preco : Float; Quantidade : Float = '')
Envia uma ordem de venda limite para fechar a operação.

### SellToCoverStop(Stop : Float, Limite : Float; Quantidade : Float = '')
Envia uma ordem stop caso exista uma posição de compra.

### SendOrder(Lado : Integer, Tipo : Integer, Quantidade : Float , Limite : Float, Stop : Float)
Envia uma ordem customizada.

### DailyResult(OpenResult : Boolean)
Retorna o resultado diário

OpenResult : Retorna o resultado diário das operações em aberto

### XRay(strName : String, bValue : Boolean, strGroup : String, dValue : Float, ColorOn : Color, ColorOff : Color)
Adiciona uma variável a lista do Raio-X da automação

## Depuração

### ConsoleLog(Content : String, Color : Integer = clBlack)
Imprime uma string no terminal de console para ajudar na depuração do código.

# Calendário

## BarAnnualization
Retorna o fator de anualização, baseado no intervalo da barra.

## BarDuration
Retorna, em minutos, a duração da barra atual.

## BarDurationF
Retorna, em minutos, a duração da barra atual.

## BarType
Retorna um número referente à periodicidade setada.

## CalcDate(DataReferencia : Integer, DiasDeslocamento : Integer)
Retorna o resultado ao efetuar a adição ou subtração de datas.

## CalcTime(HoraReferencia : Integer, MinutosDeslocamento : Integer)
Retorna o cálculo de adição ou subtração de horas.

## CloseD(QuantidadeDiasAnteriores : Integer)
Retorna o valor de fechamento de determinado dia anterior.

## CloseM(QuantidadeMesesAnteriores : Integer)
Retorna o valor de fechamento de determinado mês anterior.

## CloseW(QuantidadeSemanasAnteriores : Integer)
Retorna o valor de fechamento de determinada semana anterior.

## CloseY(QuantidadeAnosAnteriores : Integer)
Retorna o valor de fechamento de determinado ano anterior.

## CurrentAssetDate
Retorna a data atual do ativo no gráfico.

## CurrentDate
Retorna a data atual do sistema.

## CurrentTime
Retorna a hora atual do sistema.

## Date
Retorna a data da barra que está sendo analisada.

## DayOfMonth(Data : Integer)
Retorna o dia do mês de uma data específica.

## DayOfWeek(Data : Integer)
Retorna o dia da semana de uma data específica.

## DaysToExpiration(Mes : Integer, Ano : Integer)
Retorna a quantidade de dias úteis restantes até a terceira sexta-feira de um determinado mês e ano.

## ELDate(Ano : Integer, Mes : Integer, Dia : Integer)
Retorna a data em EasyLanguage format(YYYMMDD).

## ELDate_Consol(Data : Integer)
Transforma uma data YYYYMMDD em EasyLanguage format(YYYMMDD).

## FindBar(Data : Integer, Hora : Integer)
Localiza uma barra de uma data e hora específica.

## Friday
Retorna o número 5 referente ao dia da semana: sexta-feira.

## HighestVolume(Interval : Integer; Offset : Integer = 1; Type : Integer = 0; Standard : Boolean = True; Auction : Boolean = True; Cross : Boolean = True)
Retorna o maior volume de acordo com o tipo.

## HighestVolumePrice(Interval : Integer; Offset : Integer = 1; Type : Integer = 0; Standard : Boolean = True; Auction : Boolean = True; Cross : Boolean = True)
Retorna o preço do maior volume de acordo com o tipo.

## HighD(QuantidadeDiasAnteriores : Integer)
Retorna o valor de máxima de determinado dia retroativo.

## HighM(QuantidadeMesesAnteriores : Integer)
Retorna o valor de máxima de determinado mês retroativo.

## HighW(QuantidadeSemanasAnteriores : Integer)
Retorna o valor de máxima de determinada semana anterior.

## HighY(QuantidadeAnosAnteriores : Integer)
Retorna o valor de máxima de determinado ano anterior.

## LastCalcDate
Retorna a data do último candle completo do gráfico.

## LastCalcTime
Retorna o horário de fechamento do último candle.

## LastDayOfMonth(MesReferencia : Integer)
Retorna o valor do último dia do mês de referência.

## LowD(QuantidadeDiasAnteriores : Integer)
Retorna o valor de mínima de determinado dia anterior.

## LowM(QuantidadeMesesAnteriores : Integer)
Retorna o valor de mínima de determinado mês anterior.

## LowW(QuantidadeSemanasAnteriores : Integer)
Retorna o valor de mínima de determinada semana anterior.

## LowY(QuantidadeAnosAnteriores : Integer)
Retorna o valor de mínima de determinado ano anterior.

## MinutesIntoWeek
Retorna o número de minutos até domingo 12 am.

## Monday
Retorna o número 1 referente ao dia da semana: segunda-feira.

## Month(Date : Integer)
Retorna o mês de uma data específica.

## Next3rdFriday(Mes : Integer)
Retorna quantos dias úteis faltam para a terceira sexta-feira de determinado mês.

## OpenD(QuantidadeDiasAnteriores : Integer)
Retorna o valor de abertura de determinado dia anterior.

## OpenM(QuantidadeMesesAnteriores : Integer)
Retorna o valor de abertura de determinado mês anterior.

## OpenW(QuantidadeSemanasAnteriores : Integer)
Retorna o valor de abertura de determinada semana anterior.

## OpenY(QuantidadeAnosAnteriores : Integer)
Retorna o valor de abertura de determinado ano anterior.

## RS_BarsPerDay
Obtém o número estimado de barras de determinada periodicidade(em minutos).

## Saturday
Retorna o número 6 referente ao dia da semana: sábado.

## Sunday
Retorna o número 0 referente ao dia da semana: domingo.

## Thursday
Retorna o número 4 referente ao dia da semana: quinta-feira.

## Time
Retorna a hora de abertura da barra atual.

## TimeToMinutes(Hora : Integer)
Converte um horário em minutos.

## Today
Retorna a data atual do sistema.

## Tuesday
Retorna o número 2 referente ao dia da semana: Terça-feira.

## VolumeAtPrice(Interval : Integer; Offset : Integer = 1; Type : Integer = 0; Standard : Boolean = True; Auction : Boolean = True; Cross : Boolean = True)
Retorna o volume financeiro em determinado preço.

## VolumeD(QuantidadeDiasAnteriores : Integer)
Retorna o volume financeiro de determinado dia retroativo.

## VolumeM(QuantidadeMesesAnteriores : Integer)
Retorna o volume financeiro de determinado mês retroativo.

## VolumeW(QuantidadeSemanasAnteriores : Integer)
Retorna o volume financeiro de determinada semana anterior.

## VolumeY(QuantidadeAnosAnteriores : Integer)
Retorna o volume financeiro de determinado ano anterior.

## Wednesday
Retorna o número 3 referente ao dia da semana: Quarta-feira.

## Year(Date : Integer)
Retorna o ano de uma data específica.

# Candlestick

## C_3WhSolds_3BlkCrows(Comprimento : Integer, Fator : Integer, var o3WhiteSoldiers : Integer, var o3BlackCrows : Integer)
Identifica a ocorrência de dois tipos de candles: 3 White Soldiers e 3 Black Crows.

## C_BullEng_BearEng(Comprimento : Integer, var oBullishEngulfing: Integer, var oBearishEngulfing : Integer)
Identifica a ocorrência de dois tipos de candles: Bullish Engulfing e Bearish Engulfing.

## C_Doji(Percentual : Integer)
Identifica a ocorrência de um candle: Doji.

## C_Hammer_HangingMan(Comprimento : Integer, Fator : Integer, var oHammer : Integer, var oHangingMan : Integer)
Identifica a ocorrência de dois tipos de candles: Hammer e Hanging Man.

## C_MornDoji_EveDoji(Comprimento : Integer, Percentual : Float, var oMorningDojiStar : Integer, var oEveningDojiStar : Integer)
Identifica a ocorrência de dois tipos de candles: Morning Doji Star e Evening Doji Star.

## C_MornStar_EveStar(Comprimento : Integer, var oMorningStar : Integer, var oEveningStar : Integer)
Identifica a ocorrência de dois tipos de candles: Morning Star e Evening Star.

## C_PierceLine_DkCloud(Comprimento : Integer, var oPiercingLine : Integer, var oDarkCloud : Integer)
Identifica a ocorrência de dois tipos de candles: Piercing Line e Dark Cloud.

## C_ShootingStar(Comprimento : Integer, Fator : Integer)
Identifica a ocorrência de candles: C_ShootingStar.

# Exemplos

## DiMaisDiMenos(Periodo : Integer)
Exemplo de implementação do indicador DI+/DI-.

## IFR(Periodo : Integer)
Exemplo de implementação do indicador IFR.

# Gráficas

## Media(Periodo : Integer, TipoSerie : Serie)
Exemplo de implementação do indicador Média Móvel(Aritmética).

## MediaExp(Periodo : Integer, TipoSerie : Serie)
Exemplo de implementação do indicador Média Móvel(Exponencial).

## PaintVar
Exemplo de implementação de estratégia de coloração.

## WellesSum(Periodo : Integer, SerieReferencia : Serie, Offset : Integer)
Exemplo de implementação do indicador WellesSum.

## AvgPrice
Retorna a média entre Abertura, Máxima, Mínima, Fechamento de determinado candle.

## BarCount
Retorna a quantidade total de barras.

## CurrentBar
Retorna o índice atual da barra(candle).

## GetPlotColor(NumeroPlot : Integer)
Retorna o valor numérico da cor de determinado Plot.

## GetPlotWidth(NumeroPlot : Integer)
Retorna o valor da espessura de determinado Plot.

## GraphicInterval
Retorna o intervalo do gráfico.

## GraphicOffset
Retorna o offset do gráfico.

## HorizontalLine(Y : Float; Color : Integer)
Adiciona um estudo horizontal, em um indicador.

## LastBarOnChart
Retorna se é a última barra do gráfico.

## Leader
Retorna se ponto médio é menor que mínima ou maior que máxima de candle anterior.

## MaxBarsBack
Percorre a lista da série, a partir do primeiro candle criado(índice 0).

## MaxBarsForward
Percorre a lista da série, a partir do candle atual(índice 0).

## MedianPrice
Retorna a média entre a máxima e a mínima de determinado candle.

## NoPlot(NumeroPlot : Integer)
Remove determinado Plot.

## PaintBar(Cor : Integer)
Colore os candles e indicadores do gráfico.

## Plot(Dado : Float)
Desenha o indicador de acordo com o gráfico.

## PlotN(Plot : Integer; Valor : Float)
Adiciona um valor em um indicador.

## PlotText(Content : String; Color : Integer; Position : Integer; FontSize : Integer; dPrice : Float)
Adiciona um texto a um indicador.

## Range
Retorna o valor de Máxima menos Mínima do determinado candle.

## RangeLeader
Verifica se a barra atual é Range Leader.

## RGB(Red : Integer, Green : Integer, Blue : Integer)
Coloração a partir dos parâmetros RGB.

## SetPlotColor(NumeroPlot : Integer, Cor : Integer)
Altera a coloração de determinado Plot.

## SetPlotStyle(NumeroPlot : Integer; Estilo : Integer)
Altera o estilo da linha de um plot específico.

## SetPlotType(Number : Integer; Type : Integer)
Altera o tipo de gráfico de determinado plot.

## SetPlotWidth(NumeroPlot : Integer, Espessura : Integer)
Altera a espessura de determinado Plot.

## TrueHigh
Retorna o maior entre o máximo da barra e o fechamento da barra anterior.

## TrueLow
Retorna o menor entre o mínimo da barra e o fechamento da barra anterior.

## TrueRange
Retorna o valor do indicador TrueRange.

## TrueRangeCustom(Maxima : Float, Minima : Float, Fechamento : Float)
Retorna o TrueRange de acordo com os dados informados pelo usuário.

## TypicalPrice
Retorna o valor médio entre a máxima, mínima e fechamento de determinado candle.

## VerticalLine(X : Integer; Color : Integer)
Adiciona um estudo vertical em um indicador.

## WeightedClose
Retorna a média entre o ponto médio da barra e dois fechamentos.

# Indicadores

## AccAgressSaldo(TipoVolume : Integer)
Retorna o valor do indicador TR - Acúmulo de Agressão - Saldo.

## AccuDistr
Retorna o valor do indicador Acumulação/Distribuição.

## AccuDistrW
Retorna o valor do indicador Acumulação/Distribuição Williams.

## AdaptiveMovingAverage(Periodo : Integer, FastSC : Integer, SlowSC : Integer)
Retorna o valor do indicador Adaptive Moving Average(AMV).

## ADX(Periodo : Integer, PeriodoMedia : Integer)
Retorna o valor do indicador ADX.

## AgressionVolBalance
Retorna o valor do indicador TR - Volume de Agressão - Saldo.

## AgressionVolBuy
Retorna o valor do indicador TR - Volume de Agressão - Compra.

## AgressionVolSell
Retorna o valor do indicador TR - Volume de Agressão - Venda.

## ArmsEaseOfMov(Media : Integer, TipoMedia : Integer)
Retorna o valor do indicador Arms Ease of Movement.

## AroonLin(Periodo : Integer)|Linha Desejada|
Retorna o valor do indicador Aroon Linha.

## AroonOsc(Periodo : Integer)
Retorna o valor do indicador Aroon Oscilador.

## AvgAgrBuySell(AlertaVariacoes : Integer, TipoVolume : Integer, TipoDesenho: Integer)|Linha : Integer|
Retorna o valor do indicador TR - Agressão Média - Compra e Venda.

## AvgAgrTotal(AlertaVariacoes : Integer, TipoVolume : Integer, TipoDesenho: Integer)|Linha : Integer|
Retorna o valor do indicador TR - Agressão Média - Total.

## AvgSeparation(Periodo : Integer, TipoMedia : Integer)
Retorna o valor do indicador Afastamento Médio.

## AvgTrueRange(Periodo : Integer, TipoMedia : Integer)
Retorna o valor do indicador True Range.

## BalanceOfPower(Media : Integer, TipoMedia : Integer)
Retorna o valor do indicador Balança do poder.

## BearPower(Periodo : Integer)
Retorna o valor do indicador Bear Power.

## BollingerBands(Desvio : Float, Media : Integer, TipoMedia : Integer)|Linha : Integer|
Retorna o valor da linha da Banda de Bollinger de acordo com a linha desejada.

## BollingerBandW(Desvio : Float, Media : Integer, TipoMedia : Integer)
Retorna o valor do indicador Bollinger Band Width.

## BollingerBPerc(Desvio : Float, Media : Integer, TipoMedia : Integer)
Retorna o valor do indicador Boolinger b%.

## BullPower(Periodo : Integer, PeriodoMedia : Integer, TipoMedia : Integer)
Retorna o valor do indicador Bull Power.

## CCI(Periodo : Integer)
Retorna o valor do indicador CCI.

## ChaikinMoneyFlow(Periodo : Integer)
Retorna o valor do indicador Chaikin Money Flow.

## ChaikinOsc(MediaLonga: Integer, MediaCurta : Integer)
Retorna o valor do indicador Oscilador Chaikin.

## ChainSetup
Retorna o dado do indicador ChainSetup.

## CohenPriceWave(Ticks : Integer)
Desenvolvido por Rodrigo Cohen e equipe, indica a diferença absoluta de preços de cada swing do ativo.

## CohenWeisWave(Ticks : Integer)
Desenvolvido por Rodrigo Cohen e equipe, indica a soma do volume de cada swing do ativo. Serve como um indicador de exaustão.

## ContadorDeCandle
Contabiliza e sinaliza de forma numérica e organizada no gráfico o número de cada candle.

## DarvasBox|Linha : Integer|
Retorna o valor do indicador Darvas Box.

## DecisionPoints(Tipo : Integer, Linha : Integer)
Retorna o valor do indicador Pontos de Decisão.

## DiDiIndex(MedRef : Integer, TipoMedRef : Integer, Med1 : Integer, TipoMed1 : Integer, Med2 : Integer, TipoMed2 : Integer)|Linha : Integer|
Retorna o valor do indicador DiDi Index.

## DiPDiM(Periodo : Integer)|Linha : Integer|
Retorna o valor do indicador DI+/DI- de acordo com a linha desejada.

## DonchianCH(Periodo : Integer)|Linha : Integer|
Retorna o valor do indicador Canal Donchian de acordo com a linha desejada.

## DTOscillator(PeriodoEstocastico : Integer, PeriodoSK : Integer, TipoSK : Integer, PeriodoSD : Integer, TipoSD : Integer)|Linha : Integer|
Retorna o valor do indicador DT Oscillator, de acordo com a linha desejada.

## Envelope(Percentual : Float, PeriodoMedia : Integer, TipoMedia : Integer)|Linha : Integer|
Retorna o valor do indicador Envelope.

## Euroinvest(Risco: Integer, ModoCalculo : Integer, Periodo : Integer, Desvio : Float, UsarVWAP : Boolean, UsarAtr : Boolean)
Retorna o valor do indicador Euroinvest.

## FastStochastic(Periodo : Integer, PeriodoMedia : Integer, TipoMedia : Integer)
Retorna o valor do indicador Estocástico Rápido.

## FinancialVol(VolumeProjetado : Boolean, Agressores : Boolean)
Retorna o Valor do volume financeiro.

## ForceIndex(Periodo : Integer, TipoMedia : Integer)
Retorna o valor do indicador Force Index.

## FrassonATR(Fator : Float, PeriodoMaxMin : Integer, PeriodoATR : Integer)|Linha : Integer|
Retorna o valor do indicador Frasson ATR.

## FrassonVH(Fator : Float, PeriodoMaxMin : Integer, PeriodoVH : Integer)|Linha : Integer|
Retorna o valor do indicador Frasson VH.

## FullStochastic(Periodo : Integer)
Retorna o valor do indicador Estocástico Pleno.

## FuraChao(Coeficiente : Float, Deslocamento : Integer)
Retorna o valor do indicador Fura Chão.

## FuraTeto(Coeficiente : Float, Deslocamento : Integer)
Retorna o valor do indicador Fura Teto.

## HeikinAshi(Media : Integer, TipoMedia : Integer)|Dado : Integer|
Retorna o valor do indicador HeikinAshi.

## HiLoActivator(Periodo : Integer)|Linha : Integer|
Retorna o valor do HiLo Activator de acordo com a linha desejada.

## HistVolatility(Periodo : Integer, TipoMedia : Integer)
Retorna o valor do indicador Volatilidade Histórica.

## HSI(Periodo : Integer)
Retorna o valor do indicador IFR Índice de Força Harmônico (HSI).

## HullMovingAverage(Periodo : Integer)
Retorna o valor do indicador Hull Moving Average.

## IchimokuCloud(TenkanSen : Integer, KijunSen : Integer, SenkouSpanB : Integer)|Linha : Integer|
Retorna o valor do indicador Ichimoku Cloud.

## IFR(Periodo : Integer)
Retorna o valor do indicador IFR.

## ImpliedVolatility(ModeloTeorico : Boolean, TipoOpcao : Boolean)
Retorna o cálculo do indicador Volatilidade Implícita, dependendo do tipo de cálculo utilizado.

## KeltnerCH(Desvio : Float, Periodo : Integer, TipoMedia : Integer)|Linha : Integer|
Retorna o valor do indicador Keltner Chanels, conforme com a linha desejada.

## KVO(MediaLonga : Integer, MediaCurta : Integer, Sinal : Integer)|Dado : Integer|
Retorna o dado desejado do indicador KVO Linha & Histograma.

## LinearRegressionChannel(Periodo : Integer; UsarDesvioSuperior : Boolean; DesvioSuperior : Float; UsarDesvioInferior : Boolean; DesvioInferior : Float)
Canal de regressão linear

## LSVolatilityIndex
Retorna o dado desejado do indicador L&S Volatility Index.

## MACD(MediaLonga : Integer, MediaCurta : Integer, Sinal : Integer)|Dado : Integer|
Retorna o dado desejado do indicador KVO Linha & Histograma.

## Media(Periodo : Integer, TipoSerie : Serie)
Retorna o dado do indicador Média Móvel(Aritmética).

## MediaExp(Periodo : Integer, TipoSerie : Serie)
Retorna o dado do indicador Média Móvel(Exponencial).

## MFI
Retorna o valor do indicador Market Facilitation Index.

## MIMA(Periodo : Integer)
Retorna o dado do indicador PhiCube - MIMA.

## MIMAROC(Periodo : Integer)
Retorna o dado do indicador PhiCube - MIMAROC.

## Momentum(Periodo : Integer, Media : Integer, TipoMedia : Integer)
Retorna o valor do indicador Momentum.

## MomentumStochastic(Periodo : Integer)
Retorna o valor do indicador Momento Estocástico.

## MoneyFlow
Retorna o valor do indicador Money Flow.

## MoneyFlowIndex(Periodo : Integer)
Retorna o valor do indicador Money Flow Index de acordo com o período utilizado.

## NelogicaBottomFinder|Dado : Integer|
Retorna o valor do indicador Nelogica Bottom Finder de acordo com a linha Desejada.

## NelogicaPullBackFinder|Dado : Integer|
Retorna o valor do indicador Nelogica PullBack Finder de acordo com a linha desejada.

## NelogicaWeisWave(Periodo : Integer)
Retorna o valor do indicador Nelogica Weis Wave, conforme o período desejado.

## OBV
Retorna o valor do indicador OBV.

## OBVAvg
Retorna o valor do indicador OBV Ponderado.

## OnBalanceTR
Retorna o valor do indicador On Balance True Range.

## OpenDaily(DaysBack : Integer)
Retorna o dado de abertura, conforme o deslocamento especificado.

## OpenInterest
Retorna o valor do indicador Contratos em aberto.

## ParabolicSAR(Fator : Float, Limite : Float)
Retorna o valor do indicador SAR Parabólico.

## Phibo(Periodo : Integer)
Retorna o valor do indicador PhiCube - Phibo Line.

## Pivot(Normal : Boolean, TresLinhas : Boolean)|Linha : Integer|
Retorna o valor do indicador Pivot, de acordo com a linha selecionada.

## PowerMeter(Side : Integer, Minutes : Integer = 0, InitialDate : Integer = 0, EndDate : Integer = 0)
Retorna os dados do indicador PowerMeter(Medidor de Pressão), informa a quantidade do Agressor Comprador ou do Agressor Vendedor, dependendo dos parâmetros fornecidos.

## PriceNery
Retorna os dados do indicador Price Nery.

## PriceOsc(Media1 : Integer, TipoMedia1 : Integer, Media2 : Integer, TipoMedia2 : Integer)
Retorna o valor do indicador Oscilador de Preços.

## PriceVolumeTrend
Retorna o valor do indicador Tendência Preço/Volume.

## PriorCote(Dado : Integer)
Retorna o valor do indicador Prior Cote, de acordo com o dado desejado.

## PTAX
Retorna o valor do indicador TR - PTAX.

## PTAXFuturo
Retorna o valor do indicador TR - PTAX Futuro.

## QuantityVol(VolumeProjetado : Boolean, Agressores : Boolean)
Retorna o valor do indicador Volume Quantidade.

## Rafi
Retorna o valor do indicador Rafi.

## Ravi(MediaCurta : Integer, MediaLonga : Integer)
Retorna o valor do indicador Ravi, de acordo com os períodos das médias desejadas.

## RBG
Retorna os dados do indicador RBG.

## RenkoVTwo(Periodo : Integer, Abertura : Float, Deslocamento : Integer)
Retorna o dado do indicador RenkoV2, conforme a linha desejada.

## ROC(Periodo : Integer, Media : Integer, TipoMedia : Integer)
Retorna o valor do indicador ROC.

## RSI(Periodo : Integer, Tipo : Integer)
Retorna o valor do indicador IFR(RSI).

## RsiStochastic(Periodo : Integer)
Retorna o valor do indicador IFR Estocástico.

## SafeZoneDownTrend(Multiplicador : Float, Periodo : Integer, Deslocamento : Integer)
Retorna o valor do indicador Stop SafeZone DownTrend.

## SafeZoneUpTrend(Multiplicador : Float, Periodo : Integer, Deslocamento : Integer)
Retorna o valor do indicador Stop SafeZone UpTrend.

## Santo(Periodo : Integer)|Linha : Integer|
Retorna o valor do indicador PhiCube - Santo.

## SlowStochastic(Periodo : Integer)
Retorna o valor do indicador Estocástico Lento.

## SOMOSRENKOTRENDMPONTO|Linha : Integer|
Retorna o valor do indicador SomoRenko - SR_MPONTO, de acordo com a linha desejada.

## StopATR(Desvio : Float, Periodo : Integer, TipoMedia : Integer)|Dado : Integer|
Retorna o valor do indicador Stop ATR, de acordo com o dado desejado.

## TendencyTracker(Dias : Integer)
Retorna o valor do indicador Rastreador de Tendências, conforme o período desejado.

## Tilson(Fator : Float, Media : Integer)
Retorna o valor do indicador Tillson's T3 Moving Average.

## TimeAgrBuySell(AlertaVariacoes : Integer)
Retorna o valor do indicador TR - Tempo Agressão - Compra.

## TimeAgrTotal(AlertaVariacoes : Integer)
Retorna o valor do indicador TR - Tempo Agressão - Total.

## TopBottomDetector(Periodo : Integer)
Retorna o valor do indicador Detector de Topos e Fundos.

## Trades
Retorna o valor do indicador Negócios.

## TrendCloud(DiasRetroativos : Integer; CorCompra : Integer; VWAP : Integer; CorVenda : Integer)
Retorna o valor do indicador TrendCloud, de acordo com os parâmetros desejados.

## TrendSniper(DiasRetroativos : Integer; VWAP : Integer; CorCompra : Integer; CorVenda : Integer; Reversao : Integer)
Retorna o valor do indicador TrendSniper, de acordo com os parâmetros desejados.

## TRIX(Media : Integer, TipoMedia : Integer)
Retorna o valor do indicador TRIX.

## TRIXM(Media : Integer, TipoMedia : Integer)
Retorna o valor do indicador TRIXM.

## TwoMVAggression
Retorna o dado do indicador 2MV Agressão.

## TwoMVPower(Periodo1 : Integer, Periodo2 : Integer, Periodo3 : Integer, Media : Integer)
Retorna o valor do indicador 2MV Power.

## TwoMVStandard
Retorna o dado do indicador 2MV Padrão.

## UltimateOscillator(PeriodoCurto: Integer, PeriodoMedio : Integer, PeriodoLongo : Integer)
Retorna o valor do Ultimate Oscillator desenvolvido por Larry Williams.

## Valerie(Periodo : Integer; Offset : Integer)
Retorna o valor do indicador Valerie, conforme os parâmetros desejados.

## VSS(Multiplicador : Float, Media : Integer, Deslocamento : Integer)
Retorna o valor do indicador VSS.

## VWAP(Periodo : Integer)
Retorna o valor do indicador VWAP, conforme a periodicidade desejada.

## VWAPDate(Date : Integer; Time : Integer)(Periodo : Integer)
Retorna o preço médio ponderado pelo volume, a partir de uma data e horário específicos.

## VWAPMonthly
Retorna o dado do indicador VWMA Mensal.

## VWAPWeekly
Retorna o dado do indicador VWMA Semanal.

## VWMA(Periodo : Integer)
Retorna o dado do indicador VWMA, conforme o período desejado.

## WAverage(TipoSerie : SeriePeriodo, Periodo : Integer)
Retorna o dado do indicador Média Móvel(Ponderada).

## WellesSum(Periodo : Integer, SerieReferencia : Serie, Offset : Integer)
Retorna o dado do indicador WellesSum.

## Williams(Periodo : Integer)
Retorna o valor do indicador Williams %R, de acordo com o período desejado.

## xAverage(TipoSerie : SeriePeriodo, Periodo : Integer)
Retorna o dado do indicador Média Móvel(Exponencial).

# Livro

## AskPrice
Retorna o preço da melhor oferta de venda.

## AskSize
Retorna a quantidade da melhor oferta de venda.

## BidPrice
Retorna o preço da melhor oferta de compra.

## BidSize
Retorna a quantidade da melhor oferta de compra.

## BookSpread
Retorna a diferença entre o topo do livro.

## BuyOfferCount(Asset : Ativo = '', Preço Considerado : Integer = 0)
Retorna a quantidade de ofertas de compra do Ativo.

## GetAsset(Asset : Ativo = '')
Retorna o ticker do ativo

## GetFeed(Asset : Ativo = '')
Retorna o código textual do Feed do ativo.

## IsBMF
Verifica se o ativo pertence ao segmento BMF.

## Lote
Retorna a quantidade de contratos referente ao lote.

## MinPriceIncrement
Retorna o incremento mínimo do preço.

## SellOfferCount(Asset : Ativo = '', Preço Considerado : Integer = 0)
Retorna a quantidade de ofertas de venda do Ativo.

## TotalBuyQtd(Asset : Ativo = '', Preço Considerado : Integer = 0)
Retorna a quantidade de compras do Ativo.

## TotalSellQtd(Asset : Ativo = '', Preço Considerado : Integer = 0)
Retorna a quantidade de vendas do Ativo.

# Matemáticas

## ABS(Valor : Float)
Retorna o valor absoluto(sem sinal).

## Arctangent(Numero : Float)
Retorna o arcotangente(em graus) de um número.

## Ceiling(Numero : Float)
Retorna o menor inteiro maior que um número específico.

## Combination(Numero : Integer, QtdGrupos : Integer)
Retorna a quantidade de combinações, considerando um conjunto específico de números.

## Cos(Valor : Float)
Retorna o valor de um Cosseno em radianos.

## Cosine(Valor : Float)
Retorna o valor de um Cosseno em graus.

## Cotangent(Valor : Float)
Retorna o valor de uma Cotangente em graus.

## Cum(SerieDeDados : Serie)
Acumula o valor de uma série de dados.

## Exp(Valor : Float)
Retorna a enésima potência do número de Euler.

## ExpValue(Valor : Float)
Retorna o valor exponencial de um determinado número(e^x).

## ExtremePriceRatio
Obtém o ratio das extremidades de um número determinado de barras.

## Factorial(Valor : Float)
Retorna o fatorial do valor estabelecido (1*2*. n).

## FastD(Periodo : Integer)
Retorna o valor de FastD do Oscilador Estocástico.

## FastK(Periodo : Integer)
Retorna o valor de FastK do Oscilador Estocástico.

## FastKCustom(PrecoH : Serie, PrecoL : Serie, PrecoC : Serie, Periodo : Integer)
Retorna o valor de FastK a partir de preços específicos.

## Floor(Valor : Float)
Retorna o maior inteiro, menor que um número específico.

## FracPortion(Valor : Float)
Retorna a parte fracionário de um número.

## GCD(Valor1 : Float, Valor2 : Float)
Retorna o maior divisor comum entre dois números.

## HarmonicMean(SerieDados : Serie, Periodo : Integer)
Retorna a média harmônica de uma série de dados baseada em um período.

## Highest(SerieS Dados : Serie, Periodo : Integer)
Retorna o maior valor da série dentro do período.

## HighestBar(SerieDeDados : Serie, Periodo : Integer)
Retorna o índice do maior valor da série no período.

## IntPortion(Valor : Float)
Retorna a parte inteira de um número.

## Log(Valor : Float)
Retorna o logaritmo natural(ln) de um número de um número.

## Lowest(SerieDeDados : Serie, Periodo : Integer)
Retorna o menor valor da série dentro no período.

## LowestBar(SerieDeDados : Serie, Periodo : Integer)
Retorna o índice da barra com o menor valor da série no período.

## Max(Valor1 : Float, Valor2 : Float)
Retorna o maior valor entre dois números.

## MidPoint(SerieDados : Serie, Periodo : Integer)
Retorna a média entre o maior e o menor valor encontrados no período.

## Min(Valor1 : Float, Valor2 : Float)
Retorna o menor valor entre dois números.

## MinutesIntoWeek(DiaLimite : Integer, HoraLimite : Integer)
Retorna o valor de minutos desde a meia noite em horas.

## MinutesToTime(Minutos : Integer)
Retorna o valor de minutos desde a meia noite em horas.

## Mod(Dividendo : Integer, Divisor : Integer)
Retorna o resto da divisão entre dois números.

## Neg(Numero : Float)
Retorna o valor negativo de um determinado número.

## NumUnits(Amnt : Integer, MinLot : Integer)
Retorna o número de contratos/ações de um certo investimento.

## PercentChange(SerieDados : Serie, Periodo : Integer)
Retorna a alteração percentual no preço do candle atual.

## PercentR(Comprimento : Integer)
Retorna uma porcentagem de onde o preço atual está, relacionado com a faixa de negociação avaliada.

## Permutation(Numero : Integer, NumeroObjetos : Integer)
Calcula um número de permutações.

## Pos(Valor : Float)
Retorna o valor absoluto(sem sinal).

## Power(Base : Float, Expoente : Integer)
Eleva valores nas determinadas potências.

## PriceOscillator(SerieDados : Serie, ComprimentoRapido : Integer, ComprimentoLento : Integer)
Retorna o valor do indicador Price Oscillator.

## Random(Limite : Integer)
Retorna um valor aleatório de 0 até o limite.

## RateOfChange(SerieDados : Serie, Periodo : Integer)
Retorna a variação percentual de uma série.

## Round(Valor : Float)
Arredondamento de número.

## Round2Fraction(Valor : Float)
Arredonda o número para o valor mais próximo de um múltiplo do incremento mínimo de um ativo.

## Sign(Valor : Float)
Retorna um número inteiro, baseado no sinal de um número.

## Sin(Valor : Float)
Retorna o valor de Seno em radianos.

## Sine(Valor : Float)
Retorna o valor de Seno em graus.

## SlowD(Periodo : Integer)
Retorna o valor SlowD do Oscilador Estocástico.

## SlowK(Periodo : Integer)
Retorna o valor SlowK do Oscilador Estocástico.

## Sqrt(Valor : Float)
Retorna raiz quadrada dos valores.

## Square(Valor : Float)
Retorna o valor de um número ao quadrado.

## StdDevs(SerieDados : Serie, Periodo : Integer)
Calcula o desvio padrão de uma série de dados em um determinado período.

## Summation(SerieDados : Serie, Periodo : Integer)
Acumula o valor do preço de um determinado número de barras.

## Tangent(Valor : Float)
Retorna a tangente de um número em graus.

## TriAverage(SerieDados : Serie, Periodo : Integer)
Calcula a média triangular de uma série de dados, dentro de um certo período.

## UlcerIndex(SerieDados : Serie, Periodo : Integer)
Retorna o valor do indicador UlcerIndex.

## Volatility(Periodo : Integer)
Retorna a volatilidade de determinado período.

## VolumeOsc(PeriodoMediaRapida : Integer, PeriodoMediaLenta : Integer)
Retorna a diferença entre a média aritmética rápida e a média aritmética lenta da série Volume.

## VolumeROC(Periodo : Integer)
Retorna VolumeROC baseado em um número de barras.

# Opções

## Delta(DaysLeft : Integer, StrikePr : Float, AssetPr : Float, Rate100 : Float, Volty100 : Float, PutCall : Integer)
Retorna o valor de Delta.

## Gamma(DaysLeft : Integer, StrikePr : Float, AssetPr : Float, Rate100 : Float, Volty100 : Float, PutCall : Integer)
Retorna o valor de Gamma.

## Rho(DaysLeft : Integer, StrikePr : Float, AssetPr : Float, Rate100 : Float, Volty100 : Float, PutCall : Integer)
Retorna o valor de Gamma.

## Theta(DaysLeft : Integer, StrikePr : Float, AssetPr : Float, Rate100 : Float, Volty100 : Float, PutCall : Integer)
Retorna o valor de Theta.

## Vega(DaysLeft : Integer, StrikePr : Float, AssetPr : Float, Rate100 : Float, Volty100 : Float, PutCall : Integer)
Retorna o valor de Vega.

# Screening

## Select
Seleciona um ativo para mostrar no Screening.
