## Função WellesSum

## Descrição:

A função WellesSum retorna o valor do indicador WellesSum , de acordo com os parâmetros desejados.

Observação: o exemplo com o código fonte está disponível no editor de estratégias, para visualizá-lo, acesse o menu: "abrir &gt; exemplos".

## Sintaxe:

WellesSum(Periodo, Integer, SerieReferencia : Serie, Offset : Integer)



## Parâmetros:

Periodo: Período utilizado no momento do cálculo do indicador.

SerieReferencia:

Série de dados.

Offset: Referente ao parâmetro "Offset" do indicador.

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "nWS" o dado do indicador WellesSum, considerando 20(Período), série de fechamento(SerieReferencia) e 0(Offset) para o cálculo.

## nWS := WellesSum(20, Close, 0);

## Gráficas

## Função AvgPrice

## Descrição:

A função AvgPrice retorna o valor da média entre Abertura, Fechamento, Máxima e Mínima, de determinado candle.

## Sintaxe:

AvgPrice

## Parâmetros:

Sem parâmetros

## Retorno:

Float

## Exemplos:

Será atribuído à variável "nAvg" o retorno da função AvgPrice.



## Função BarCount

## aux := BarCount;

## Descrição:

A função BarCount retorna a quantidade total de barras.

## Sintaxe:

BarCount

## Parâmetros:

Sem parâmetros.

## Retorno:

Integer

## Exemplos:

No exemplo, será atribuído à variável 'aux' o total de barras para o período.

## Função CurrentBar

## Descrição:

A função CurrentBar tem como finalidade retornar ao usuário o índice do candle atual.

## Sintaxe:

CurrentBar

## Parâmetros:

Sem parâmetros.

nAvg := AvgPrice;


## Retorno:

Integer

## Exemplos:

No exemplo, o candle de número 100 será identificado com a coloração vermelha.


## Funcão LineSegment

## Descrição:

A função LineSegment tem como finalidade adicionar um estudo com uma linha customizável em um indicador.

## Sintaxe:

LineSegment (PriceStart : Float; PriceEnd : Float; StartDate : Integer; EndDate : Integer; Extrapolate : Boolean; Text : String; Color : Integer [Opcional]; LineWidth : Integer [Opcional]; Style : Integer [Opcional]; FontSize : Integer [Opcional]; TextPosition : Integer : [Opcional]; StartTime : Integer [Opcional]; EndTime : Integer [Opcional])

## Parâmetros:

- ● PriceStart: Preço do primeiro ponto que define a linha (Y1)
- ● PriceEnd: Preço do Segundo ponto que define a linha (Y2)
- ● StartDate: Data do primeiro ponto que define a linha (X1)
- ● EndDate: Data do segundo ponto que define a linha (X2)
- ● Extrapolate: Se a linha deve extrapolar para direita
- ● Text: Texto que será pintado junto da linha
- ● Color: Cor da linha
- ● LineWidth: Espessura da linha
- ● Style: Estilo da linha. Ver SetPlotStyle para mais detalhes
- ● FontSize: Cor da Fonte
- ● TextPosition: Posição do texto na linha. Podendo ser: tpTopLeft, tpTopRight, tpBottomLeft e tpBottomRight
- ● StartTime: Define um tempo especifico para o inicio da linha
- ● EndTime: Define um tempo especifico para o fim da linha

## Retorno:

Sem retorno

## Exemplos:




No exemplo abaixo, será adicionada uma linha entre os pontos (12/11/2024, 128.000) e (25/11/2024, 125.000), Extrapolando para direita, Com um texto 'Linha de teste', da cor vermelha, no estilo pontilhado com fonte tamanho 8, o texto no canto superior esquero, começando e terminando as 12:00 no candle


## Função GetPlotColor

## Descrição:

A função GetPlotColor possui como funcionalidade retornar o valor numérico da cor de determinado Plot.

## Sintaxe:

GetPlotColor(NumeroPlot : Integer)

## Parâmetros:

NumeroPlot: Número do Plot para obter a cor.

## Retorno:

Integer

## Exemplos:



No exemplo, será aplicada a coloração do Plot no Plot2.

SetPlotColor(1, RGB(200, 200, 200)); SetPlotColor(2, GetPlotColor(1));



## Função GetPlotWidth

## Descrição:

A função GetPlotWidth possui como finalidade retornar o valor da espessura de determinado Plot.

## Sintaxe:

GetPlotWidth(NumeroPlot : Integer)

## Parâmetros:

NumeroPlot: Número do Plot para obter a espessura.

## Retorno:

Integer

## Exemplos:

No exemplo, será aplicada a espessura do Plot no Plot2.

SetPlotWidth(1, 5);

SetPlotWidth(2, GetPlotWidth(1));

## Função GraphicInterval

## Descrição:

A função GraphicInterval retorna o intervalo do gráfico

## Sintaxe:

GraphicInterval

## Parâmetros:

Sem parâmetros.

## Retorno:

Integer



## Exemplos:

gInterval :=  GraphicInterval;

## Função GraphicOffset

gOffset :=  GraphicOffset;

No exemplo, será atribuído à variável 'gInterval' o retorno da função.

## Descrição:

A função GraphicOffset retorna o offset do gráfico.

## Sintaxe:

GraphicOffset

## Parâmetros:

Sem parâmetros.

## Retorno:

Integer

## Exemplos:

No exemplo, será atribuído à variável 'gOffset ' o retorno da função.

## Funcão HorizontalLine

## Descrição:

A função HorizontalLine tem como finalidade, adicionar um estudo horizontal em um indicador.

## Sintaxe:



HorizontalLine (Y : Float; Color : Interger)

## Parâmetros:

Y: Valor do estudo. Color: Cor da linha.

## Retorno:

Sem retorno

## Exemplos:

No exemplo abaixo, será adicionada uma linha vermelha, no nível 5288.

## HorizontalLine(5288, RGB(200, 0, 0));

## Funcão HorizontalLineCustom

## Descrição:

A função HorizontalLineCustom tem como finalidade, adicionar um estudo horizontal customizável em um indicador.

## Sintaxe:

HorizontalLineCustom (Price : Float; Color : Integer; LineWidth: Integer; Style: Integer; Text: String; FontSize : Integer [Opcional]; TextPosition : Integer [Opcional]; StartDate: Integer [Opcional]; EndDate : Integer [Opcional]; PriceVariation : Float [Opcional]; StartTime: Integer [Opcional]; Endtime : Integer [Opcional])

## Parâmetros:

- · Price: Valor do estudo.
- · Color: Cor da linha.
- · LineWidth: Espessura da linha.
- · Style: Estilo da linha. Ver SetPlotStyle para mais detalhes.
- · Text: Texto da linha.
- · FontSize : Tamanho da fonte
- · TextPosition: Posição do texto na linha. Podndo ser: tpTopLeft, tpTopRight, tpBottomLeft e tpBottomRight
- · StartDate: Data inicial da linha.
- · EndDate : Data final da linha.
- · PriceVariation: Variação de preço que será usado para formar uma pintura de preenchimento em cima e abaixo da linha principal.
- · StartTime: Horário inicial da linha
- · EndTime: Horário final da linha


## Retorno:

Sem retorno

## Exemplos:

No exemplo abaixo, será adicionada uma linha amarela, com espessura 3, estilo linha, com fonte de tamanho 10, texto no topo direito, do início ao fim do gráfico e com uma variação de 1000 no preço, das 10h às 18h.


## Função Last BarOn Chart

## Descrição:

A função LastBarOnChart têm como função retornar um valor Booleano mostrando se o candle atual é o último candle do gráfico.

## Sintaxe:

LastBarOnChart

## Parâmetros:

Sem parâmetros.

## Retorno:

Boolean

Exemplos:




No exemplo a seguir, o candle atual será identificado com a coloração amarela.

if (LastBarOnChart) then

PaintBar(clYellow) ;

## Função Leader

if (Leader = 1) then

PaintBar(clVerde) ;

## Função MaxBarsBack

## Descrição:

A função Leader retorna o valor de 1 quando o ponto médio for menor que a mínima anterior ou  quando o ponto médio for maior que máxima anterior. Caso contrário retorna 0.

## Sintaxe:

Leader

## Parâmetros:

Sem parâmetros

## Retorno:

Integer

## Exemplos:

No exemplo abaixo, caso a função Leader seja igual a um, o candle analisado será identificado pela cor verde.

## Descrição:

A função MaxBarsBack tem como finalidade percorrer a lista da série, iniciando(índice 0) a partir do primeiro candle criado.



if (MaxBarsBack = 1) then

PaintBar(clGreen) ;

## Sintaxe:

MaxBarsBack

## Parâmetros:

Sem parâmetros.

## Retorno:

Integer

## Exemplos:

No exemplo, será aplicada uma coloração no segundo candle criado.

## Função MaxBarsForward

## Descrição:

A função MaxBarsForward tem como finalidade percorrer a lista da série, iniciando(índice 0) a partir do último candle criado(atual).

## Sintaxe:

MaxBarsForward

## Parâmetros:

Sem parâmetros.

## Retorno:

Integer

## Exemplos:

No exemplo, será aplicada uma coloração no candle anterior ao atual.




## Função MedianPrice

## Descrição:

A função MedianPrice retorna a média entre a máxima e a mínima de cada candle.

## Sintaxe:

MedianPrice

## Parâmetros:

Sem parâmetros

## Retorno:

Float

## Exemplos:

No exemplo a seguir, caso o dado de MedianPrice do candle atual for maior que o do anterior, os candles serão destacados com a coloração verde.

if (MedianPrice &gt; MedianPrice[1]) then

PaintBar(clGreen) ;

## Função NoPlot

## Descrição:

A função NoPlot tem como finalidade efetuar a remoção de determinado Plot.

## Sintaxe:

NoPlot(NumeroPlot : Integer)



## Parâmetros:

NumeroPlot: Número do Plot(1, 2, 3 e 4) para a remoção.

## Retorno:

Void: Sem retorno.

## Exemplos:

Conforme no exemplo a seguir, será removida a linha referente ao Plot, e será plotada somente a linha vinculada ao Plot2.

Plot(Close) ;

Plot2(Open) ;

NoPlot(1) ;

## Função PaintBar

## Descrição:

A função PaintBar permite a aplicação de colorações, em indicadores ou candles.

## Sintaxe:

PaintBar(Cor : Integer)

## Parâmetros:

Cor: Determina a coloração, podendo-se passar por parâmetro uma String ou a chamada da função RGB:

clNomeCor String para aplicação, conforme a seguinte lista:

clBlack clMarrom

clGreen clOlive

clNavy clPurple

clTeal clGray

clSilver clRed

clLime clYellow

clBlue



clFuchsia clAqua clWhite clMoneyGreen clSkyBlue

## RGB Função para aplicação.

RGB(255,0,0)

## Retorno:

Float

## Exemplos:

No exemplo, será aplicada uma coloração(verde) quando o histograma de MACD for maior que zero. Ou se usada a função comentada será aplicada a coloração Vermelha de acordo com o RGB.


## Função Plot

## Descrição:

A função Plot realiza a ligação dos valores passados por parâmetro e cria gráficos de linhas.

É possível efetuar a inserção de no máximo 99 linhas, onde deverá ser utilizada a função Plot numerada: Plot, Plot2, Plot3… Plot99.

## Sintaxe:

Plot(Dado : Float);

Plot2(Dado : Float);

Plot3(Dado : Float);

Plot99(Dado : Float);

## Parâmetros:

Dado:

Pode-se utilizar variáveis, funções ou constantes para realizar o desenho do indicador.



## Retorno:

Void: Sem retorno.

## Exemplos:

Conforme no exemplo a seguir, são plotados os dados de fechamento do dia anterior e abertura do dia atual.

Plot(CloseD(1)) ; Plot99(OpenD(0)) ;

## Função PlotN

## Descrição:

A função PlotN, assim como a Plot, desenha o indicador conforme a série de dados informada, porém o número do plot deve ser determinado por parâmetro (entre 0 e 99).

## Sintaxe:

PlotN(Plot : Interger; Valor : Float)

## Parâmetros:

Plot:

Número do plot, entre 0 e 99.

Dado: Pode-se utilizar variáveis, funções ou constantes para realizar o desenho do indicador.

## Retorno:

Void:

Sem retorno.

## Exemplos:

No exemplo, são plotados os dados de fechamento do dia anterior e abertura do dia atual.

PlotN(0, CloseD(1)) ;

PlotN(99, OpenD(0)) ;




## Função PlotText

## Descrição:

A função PlotText possui como finalidade, adicionar um texto e emoji a um indicador.

## Sintaxe:

PlotText(Content : String; Color : Interger; Position : Interger; FontSize : Interger; dPrice : Float)

## Parâmetros:

Content: Conteúdo do texto.

Color: Cor da fonte.

Position: Posição do texto.

0 - Abaixo do candle

1 - Centralizado

2 - Acima do candle

3 - Posiciona no preço definido em dPrice

FontSize: Tamanho da fonte do texto.

dPrice: Quando utilizada Position=3, será utilizado o valor de dPrice para posicionar o texto.

## Retorno:

Void: Sem retorno.

## Exemplos:

No exemplo, será adicionado o texto "Close &gt; M20', após o fechamento anterior estar acima da média exponencial de 20 períodos, e, caso o fechamento anterior fique abaixo, será visualizado o "Close &lt; M20.

if (close[1] &lt; mediaExp(20, close)[1]) and (close &gt; mediaExp(20, close)) then PlotText("Close &gt; M20!", clLime, 2, 6) else if (close[1] &gt; mediaExp(20, close)[1]) and (close &lt; mediaExp(20, close)) then PlotText("Close &lt; M20!", clRed, 0, 6);

## Função Range

## Descrição:



A função Range retorna a diferença entre a máxima e a mínima do candle.

nRange := Range;

## Função RangeLeader

## Sintaxe:

Range

## Parâmetros:

Sem parâmetros

## Retorno:

Float

## Exemplos:

No exemplo, a variável "nRange" irá receber o retorno do dado da função Range.

## Descrição:

A função RangeLeader verifica se a barra atual é Range Leader.

## Sintaxe:

RangeLeader

## Parâmetros:

Sem parâmetros

## Retorno:

Float

## Exemplos:

No exemplo, a variável "nRL" irá receber o retorno do dado da função RangeLeader.



## nRL := RangeLeader;

## Função RGB

## Descrição:

A função RGB permite ao usuário customizar cores, a partir da aplicação de intensidade dos parâmetros vermelho, verde e azul.

## Sintaxe:

RGB(Red : Integer, Green : Integer, Blue : Integer)

## Parâmetros:

Red: Intensidade cor vermelha, variando de 0 a 255; Green: Intensidade cor verde, variando de 0 a 255; Blue: Intensidade cor azul, variando de 0 a 255.

## Retorno:

Integer

## Exemplos:

No exemplo a seguir, será aplicada a coloração azul, conforme os parâmetros de RGB.

## PaintBar(RGB(0, 0, 230)) ;

## Função SetPlotColor

## Descrição:

A função SetPlotColor possui como finalidade alterar a coloração de determinado Plot(1 a 4)

## Sintaxe:

SetPlotColor(NumeroPlot : Integer, Cor : Integer)



## Parâmetros:

NumeroPlot: Número do Plot específico:

1 - Plot

2 - Plot2

3 - Plot3

4 - Plot4

Cor: Determina a coloração, podendo-se passar por parâmetro uma String ou a chamada da função RGB:

clNomeCor - String para aplicação, conforme a seguinte lista:

clNomeCor - String para aplicação, conforme a seguinte lista:

clBlack

clMarrom

clGreen

clOlive

clNavy

clPurple

clTeal

clGray

clSilver

clRed

clLime

clYellow

clBlue

clFuchsia

clAqua

clWhite

clMoneyGreen

clSkyBlue

RGB - Função para aplicação.

## Retorno:

Void: Sem retorno.

## Exemplos:

No exemplo, será alterada a coloração(vermelha) referente à linha do Plot.

Plot(Close) ;

SetPlotColor(1, clRed) ;

## Função SetPlotStyle

## Descrição:

A partir da função SetPlotStyle, é possível alterar o estilo da linha de um plot específico.

## Sintaxe:



SetPlotStyle(NumeroPlot : Integer; Estilo : Integer)

## Parâmetros:

NumeroPlot: Número do Plot

Estilo: Estilo de linha

0 - Contínua

1 - Tracejada (Traço longo)

2 - Tracejada (Traço curto)

3 - Tracejada (Traço longo e curto)

4 - Tracejada (Traço longo e dois curtos)

## Retorno:

Void: Sem retorno.

## Exemplos:

No exemplo, serão customizados os estilos dos plots, onde o primeiro possuirá a linha tracejada, com traços longos, e o segundo plot, com traços curtos.


## Função SetPlotType

## Descrição:

A função SetPlotType possui como finalidade alterar o tipo de gráfico de determinado plot.

## Sintaxe:

SetPlotType(Number : Integer; Type : Integer)

## Parâmetros:

Number: Número do Plot específico Type: Tipo de visualização 0 - Linha 1 - Histograma



## Retorno:

Void: Sem retorno.

## Exemplos:

No exemplo, será alterado o tipo do plot 1 para histograma.

PlotN(1, closeD(1)); SetPlotType(1, 1);

## Função SetPlotWidth

## Descrição:

A função SetPlotWidth possui como finalidade alterar a espessura de determinado Plot(1 a 4)

## Sintaxe:

SetPlotWidth(NumeroPlot : Integer, Espessura : Integer)

## Parâmetros:

NumeroPlot: Número do Plot específico:

- 1 - Plot
- 2 - Plot2
- 3 - Plot3
- 4 - Plot4

Espessura: Número para a nova espessura.

## Retorno:

Void: Sem retorno.

## Exemplos:

No exemplo, será alterada a espessura referente à linha do Plot.




## TH := TrueHigh;

## Descrição:

A função TrueHigh retorna o maior entre o máximo da barra e o fechamento da barra anterior.

## Sintaxe:

TrueHigh

## Parâmetros:

Sem parâmetros.

## Retorno:

Float

## Exemplos:

No exemplo, a variável "TH" irá receber o dado da função TrueHigh.

## Função TrueLow

## Descrição:

A função TrueLow retorna o menor entre a mínima da barra e o fechamento da barra anterior.

## Sintaxe:

TrueLow

## Parâmetros:

## Função TrueHigh



TL := TrueLow;

TR := TrueRange;

Sem parâmetros.

## Retorno:

Float

## Exemplos:

No exemplo, a variável "TL" irá receber o dado da função TrueLow.

## Função TrueRange

## Descrição:

A função TrueRange retorna a diferença entre TrueHigh e TrueLow.

## Sintaxe:

TrueRange

## Parâmetros:

Sem parâmetros.

## Retorno:

Float

## Exemplos:

No exemplo, a variável "TR" irá receber o valor do indicador True Range.



## Função TrueRangeCustom

## Descrição:

A função TrueRangeCustom retorna o TrueRange de acordo com os dados informados pelo usuário.

## Sintaxe:

TrueRangeCustom(Maxima  : Float, Minima : Float, Fechamento : Float)

## Parâmetros:

Maxima: Valor de máxima para o cálculo do indicador. Minima: Valor de mínima para o cálculo do indicador. Fechamento: Valor de fechamento de referência.

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "TRC" o dado da função TrueRangeCustom.

## TRC := TrueRangeCustom(3763.5, 3761, 3761);

## Função TypicalPrice

## Descrição:

A função TypicalPrice retorna a média entre a máxima, mínima e fechamento do candle.

## Sintaxe:

TypicalPrice

## Parâmetros:

Sem parâmetros


## Retorno:

Float

## Exemplos:

No exemplo, a variável "aux" irá receber o retorno do dado da função TypicalPrice.

## aux := TypicalPrice;

## Função VerticalLine

## Descrição:

A função VerticalLine a diciona um estudo vertical em um indicador.

## Sintaxe:

VerticalLine(Y : Integer; Color : Integer)

## Parâmetros:

Y: Data, com o formato 1AAMMDD Color: Cor da linha

## Retorno:

Void: Sem retorno

## Exemplos:

No exemplo,será inserida uma linha vertical amarela, para o dia anterior..

## VerticalLine(CurrentDate-1, clYellow);




## Funcão VerticalLineCustom

## Descrição:

A função VerticalLineCustom tem como finalidade, permitir que uma chamada de linha vertical crie N linhas verticais no gráfico.

.

## Sintaxe:

VerticalLineCustom(Color : Color; LineWidth : Integer; Style : Integer; Text : String; FontSize = 8 : Integer; TextPosition : Integer = tpBottomRight; PriceTop : Float = 0; PriceBottom : Float = 0; PaintRegion : Boolean)

## Parâmetros:

- ● Color: Cor da linha.
- ● LineWidth : Espessura da linha.
- ● Style : Estilo da linha. Ver SetPlotStyle para mais detalhes.
- ● Text: Texto da linha.
- ● FontSize : Tamanho da fonte
- ● TextPosition: Posição do texto na linha. Podendo ser: tpTopLeft, tpTopRight, tpBottomLeft e tpBottomRight
- ● PriceTop: Preço de onde a linha começa a pintar (Caso zero, pinta a partir do topo do gráfico)
- ● PriceBottom : Preço até onde a linha  pinta (Caso zero, pinta até o fundo do gráfico)
- ● PaintRegion: Se verdadeiro pinta um retângulo até a próxima linha ou ao final caso seja a última linha.

## Retorno:

Void: Sem retorno

## Exemplos:

No exemplo, serão inseridas duas linhas verticais (no caso de um gráfico em Período Diário), a primeira será pintada no dia atual na cor vermelha, espessura 1, estilo pontilhado, com texto 'TESTE' de tamanho 8 pintado à esquerda do topo da linha, a linha irá iniciar no preço 128.000 e finalizará em 125.000 e o retângulo será pintado até o fim.

Além da primeira linha, pintaremos uma outra linha em dois dias atrás de cor verde, espessura 1 e linha sólida, com texto 'TESTE2' de tamanho 8 pintado à esquerda no fundo da linha, a linha irá iniciar no preço 128.500 e finalizará em 123.000 e o retângulo será pintado até a próxima linha (que no caso é a pintada no dia atual)





## Função WeightedClose

## Descrição:

A função WeightedClose retorna a média entre o ponto médio da barra e dois fechamentos.

## Sintaxe:

WeightedClose

## Parâmetros:

Sem parâmetros

## Retorno:

Float



## Exemplos:

No exemplo, a variável "aux" irá receber o retorno do dado da função WeightedClose.

## aux := WeightedClose;

## Indicadores

Todas funções de indicadores não poderão conter variáveis em seus parâmetros, apenas valores constantes. O único tipo de parâmetro que foge um pouco à esta regra são os parâmetros do tipo Serie que contém um valor para cara candle, e esses valores poderiam ser considerados 'variáveis' dado que a série muda ao longo do tempo. Um exemplo é a função média, que recebe como parametro uma serie: Media(Periodo : Integer, TipoSerie : Serie)

Exemplo de código:

## Avg := Media(21, Close);

Veja abaixo as descrições das funções de indicadores disponíveis nas plataformas da Nelogica:

## Função AccAgressSaldo

## Descrição:

A função AccAgressSaldo retorna o valor do indicador TR - Acúmulo de Agressão - Saldo .

## Sintaxe:

AccAgressSaldo(TipoVolume : Integer)

## Parâmetros:

TipoVolume: Tipo de volume para o cálculo:

0 - Financeiro

1 - Quantidade

2 - Negócios

## Retorno:

Float

## Exemplos:



No exemplo, a variável "aac" irá receber o volume de quantidade do indicador TR - Acúmulo de Agressão - Saldo.

## aac := AccAgressSaldo(1);

## Função AccuDistr

## nAcc := AccuDistr;

## Função AccuDistrW

## Descrição:

A função AccuDistr retorna o valor do indicador Acumulação/Distribuição .

## Sintaxe:

AccuDistr

## Parâmetros:

Sem parâmetros.

## Retorno:

Float

## Exemplos:

No exemplo, a variável "nAcc" irá receber o valor do indicador Acumulação/Distribuição.

## Descrição:

A função AccuDistrW retorna o valor do indicador Acumulação/Distribuição  Williams .

## Sintaxe:



## AccuDistrW

## Parâmetros:

Sem parâmetros.

## Retorno:

Float

## Exemplos:

No exemplo, a variável "nADW" irá receber o valor do indicador Acumulação/Distribuição Williams.

nADW := AccuDistrW;

## Função AdaptiveMovingAverage

## Descrição:

A função AdaptiveMovingAverage retorna o valor do indicador Adaptive Moving Average , de acordo com o períodos específicos desejados.

## Sintaxe:

AdaptiveMovingAverage(Periodo : Integer, FastSC : Integer, SlowSC : Integer)

## Parâmetros:

Periodo: Período utilizado no momento do cálculo do indicador.

FastSC: Determina o período para o indicador FastStochastic.

SlowSC: Determina o período para o indicador SlowStochastic.

## Retorno:

Float

## Exemplos:

No exemplo, a variável "amv" irá receber o valor do indicador Adaptive Moving Average, considerando 10 períodos para o cálculo, com 2 períodos para FastStochastic, e 30 para SlowStochastic.



## amv := AdaptiveMovingAverage(10, 2, 30);

## Função ADX

## Descrição:

A função ADX retorna o valor do indicador ADX , de acordo com os períodos desejados.

## Sintaxe:

ADX(Periodo : Integer, PeriodoMedia : Integer)

## Parâmetros:

Periodo: Período utilizado no momento do cálculo do indicador.

PeriodoMedia: Período utilizado no momento do cálculo da média utilizada no indicador.

## Retorno:

Float

## Exemplos:

No exemplo, a variável "nADX" irá receber o valor do indicador ADX, considerando Periodo=9 e PeriodoMedia=9 para o cálculo.

## nADX := ADX(9,9);

## Função AgressionVolBalance

## Descrição:

A função AgressionVolBalance retorna o valor do indicador TR - Volume de Agressão - Saldo .

## Sintaxe:

AgressionVolBalance



## avb := AgressionVolBalance;

## Função AgressionVolBuy

## avb := AgressionVolBuy;

## Parâmetros:

Sem parâmetros.

## Retorno:

Float

## Exemplos:

No exemplo, a variável "avb" irá receber o valor do indicador TR - Acúmulo de Agressão - Saldo.

## Descrição:

A função AgressionVolBuy retorna o valor do indicador TR - Volume de Agressão - Compra .

## Sintaxe:

AgressionVolBuy

## Parâmetros:

Sem parâmetros.

## Retorno:

Float

## Exemplos:

No exemplo, a variável "avb" irá receber o valor do indicador TR - Volume de Agressão - Compra.



## Função AgressionVolSell

## Descrição:

A função AgressionVolSell retorna o valor do indicador TR - Volume de Agressão - Venda .

## Sintaxe:

AgressionVolSell

## Parâmetros:

Sem parâmetros.

## Retorno:

Float

## Exemplos:

No exemplo, a variável "avs" irá receber o valor do indicador AgressionVolSell.

## avs := AgressionVolSell;

## Função ArmsEaseOfMov

## Descrição:

A função ArmsEaseOfMov retorna o valor do indicador Arms Ease of Movement , de acordo com o período e tipo de média desejados.

## Sintaxe:

ArmsEaseOfMov(Media : Integer, TipoMedia : Integer)

## Parâmetros:

Media: Período da média utilizada no momento do cálculo do indicador. TipoMedia: Determina o tipo da média utilizada,

- 0 - Aritmética
- 1 - Exponencial
- 2 - Welles Wilder
- 3 - Ponderada


## Retorno:

Float

## Exemplos:

No exemplo, a variável "nATR" irá receber o valor do indicador Arms Ease of Movement, considerando 9 períodos para o tipo de média exponencial.

## nATR := ArmsEaseOfMov(9, 1);

## Função AroonLin

## Descrição:

A função AroonLin retorna o valor do indicador Aroon Linha , de acordo com o período desejado.

## Sintaxe:

AroonLin(Periodo : Integer)|Linha : Integer|

## Parâmetros:

Período utilizado no momento do cálculo do indicador.

Periodo: Linha: Determina qual linha será obtida:

- 0 Aroon Up
- 1 Aroon Down

## Retorno:

Float

## Exemplos:

No exemplo, a variável "fAroon" irá receber o valor da linha "Aroon Down", considerando 9 períodos para o cálculo.

## fAroon := AroonLin(9)|1|;




## Função AroonOsc

## Descrição:

A função AroonOsc retorna o valor do indicador Aroon Oscilador , de acordo com o período desejado.

## Sintaxe:

AroonOsc(Periodo : Integer)

## Parâmetros:

Periodo: Período utilizado no momento do cálculo do indicador.

## Retorno:

Float

## Exemplos:

No exemplo, a variável "fAroonOsc" irá receber o valor do indicador Aroon Oscilador, considerando 9 períodos para o cálculo.

## fAroonOsc := AroonOsc(9);

## Função AutoFibonacci

## Descrição:

A função AutoFibonacci retorna o valor do indicador AutoFibonacci , de acordo com os parâmetros desejados.

## Sintaxe:

AutoFibonacci(Período : Integer, Níveis: Integer)|Nível : Integer|

## Parâmetros:

Período: Período utilizado no momento do cálculo do indicador.

Níveis: Determina quantos níveis serão gerados para o indicador, limitado em 8, e seguindo a ordem: (0%, 23.6%, 38.2%, 50%, 61.8%, 78.6%, 100%, 161.8%).


## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "aux" o retorno do indicador, considerando um período de 144 candles, e gerando oito níveis. Ao não especificar o nível desejado, o padrão será sempre retornar o nível 0 (0%).

## aux := AutoFibonacci(144, 8);

Também é possível escolher qual o nível desejado passando como parâmetro no final da chamada. No exemplo, será atribuído à variável "aux" o retorno do indicador, considerando um período de 144 candles, gerando oito níveis e retornando o valor do nível 4 (50%).

## aux := AutoFibonacci(144, 8)|3|;

## Função AutoFibonacciCustom

## Descrição:

A função AutoFibonacciCustom retorna o valor do indicador Auto Fibonacci , de acordo com os parâmetros desejados.

## Sintaxe:

AutoFibonacciCustom(Período : Integer, Valor do Nível: Float)

## Parâmetros:

Período:

Período utilizado no momento do cálculo do indicador.

Valor do Nível: Determina qual o valor do nível utilizado para o cálculo do indicador.

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "aux" o retorno do indicador, considerando um periodo de 144 candles, e o valor do nível em 75.5%.

## aux := AutoFibonacciCustom(144, 75.5);




## Função AvgAgent

## Descrição:

A função AvgAgent retorna o preço médio filtrado por agente . Retorna os dados em tempo real, não executando em backtest.

## *Exclusivo Profit Ultra

## Sintaxe:

AvgAgent(AgentID : Integer, Período : Integer )

## Parâmetros:

AgentID:

ID do agente na B3.

Período:

Determina qual tipo de cálculo do preço médio será obtido:

0 - Retorna o preço médio diário, não importando o tempo gráfico onde está executando.

1 - Retorna o preço médio candle a candle.

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "aux" o retorno da função, a constante AgentID terá como filtro o agente 3 e o preço médio será diário.

const

AgentID = 3;

var

aux : Float;

begin

aux := AvgAgent(AgentID, 0);

end;

## Função AvgAgrBuySell

## Descrição:

A função AvgAgrBuySell retorna o valor do indicador TR - Agressão Média - Compra e Venda , de acordo com os parâmetros desejados.

## Sintaxe:

AvgAgrBuySell(AlertaVariacoes : Integer, TipoVolume : Integer, TipoDesenho : Integer)|Linha : Integer|



## Parâmetros:

AlertaVariacoes: Número de variações.

TipoVolume: Determina qual tipo de volume será obtido:

- 0 - Financeiro
- 1 - Quantidade

TipoDesenho: Relação entre compra e venda:

- 0 - Compra e Venda
- 1 - Compra/Venda
- 2 - Compra-Venda

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "aux" o retorno do indicador, considerando 3 variações, a quantidade e tipo de desenho .

## aux := AvgAgrBuySell(3, 1, 0);

## Função AvgAgrTotal

## Descrição:

A função AvgAgrTotal retorna o valor do indicador TR - Agressão Média - Total , de acordo com os parâmetros específicos.

## Sintaxe:

AvgAgrTotal(AlertaVariacoes: Integer, TipoVolume : Ingeter, TipoDesenho : Integer)|Linha : Integer|

## Parâmetros:

AlertaVariacoes: Número de variações.

TipoVolume: Determina qual tipo de volume será obtido:

- 0 - Financeiro
- 1 - Quantidade

TipoDesenho: Relação entre compra e venda:

- 0 - Compra e Venda
- 1 - Compra/Venda
- 2 - Compra-Venda

Linha: Determina qual linha será obtida:



- 0 - Volume indicador
- 1 - Avaliar

## Retorno:

Float

## Exemplos:

No exemplo, a variável "n" irá receber o valor da função AvgAgrTotal.

## n := AvgAgrTotal(3, 1, 0);

## Função AvgSeparation

## Descrição:

A função AvgSeparation retorna o valor do indicador Afastamento Médio , de acordo com o período e tipo de média desejados.

## Sintaxe:

AvgSeparation(Periodo : Integer, TipoMedia : Integer)

## Parâmetros:

Periodo: Período utilizado no momento do cálculo do indicador.

TipoMedia:

Determina qual média será considerada:

- 0 - Aritmética
- 1 - Exponencial
- 2 - Welles Wilder
- 3 - Ponderada

## Retorno:

Float

## Exemplos:

No exemplo, a variável "avgSep" irá receber o valor do indicador Afastamento Médio, considerando 21 períodos e tipo exponencial para o cálculo.

## avgSep := AvgSeparation(21, 1);



## Função AvgTrueRange

## Descrição:

A função AvgTrueRange retorna o valor do indicador True Range , de acordo com o período e tipo de média desejados.

## Sintaxe:

AvgTrueRange(Periodo : Integer, TipoMedia : Integer)

## Parâmetros:

Período: Período utilizado no momento do cálculo do indicador. TipoMedia: Determina qual média será considerada:

- 0 - Aritmética
- 1 - Exponencial
- 2 - Welles Wilder
- 3 - Ponderada

## Retorno:

Float

## Exemplos:

No exemplo, a variável "nATR" irá receber o valor do indicador True Range, considerando 5 períodos, e tipo de média ponderada para o cálculo.

## nATR := AvgTrueRange(5, 3);

## Função BalanceAgent

## Descrição:

A função BalanceAgent retorna o saldo financeiro filtrado por agente . Retorna os dados em tempo real, não executando em backtest.

## *Exclusivo Profit Ultra

## Sintaxe:

BalanceAgent(AgentID : Integer, Período : Integer )



## Parâmetros:

AgentID:

ID do agente na B3.

Período: Determina qual tipo de cálculo do saldo será obtido:

0 - Retorna o saldo diário, não importando o tempo gráfico onde está executando.

1 - Retorna o saldo candle a candle.

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "aux" o retorno da função, a constante AgentID terá como filtro o agente 3 e o saldo será diário.

const

AgentID = 3;

var

aux : Float;

begin

aux := BalanceAgent(AgentID, 0);

end;

## Função BalanceOfPower

## Descrição:

A função BalanceOfPower retorna o valor do indicador Balança do Poder , de acordo com o período desejado.

## Sintaxe:

BalanceOfPower(Media : Integer, TipoMedia : Integer)

## Parâmetros:

Media: Período utilizado no momento do cálculo do indicador.

TipoMedia: Determina o tipo da média utilizada,

- 0 - Aritmética
- 1 - Exponencial
- 2 - Welles Wilder
- 3 - Ponderada

## Retorno:


## Float

## Exemplos:

No exemplo, a variável "nBalance" irá receber o valor do indicador Balança do Poder, considerando 14 períodos, e o tipo de média exponencial para o cálculo.

## nBalance := BalanceOfPower(14,1);

## Função BearPower

## Descrição:

A função BearPower retorna o valor do indicador Bear Power , conforme o período desejado.

## Sintaxe:

BearPower(Periodo : Integer)

## Parâmetros:

Periodo: Período utilizado no momento do cálculo do indicador.

## Retorno:

Float

## Exemplos:

No exemplo, a variável "nBear" irá receber o dado do indicador Bear Power, considerando 13 períodos.

## nBear := BearPower(13);

## Função BollingerBands

## Descrição:

A função BollingerBands retorna o valor do indicador Bandas de Bollinger , de acordo com o período e tipo de média desejados.




## Sintaxe:

BollingerBands(Desvio : Float, Media : Integer, TipoMedia : Integer)|Linha : Integer|

## Parâmetros:

Desvio:

Media:

TipoMedia:

Desvio utilizado no momento do cálculo do indicador. Período da média utilizada no momento do cálculo do indicador. Determina o tipo da média utilizada,

- 0 - Aritmética
- 1 - Exponencial
- 2 - Welles Wilder
- 3 - Ponderada

## Retorno:

Linha:

Determina qual linha será obtida:

0 - Superior

1 - Inferior

## Float

## Exemplos:

No  exemplo,  a  variável  "fBool" irá receber o valor da linha inferior do indicador Bandas de Bollinger, considerando 2.0 como desvio, 20 períodos e tipo de média aritmética.

## fBool := BollingerBands(2.0, 20, 0)|1|;

## Função BollingerBandW

## Descrição:

A função BollingerBandW retorna o valor do indicador Bollinger Band Width , de acordo com o período e tipo de média desejados.

## Sintaxe:

BollingerBandW(Desvio : Float, Media : Integer, TipoMedia : Integer)

## Parâmetros:

Desvio:

Desvio utilizado no momento do cálculo do indicador. Período da média utilizada no momento do cálculo do indicador. Determina o tipo da média utilizada,

Media:

TipoMedia:



- 0 - Aritmética
- 1 - Exponencial
- 2 - Welles Wilder
- 3 - Ponderada

## Retorno:

Float

## Exemplos:

No exemplo, a variável "fBoolinBW" irá receber o valor do indicador Bollinger Band Width, considerando 2.0 como desvio, 20 períodos e tipo de média exponencial.

## fBoolinBW := BollingerBandW(2.0,20,1);

## Função BollingerBPerc

## Descrição:

A função BollingerBPerc retorna o valor do indicador Bollinger b% , de acordo com o período e tipo de média desejados.

## Sintaxe:

BollingerBPerc(Desvio : Float, Media : Integer, TipoMedia : Integer)

## Parâmetros:

Desvio:

Media:

TipoMedia:

Desvio utilizado no momento do cálculo do indicador. Período da média utilizada no momento do cálculo do indicador. Determina o tipo da média utilizada,

- 0 - Aritmética
- 1 - Exponencial
- 2 - Welles Wilder
- 3 - Ponderada

## Retorno:


## Float

## Exemplos:

No exemplo, a variável "fBool" irá receber o valor do indicador Bollinger Band Width, considerando 2.0 como desvio, 20 períodos e tipo de média Ponderada.

## fBool := BollingerBPerc(2.0,20,3);

## Função BullPower

## Descrição:

A função BullPower retorna o valor do indicador Bull Power , de acordo com o período e tipo de média desejados.

## Sintaxe:

BullPower(Periodo : Integer, PeriodoMedia : Integer, TipoMedia : Integer)

## Parâmetros:

Periodo: Período utilizado no momento do cálculo do indicador;

PeriodoMedia: Período utilizado no momento do cálculo da média utilizada no indicador.

TipoMedia: Determina o tipo da média utilizada,

- 0 - Aritmética
- 1 - Exponencial
- 2 - Welles Wilder
- 3 - Ponderada

## Retorno:

Float

## Exemplos:

No exemplo, a variável "nBull" irá receber o valor do indicador Bull Power, considerando 21 períodos, e 9 períodos para a média aritmética.

## nBull := BullPower(21,9,0)




## Função CCI

## Descrição:

A função CCI retorna o valor do indicador CCI , de acordo com o período desejado.

## Sintaxe:

CCI(Periodo : Integer)

## Parâmetros:

Periodo: Período utilizado no momento do cálculo do indicador.

## Retorno:

Float

## Exemplos:

No exemplo, a variável "nCCI" irá receber o valor do indicador CCI, considerando 14 períodos para o cálculo.

## nCCI := CCI(14);

## Função ChaikinMoneyFlow

## Descrição:

A função ChaikinMoneyFlow retorna o valor do indicador Chaikin Money Flow , de acordo com o período desejado.

## Sintaxe:

ChaikinMoneyFlow(Periodo  : Integer)

## Parâmetros:

Periodo: Período utilizado no momento do cálculo do indicador.

## Retorno:


## Float

## Exemplos:

No exemplo, a variável "nCMF" irá receber o valor do indicador Chaikin Money Flow, considerando 21 período para o cálculo.

## nCMF := ChaikinMoneyFlow(21);

## Função ChaikinOsc

## Descrição:

A função ChaikinOsc retorna o valor do indicador Oscilador Chaikin , de acordo com as médias desejadas.

## Sintaxe:

ChaikinOsc(MediaLonga : Integer, MediaCurta : Integer)

## Parâmetros:

MediaLonga: Determina o período da Média Longa para formação do cálculo. MediaCurta: Determina o período da Média Curta.

## Retorno:

Float

## Exemplos:

No exemplo, a variável "nCo" irá receber o valor do indicador Oscilador Chaikin, considerando 10 períodos para a média longa, e 3 para a curta.

## nCo := ChaikinOsc(10, 3);

## Função ChainSetup

## Descrição:

A função ChainSetup retorna o valor do indicador ChainSetup .



## Sintaxe:

ChainSetup

## Parâmetros:

Sem parâmetros.

## Retorno:

Float

## Exemplos:

No exemplo, a variável "cs" irá receber o dado do indicador ChainSetup.

## cs := ChainSetup;

## Função CohenPriceWave

## Descrição:

A função CohenPriceWave retorna o dado do indicador Cohen - Price Wave (desenvolvido por Rodrigo Cohen e equipe).

## Sintaxe:

CohenPriceWave(Ticks : Integer)|Histograma : Integer|

## Parâmetros:

Ticks: Níveis de preço.

Histograma: Determina o dado do histograma:

1 - Compra

2 - Venda

## Retorno:

Float

## Exemplos:




No exemplo, será atribuído à variável "cPriceWave", o retorno do indicador, considerando 15 ticks para o cálculo.

## cPriceWave := CohenPriceWave(15)|1|;

## Função CohenWeisWave

## Descrição:

A função CohenWeisWave retorna o dado do indicador Cohen - Weis Wave (desenvolvido por Rodrigo Cohen e equipe).

## Sintaxe:

CohenWeisWave(Ticks : Integer)

## Parâmetros:

Ticks: Relacionado ao valor de entrada do indicador.

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "cWeisWave", o retorno do indicador, considerando 15 ticks para o cálculo.

## cWeisWave:= CohenWeisWave(15);

## Função ContadorDeCandle

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

## nCandle:= ContadorDeCandle;

## Função DarvasBox

## Descrição:

A função DarvasBox retorna o valor do indicador Darvas Box .

## Sintaxe:

DarvasBox|Linha : Integer|

## Parâmetros:

Linha: Determina qual dado(Compra ou Venda) será obtido:

- 0 Compra

1 Venda

## Retorno:

Float

## Exemplos:

No exemplo, a variável "nDB" irá receber os valores(Dado: Venda) do indicador Darvas Box.




## Função DecisionPoints

## Descrição:

A função DecisionPoints retorna o valor do indicador Pontos de Decisão .

## Sintaxe:

DecisionPoints(Tipo : Integer, Linha : Integer)

## Parâmetros:

Tipo: Determina o tipo: Preço, Volume, Faixas de Volume e Variação:

- 0 - Tipo Preço:
- Linha: Dado da série que será obtido
- 0 - Abertura
- 1 - Máxima
- 2 - Mínima
- 3 - Fechamento
- 4 - Ajuste
- 1 - Tipo Volume:

Linha: Três maiores volumes dos períodos

- 0 - Dado volume
- 1 - Dado volume
- 2 - Dado volume
- 2 - Tipo Faixas de Volume:

Linha:

- 0 - Retorna o dado específico ao tipo
- 3 - Tipo Variação:
- Linha:
- 0 - Dado variação linha inferior (-2%)
- 1 - Dado variação linha inferior (-1%)
- 2 - Dado variação linha superior  (1%)
- 3 - Dado variação linha superior (2%)

## Retorno:

Float

## Exemplos:

No exemplo, a variável "DecisionP" irá receber o dado referente à máxima.

## DecisionP := DecisionPoints(0, 1);



## Função DiDiIndex

## Descrição:

A função DiDiIndex retorna o valor do indicador Didi Index , de acordo com o período e tipos de médias desejados.

## Sintaxe:

DiDiIndex(MediaReferencia  : Integer, TipoMediaReferencia : Integer, Media1 : Integer, TipoMedia1 : Integer, Media2 : Integer, TipoMedia2 : Integer)|Linha : Integer|

## Parâmetros:

MediaReferencia: Parâmetro para o período utilizado no cálculo da média de referência do indicador. TipoMediaReferencia: Determina qual média será considerada

- 0 - Aritmética
- 1 - Exponencial
- 2 - Welles Wilder
- 3 - Ponderada

Media1: Período utilizado no cálculo da média1 do indicador.

TipoMedia1: Determina qual média será considerada:

- 0 - Aritmética
- 1 - Exponencial
- 2 - Welles Wilder
- 3 - Ponderada

Media2 : Período utilizado no cálculo da média1 do indicador.

TipoMedia2 : Determina qual média será considerada:

- 0 - Aritmética
- 1 - Exponencial
- 2 - Welles Wilder
- 3 - Ponderada

Linha: Determina qual linha será obtida:

- 0 - Linha
- 1 - Linha 2

## Retorno:

Float

## Exemplos:

No exemplo, a variável "fdIndex " irá receber o valor da "linha 2", considerando 8(Média de Referência), 3(Média 1) e 20(Média 1) períodos, aplicando o tipo de média aritmética para o cálculo.

## fdIndex := DidiIndex(8,0,3,0,20,0)|1|;



## Função DiPDiM

## Descrição:

A função DiPDiM retorna o valor do indicador DI+/DI, de acordo com o período desejado.

## Sintaxe:

DiPDiM(Periodo : Integer)|Linha : Integer|

## Parâmetros:

Periodo: Período utilizado no momento do cálculo do indicador. Linha: Determina qual linha será obtida:

0 DI+

1 DI-

## Retorno:

Float

## Exemplos:

No exemplo, a variável "aux" irá receber o valor DI- do indicador DI+/DI-, considerando 14 período para o cálculo.

## aux := DiPDiM(14)|1|;

## Função DivergenceDetector

## Descrição:

A função DivergenceDetector retorna os pontos de alta ou baixa (PH ou PL) do ativo de acordo com o número de pivôs à esquerda e direita definidos nos parâmetros ou retorna a quantidade de indicadores considerados naquele candle relacionados aos indicadores considerados na divergência. Esse indicador retorna os pontos identificados pelo indicador Detector de Divergências .

## Sintaxe:

DivergenceDetector(LeftPivot : Integer, RightPivot : Integer, MACD : Boolean = 0, MACDHistogram : Boolean = 0, RSI : Boolean = 0, Stochastic: Boolean = 0, CCI: Boolean = 0, Momentum: Boolean = 0, OBV: Boolean = 0, Diosc: Boolean = 0, VWmacd: Boolean = 0, ChaikinMoneyFlow: Boolean = 0, MoneyFlowIndex: Boolean = 0)|Index : Integer|



## Parâmetros:

LeftPivot  : Número de candles à considerar como pivô à esquerda (apenas influencia cálculo de PH e PL)

RightPivot :

Número de candles à considerar como pivô à direita (apenas influencia cálculo de PH e PL)

MACD: Parâmetro opcional que indica se deve considerar o indicador MACD para cálculo de divergência dos indicadores

MACDHistogram: Parâmetro opcional que indica se deve considerar o indicador MACD Histograma para cálculo de divergência dos indicadores

RSI: Parâmetro opcional que indica se deve considerar o indicador RSI para cálculo de divergência dos indicadores

Stochastic: Parâmetro opcional que indica se deve considerar o indicador Estocástico para cálculo de divergência dos indicadores

CCI: Parâmetro opcional que indica se deve considerar o indicador CCI para cálculo de divergência dos indicadores

Momentum: Parâmetro opcional que indica se deve considerar o indicador Momentum para cálculo de divergência dos indicadores

OBV: Parâmetro opcional que indica se deve considerar o indicador OBV para cálculo de divergência dos indicadores

Diosc: Parâmetro opcional que indica se deve considerar o indicador Diosc para cálculo de divergência dos indicadores

VWmacd: Parâmetro opcional que indica se deve considerar o indicador VWmacd para cálculo de divergência dos indicadores

ChaikinMoneyFlow: Parâmetro opcional que indica se deve considerar o indicador Chaikin Money Flow para cálculo de divergência dos indicadores

MoneyFlowIndex: Parâmetro opcional que indica se deve considerar o indicador MoneyFlowIndex para cálculo de divergência dos indicadores

Index: Determina qual tipo de cálculo será obtido:

- 0 Retorna os valores de PH e PL para o ativo, onde os resultados são da seguinte forma:
- --1 caso o candle analisado seja PL
- -0 caso não seja nem PL nem PH
- -1 caso o candle analisado seja PH
- 1 Retorna os valores relacionados à divergência dos indicadores definidos da seguinte forma:
- -Soma a quantidade de indicadores que indicam divergência naquele candle e retorna o valor positivo caso seja um candle positivo ou negativo caso seja um candle negativo

## Retorno:

Float

## Exemplos:

No exemplo, a variável x irá receber o valor relacionado a PH/PL do candle a ser analisado considerando os valores passados para o LeftPivot e RightPivot (note que esse valor é independente dos indicadores passados opcionalmente por parâmetro)

## x := DivergenceDetector(5, 5)|0|;



No exemplo abaixo, a variável x irá receber o valor relacionado à soma dos indicadores que detectaram alguma divergência, ou nenhuma, no candle analisado. Nesse exemplo abaixo, estamos considerando apenas os indicadores MACD MACD Histograma , e RSI para o cálculo.

## x := DivergenceDetector(5, 5, True, True, True)|1|;

## Função DonchianCH

## Descrição:

A função DonchianCh retorna o valor do indicador Canal Donchian , de acordo com o período desejado.

## Sintaxe:

DonchianCh(Periodo : Integer)|Linha : Integer|

## Parâmetros:

Periodo: Período utilizado no momento do cálculo do indicador. Linha: Determina qual linha será obtida:

0 - Média

1 - Superior

2 - Inferior

## Retorno:

Float

## Exemplos:

No exemplo, a variável "nDC" irá receber o valor da linha inferior do indicador Canal Donchian, considerando 20 períodos para o cálculo.

## nDC := DonchianCh(20)|2|;

## Função DTOscillator

## Descrição:

A função DTOscillator retorna o valor do indicador DT Oscillator , conforme os parâmetros desejados.



## Sintaxe:

DTOscillator(PeriodoEstocastico : Integer, PeriodoSK : Integer, TipoSK : Integer, PeriodoSD : Integer, TipoSD : Integer)|Linha : Integer|

## Parâmetros:

PeriodoEstocastico: Período utilizado no momento do cálculo do indicador.

PeriodoSK: Período referente ao parâmetro "Período SK".

TipoSK: Determina qual média será considerada:

- 0 - Aritmética
- 1 - Exponencial
- 2 - Welles Wilder
- 3 - Ponderada

PeriodoSD: Período referente ao parâmetro "Período SD".

TipoSD: Determina qual média será considerada:

- 0 - Aritmética
- 1 - Exponencial
- 2 - Welles Wilder
- 3 - Ponderada

Linha: Determina qual linha será obtida:

- 0 Linha 1
- 1 Linha 2

## Retorno:

Float

## Exemplos:

No exemplo, a variável "dtOsc" irá receber o valor do indicador DT Oscillator, considerando 12(PeriodoEstocastico), 8(PeriodoSK), 5(PeriodoSD) períodos, e tipo aritmétia para o cálculo.

## dtOsc := DTOscillator(12, 8, 0, 5, 0)|1|;

## Função Envelope

## Descrição:

A função Envelope retorna o valor do indicador Envelope , de acordo com o período e média desejados.

## Sintaxe:

Envelope(Percentual : Float, PeriodoMedia : Integer, TipoMedia : Integer)|Linha : Integer|



## Parâmetros:

Percentual: Percentual utilizado no momento do cálculo do indicador.

PeriodoMedia: Período utilizado para o cálculo da média.

TipoMedia: Determina qual média será considerada:

- 0 - Aritmética
- 1 - Exponencial
- 2 - Welles Wilder
- 3 - Ponderada

Linha: Determina qual linha será obtida:

- 0 Ponto médio
- 1 Superior
- 2 Inferior

## Retorno:

Float

## Exemplos:

No  exemplo,  será  atribuído  à  variável  "nEnv"  o  dado  da  linha  superior  do  indicador  Envelope, considerando 5.0 como percentual, 20 períodos e tipo de média aritmética para o cálculo.

## nEnv := Envelope(5.0, 20 , 0)|1|;

## Função Euroinvest

## Descrição:

A função Euroinvest retorna o valor do indicador Euroinvest , conforme os parâmetros determinados.

## Sintaxe:

Euroinvest(Risco: Integer, ModoCalculo : Integer, Periodo : Integer, Desvio : Float, UsarVWAP : Boolean, UsarAtr : Boolean)

## Parâmetros:

Risco: Determina o tipo de perfil:

0 - Zero

1 - Um

2 - Dois

3 - Trés

ModoCalculo: Tipo de média:

0 - Aritmética



- 1 - Exponencial
- 2 - Welles Wilder
- 3 - Ponderada

Periodo: Período considerado para o cálculo da média.

Desvio: Desvio da média.

UsarVWAP: Determina se o VWAP será utiizado.

UsarAtr: Determina a habilitação do StopATR.

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "fEuro" o retorno da função, considerando o perfil Zero, tipode média aritmética, 21 períodos, com 2 de desvio, onde o VWAP e StopAtr estão habilitados.

## fEuro := Euroinvest(0, 0, 21, 2.0, True, True);

## Função FastStochastic

## Descrição:

A função FastStochastic retorna o valor do indicador Estocástico Rápido , de acordo com o período desejado.

Observação: Os parâmetros PeriodoMedia e TipoMedia são opcionais, caso não sejam determinados, serão utilizados os valores 14 e 1 respectivamente.

## Sintaxe:

FastStochastic(Periodo : Integer, PeriodoMedia : Integer, TipoMedia : Integer)

## Parâmetros:

Período: Período utilizado no momento do cálculo do indicador. PeriodoMedia: Período utilizado no momento do cálculo da média.

TipoMedia: Tipo da média a ser calculada pelo indicador:

- 0 - Aritmética
- 1 - Exponencial
- 2 - Welles Wilder
- 3 - Ponderada

## Retorno:

Float



## Exemplos:

No exemplo, a variável "nEstRap" irá receber o valor do indicador Estocástico Rápido, considerando 14 períodos para o cálculo.

## nEstRap := FastStochastic(14);

## Função FinancialVol

## Descrição:

A função FinancialVol retorna o valor do indicador Volume Financeiro , podendo-se incluir ou desconsiderar os dados: "volume projetado" e "leilão e trades diretos".

Observação: O parâmetro Agressores só será considerado para o cálculo do indicador caso o seja assinado o Opcional ' Plugin Tape Reading '. Caso não possua o opcional o indicador será sempre calculado como False, independente do que for inserido no campo.

## Sintaxe:

FinancialVol(VolumeProjetado : Boolean, Agressores : Boolean)

## Parâmetros:

VolumeProjetado: Determina se o volume irá considerar o dado projetado. Agressores: Determina se o volume irá desconsiderar o leilão e trades diretos.

## Retorno:

Float

## Exemplos:

No exemplo, a variável "vFinanceiro" irá receber o valor do indicador Volume Financeiro, desconsiderando os dados de "volume projetado" e "leilão e trades diretos".

vFinanceiro := FinancialVol(False, False);



## Função ForceIndex

## Descrição:

A função ForceIndex retorna o valor do indicador Force Index , de acordo com o período e tipo de média desejados.

## Sintaxe:

ForceIndex(Periodo : Integer, TipoMedia : Integer)

## Parâmetros:

Periodo: Período utilizado no momento do cálculo do indicador.

TipoMedia: Determina qual média será considerada:

- 0 - Aritmética
- 1 - Exponencial
- 2 - Welles Wilder
- 3 - Ponderada

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "nForce" o valor do indicador Force Index, considerando 13 períodos e tipo de média exponencial.

## nForce := ForceIndex(13, 1);

## Função FrassonATR

## Descrição:

A função FrassonATR retorna o valor do indicador Frasson ATR , de acordo com o fator e períodos desejados.

## Sintaxe:

FrassonATR(Fator : Float, PeriodoMaxMin : Integer, PeriodoATR : Integer)|Linha : Integer|

## Parâmetros:



Fator: Fator de multiplicação do ATR utilizado no momento do cálculo do indicador.

PeriodoMaxMin Determina o período de Máxima de Miníma.

PeriodoATR Determina o período do cálculo do ATR.

Linha: Determina qual linha será obtida:

- 0 Superior
- 1 Inferior

## Retorno:

Float

## Exemplos:

No exemplo, a variável "nFrasson" irá receber o valor da linha inferior do indicador Frasson ATR, considerando 0,03(Fator), 15(Período Máxima/Mínima) e 50(Período ATR) para o cálculo.

## nFrasson := FrassonATR(0.03, 15, 50)|1|;

## Função FrassonVH

## Descrição:

A função FrassonVH retorna o valor do indicador Frasson VH , de acordo com o fator e períodos desejados.

## Sintaxe:

FrassonVH(Fator : Float, PeriodoMaxMin : Integer, PeriodoVH : Integer)|Linha : Integer|

## Parâmetros:

Fator: Fator de multiplicação do ATR utilizado no momento do cálculo do indicador.

PeriodoMaxMin Determina o período de Máxima de Miníma.

PeriodoVH Determina o período do cálculo do VH.

Linha: Determina qual linha será obtida:

- 0 Superior

1 Inferior

## Retorno:

Float

## Exemplos:



No exemplo, a variável "nFrasson" irá receber o valor da linha superior do indicador Frasson VH, considerando 0,03(Fator), 15(Período Máxima/Mínima) e 50(Período VH) para o cálculo.

## nFrasson := FrassonVH(0.03, 15, 50);

## Função FullStochastic

## Descrição:

A função FullStochastic retorna o valor do indicador Estocástico Pleno , de acordo com o período desejado.

## Sintaxe:

FullStochastic(Periodo : Integer)

## Parâmetros:

Periodo: Período utilizado no momento do cálculo do indicador.

## Retorno:

Float

## Exemplos:

No exemplo, a variável "nPlen" irá receber o valor do indicador Estocástico Pleno, considerando 14 períodos para o cálculo.

## nPlen := FullStochastic(14);

## Função FuraChao

## Descrição:

A função FuraChao retorna o valor do indicador Fura-Chão , de acordo com o coeficiente e deslocamento desejados.

## Sintaxe:

FuraChao(Coeficiente : Float, Deslocamento : Integer)



## Parâmetros:

Coeficiente: Coeficiente utilizado no momento do cálculo do indicador.

Deslocamento: Determina quantos períodos anteriores serão utilizados como base no indicador.

## Retorno:

Float

## Exemplos:

No exemplo, a variável "fChao" irá receber o valor do indicador Fura-Chão, considerando 0.14(Coeficiente) e 1 período(Deslocamento) para o cálculo.

## fChao := FuraChao(0.14, 1);

## Função FuraTeto

## Descrição:

A função FuraTeto retorna o valor do indicador Fura-Teto , de acordo com o coeficiente e deslocamento desejados.

## Sintaxe:

FuraTeto(Coeficiente : Float, Deslocamento : Integer)

## Parâmetros:

Coeficiente: Coeficiente utilizado no momento do cálculo do indicador.

Deslocamento: Determina quantos períodos anteriores serão utilizados como base no indicador.

## Retorno:

Float

## Exemplos:

No exemplo, a variável "fTeto" irá receber o valor do indicador Fura-Teto, considerando 0.14(Coeficiente) e 1 período(Deslocamento) para o cálculo.

## fTeto := FuraTeto(0.14, 1);



## Função HeikinAshi

## Descrição:

A função HeikinAshi retorna o valor do indicador Heikin Ashi , de acordo com o período e tipo de média desejados.

## Sintaxe:

HeikinAshi(Media : Integer, TipoMedia : Integer)|Dado : Integer|

## Parâmetros:

Media: Media utilizado no momento do cálculo do indicador. TipoMedia: Determina qual média será considerada

- 0 - Aritmética
- 1 - Exponencial
- 2 - Welles Wilder
- 3 - Ponderada

Linha: Determina qual dado será obtido:

- 0 - Abertura
- 1 - Fechamento
- 2 - Máxima
- 3 - Mínima

## Retorno:

Float

## Exemplos:

No exemplo, a variável "HeikinAshi" irá receber o valor de fechamento do indicador Heikin Ashi, considerando 1(Período) e 0(Aritmética) para o cálculo.

## nHA := HeikinAshi(1, 0)|1|;

## Função HiLoActivator

## Descrição:



A função HiloActivator retorna o valor do indicador HiLo Activator , de acordo com o período desejado.

## Sintaxe:

HiloActivator(Periodo : Integer)|Linha : Integer|

## Parâmetros:

Periodo: Período utilizado no momento do cálculo do indicador.

Linha: Determina qual linha será obtida:

0 - Valor Indicador

1 - Tendência

Retorno para identificação da tendência:

0 - Baixa

1 - Alta

## Retorno:

Float

## Exemplos:

No exemplo, a variável "nHiLo" irá receber o valor do indicador HiLo Activator, considerando 3 períodos para o cálculo.

## nHiLo := HiloActivator(3);

## Função HistVolatility

## Descrição:

A função HistVolatility retorna o valor do indicador Volatilidade Histórica , de acordo com o período e tipo de média desejados.

## Sintaxe:

HistVolatility(Periodo : Integer, TipoMedia : Integer)

## Parâmetros:

Periodo: Período utilizado no momento do cálculo do indicador.

TipoMedia: Determina qual média será considerada:

0 - Aritmética



- 1 - Exponencial
- 2 - Welles Wilder

## nVH := HistVolatility(22, 2);

## vHSI := HSi();

## Retorno:

Float

## Exemplos:

No exemplo, a variável "nVH" irá receber o valor do indicador Volatilidade Histórica, considerando 22(Períodos) e tipo de média exponencial.

## Função HSI

## Descrição:

A função HSI retorna o dado do indicador IFH Índice de Força Harmônico (HSI) , conforme o período desejado.

## Sintaxe:

HSI

## Parâmetros:

Sem parâmetros.

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "vHSI" o retorno da função.



## Função HullMovingAverage

## Descrição:

A função HullMovingAverage retorna o valor do indicador Hull Moving Average , de acordo com o período desejado.

## Sintaxe:

HullMovingAverage(Periodo : Integer)

## Parâmetros:

Periodo: Período utilizado no momento do cálculo do indicador.

## Retorno:

Float

## Exemplos:

No exemplo, a variável "vHMV" irá receber o valor do indicador Hull Moving Average, considerando 8 períodos para o cálculo.

## vHMV := HullMovingAverage(8);

## Função IchimokuCloud

## Descrição:

A função IchimokuCloud retorna o valor do indicador Ichimoku Cloud , de acordo com os parâmetros desejados.

## Sintaxe:

IchimokuCloud(TenkanSen  : Integer, KijunSen : Integer, SenkouSpanB : Integer)|Linha : Integer|

## Parâmetros:

TenkanSen: Utilizado no momento do cálculo do indicador. KijunSen: Utilizado no momento do cálculo do indicador. SenkouSpanB: Utilizado no momento do cálculo do indicador. Linha: Determina qual linha será obtida:



0 - Tenkan-Sen

1 - Kijun-Sen

2 - Chikou Span

3 - Senkou Span A

4 - Senkou Span B

## Retorno:

Float

## Exemplos:

No exemplo, a variável "nIchimoku" irá receber o valor da linha "Senkou Span B" do indicador Ichimoku Cloud, considerando 9(Tenkan-Sen), 26(Kijun-Sen) e 52(Senkou Span B) para o cálculo.

## nIchimoku := IchimokuCloud(9, 26, 52)|4|;

## Função ImpliedVolatility

## Descrição:

A função ImpliedVolatility retorna o valor do indicador Volatilidade Implícita , utilizado para calcular Volatilidade Implícita de derivativos (opções), de acordo com o período desejado.

## Sintaxe:

ImpliedVolatility(ModeloTeorico : Boolean, TipoOpcao : Boolean)

## Parâmetros:

ModeloTeorico: Determina o modelo para o cálculo:

True - Black &amp; Scholes

False -

Binomial

TipoOpcao: Determina o tipo da opção.

True - Americana

False -

Européia

## Retorno:

Float

## Exemplos:



No exemplo, a variável "nIV" irá receber o valor do indicador Volatilidade Implícita, utilizando o modelo Black &amp; Scholes.

## nIV := ImpliedVolatility(True, False);

## Função KeltnerCH

## Descrição:

A função KeltnerCH retorna o valor do indicador Keltner Channels , de acordo com o período e tipo de média desejados.

## Sintaxe:

KeltnerCH(Desvio : Float, Periodo : Integer, TipoMedia : Integer)|Linha : Integer|

## Parâmetros:

Desvio: Desvio utilizado no momento do cálculo do indicador.

Periodo: Período utilizado para o cálculo do indicador.

TipoMedia: Determina qual média será considerada:

- 0 - Aritmética
- 1 - Exponencial
- 2 - Welles Wilder
- 3 - Ponderada

Linha: Determina qual linha será obtida:

- 0 - Superior
- 1 - Inferior

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "nCh" o valor da linha inferior do indicador Keltner Channels, considerando 2.0(Desvio), 20(Períodos) e tipo de média exponencial.

## nCh := KeltnerCH(2.0, 20, 1)|1|;



## Função KVO

## Descrição:

A função KVO retorna o valor do indicador KVO , de acordo com os períodos desejados.

## Sintaxe:

KVO(MediaLonga : Integer, MediaCurta : Integer, Sinal : Integer)|Dado : Integer|

## Parâmetros:

MediaLonga: Determina o período da Média Longa para formação do cálculo.

MediaCurta: Determina o período da Média Curta.

Sinal: Determina o sinal para a formação do cálculo.

Linha: Determina qual linha será obtida:

0 - Linha

1 - Histograma

## Retorno:

Float

## Exemplos:

No exemplo, a variável "n" irá receber o valor do histograma do indicador KVO, considerando 55(Média Longa), 34(Média Curta), 13(Sinal) para o cálculo.

## n := KVO(55, 34, 13)|1|;

## Função LinearRegressionChannel

## Descrição:

A função LinearRegressionChannel retorna os dados do indicador Canal de Regressão Linear.

## Sintaxe:

LinearRegressionChannel(Periodo : Integer; UsarDesvioSuperior : Boolean; DesvioSuperior : Float; UsarDesvioInferior : Boolean; DesvioInferior : Float)|Linha : Integer|



## Parâmetros:

Periodo: Total de candles considerados.

UsarDesvioSuperior: Define se o desvio superior será utilizado.

DesvioSuperior: Desvio superior considerado.

UsarDesvioInferior: Define se o desvio inferior será utilizado.

DesvioInferior: Desvio inferior considerado.

Linha: Determina qual linha será obtida:

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



nOBV := OBVAvg(10, 3);

## Função OnBalanceTR

## nOBTR := OnBalanceTR;

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



## PriceVolumeTrend

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



nRBG:= RBG;

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


## Float

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

## aux := SafeZoneDownTrend(2.0,

10, 0);

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


## Float

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
