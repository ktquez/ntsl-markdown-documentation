## Função DiMaisDiMenos

## Descrição:

O exemplo DiMaisDiMenos possui a implementação do indicador DI+/DI, onde foi determinado um parâmetro (input) para o período.

Observação: o exemplo com o código fonte está disponível no editor de estratégias, para visualizá-lo, acesse o menu: "abrir &gt; exemplos".

## Sintaxe:

DiMaisDiMenos(Periodo : Integer)

## Parâmetros:

Periodo: Período utilizado no momento do cálculo do indicador.

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "aux" o retorno do indicador criado.

## aux := DiMaisDiMenos(14);

## Função IFR

## Descrição:




A função IFR retorna o valor(tipo clássico) do indicador IFR , de acordo com o período.

Observação: o exemplo com o código fonte está disponível no editor de estratégias, para visualizá-lo, acesse o menu: "abrir &gt; exemplos".

## Sintaxe:

IFR(Periodo : Integer)

## Parâmetros:

Periodo: Período utilizado no momento do cálculo do indicador.

## Retorno:

Float

## Exemplos:

No exemplo, a variável "aux" irá receber o valor do indicador IFR, considerando 2 períodos para o cálculo.

## aux := IFR(2);

## Função Media

## Descrição:

A função Media retorna o valor do indicador Média Móvel, tipo aritmética.

Observação: o exemplo com o código fonte está disponível no editor de estratégias, para visualizá-lo, acesse o menu: "abrir &gt; exemplos".

## Sintaxe:

Media(Periodo : Integer, TipoSerie : Serie)

## Parâmetros:

Período:

Período utilizado no momento do cálculo do indicador. Série que será considerada para o cálculo.

TipoSerie:

## Retorno:


## Float

## Exemplos:

No exemplo, será atribuído à variável "vMed" o valor do indicador Média Móvel(Aritmética), considerando 100 períodos, e a série de fechamento(Close) para o cálculo.

vMed := Media(100, Close);

## Função MediaExp

## Descrição:

A função MediaExp retorna o valor do indicador Média Móvel, tipo exponencial.

Observação: o exemplo com o código fonte está disponível no editor de estratégias, para visualizá-lo, acesse o menu: "abrir &gt; exemplos".

## Sintaxe:

MediaExp(Periodo : Integer, TipoSerie : Serie)

## Parâmetros:

Periodo: Período utilizado no momento do cálculo do indicador. TipoSerie: Série que será considerada para o cálculo.

## Retorno:

Float

## Exemplos:

No exemplo, será atribuído à variável "vMed" o valor do indicador Média Móvel(Exponencial), considerando 100 períodos, e a série de fechamento(Close) para o cálculo.

vMed := MediaExp(100, Close);






## Função PaintVar

## Descrição:

A  função PaintVar possui  a  implementação  de  uma  estratégia  de  coloração,  a  qual  compara  se  o fechamento do último candle é positivo ou negativo em relação ao fechamento do(candle) anterior, e, como indicador, apenas retorna o último preço do ativo.

Observação: o exemplo com o código fonte está disponível no editor de estratégias, para visualizá-lo, acesse o menu: "abrir &gt; exemplos".

## Sintaxe:

PaintVar

## Parâmetros:

Sem parâmetros.

## Retorno:

Float

## Exemplos:

No exemplo, será plotado o último preço, onde a regra de coloração correspondente poderá ser aplicada sobre o indicador.

## Plot(PaintVar) ;

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
