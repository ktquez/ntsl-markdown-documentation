# Alarme

# Função Alert

## Descrição:
A função Alert tem como finalidade gerar um alarme ao usuário.

## Sintaxe:
Alert(Cor : Integer)

## Parâmetros:
Cor: Determina a cor desejada para o popup de notificação, no momento de execução do alarme.

Observação: Uma cor pode ser determinada a partir de uma função RBG, ou através de uma String com o nome da cor.

## Retorno:
Void: Sem retorno.

## Exemplos:
No exemplo a seguir, será emitido um alarme(e um popup com coloração vermelha) caso a média móvel aritmética de 9 períodos for menor que a média de 21.

```
if(Media(9, Close) < Media(21, Close)) then Alert(clRed);
```

# Back-Testing

# Função BuyAtMarket

## Descrição:
A função BuyAtMarket tem como funcionalidade realizar uma ordem de compra a mercado.

Importante: Caso o parâmetro de quantidade não seja especificado, a ordem será inserida considerando o campo Quantidade na aba de Execução do editor de estratégias, respeitando que o mínimo seja 1 lote. Na automação, a quantidade considerada é a configurada no campo "Quantidade por Ordem".

Quando o parâmetro é especificado, a estratégia ignora os campos de configuração de quantidade e irá utilizar a quantidade especificada pelo código. Essa quantidade deve ser múltipla do lote do ativo.

## Sintaxe:
BuyAtMarket(Quantidade : Float = '')

## Parâmetros:
Sem parâmetros.

## Retorno:
Void: Sem retorno.

## Exemplos:
No exemplo, caso a mínima do candle atual for igual a do candle anterior, será realizada uma simulação de ordem a mercado.

```
if (Low = Low[1]) then
  BuyAtMarket;
```

# Função BuyLimit

## Descrição:
A função BuyLimit possui como finalidade enviar uma ordem de compra do tipo limite.

Importante: Caso o parâmetro de quantidade não seja especificado, a ordem será inserida considerando o campo Quantidade na aba de Execução do editor de estratégias, respeitando que o mínimo seja 1 lote. Na automação, a quantidade considerada é a configurada no campo "Quantidade por Ordem".

Quando o parâmetro é especificado, a estratégia ignora os campos de configuração de quantidade e irá utilizar a quantidade especificada pelo código. Essa quantidade deve ser múltipla do lote do ativo.

## Sintaxe:
BuyLimit(Preco : Float, Quantidade : Float = '')

## Parâmetros:
Preço: Preço para a inserção da ordem. Quantidade: Quantidade da ordem.

## Retorno:
Void: Sem retorno.

## Exemplos:
No exemplo, caso a média exponencial de periodo1 for maior que a de periodo2, será criada a ordem de compra considerando o último preço.

```
medR := mediaExp(periodo1, close); 
medL := mediaExp(periodo2, close); 
if (medR[1] < medL[1]) and (medR > medL) then 
  BuyLimit(close, lote);
```

# Função BuyPosition

## Descrição:
A função BuyPosition retorna o tamanho da posição em lote da compra.

## Sintaxe:
BuyPosition

## Parâmetros:
Sem parâmetros.

## Retorno:
Integer

## Exemplos:
No exemplo, a variável "buyPos" irá receber o total da posição de compra.

```
buyPos := BuyPosition;
```

# Função BuyPositionQty

## Descrição:
A função BuyPositionQty retorna o tamanho da posição em quantidade da compra.

## Sintaxe:
BuyPositionQty

## Parâmetros:
Sem parâmetros.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "buyPos" irá receber o total da posição de compra.

```
buyPos := BuyPositionQty;
```

# Função BuyPrice

## Descrição:
A função BuyPrice retorna o preço de compra da posição.

## Sintaxe:
BuyPrice

## Parâmetros:
Sem parâmetros.

## Retorno:
Float

## Exemplos:
No exemplo, será atribuído à variável "pCompra" o valor de compra da posição.

```
pCompra := BuyPrice;
```

# Função BuyStop

## Descrição:
A partir da função BuyStop, é possível criar uma ordem do tipo Stop, onde o preço stop determina o preço de gatilho, e o limite especifica até qual preço a ordem poderá ser executada.

Importante: Caso o parâmetro de quantidade não seja especificado, a ordem será inserida considerando o campo Quantidade na aba de Execução do editor de estratégias, respeitando que o mínimo seja 1 lote. Na automação, a quantidade considerada é a configurada no campo "Quantidade por Ordem".

Quando o parâmetro é especificado, a estratégia ignora os campos de configuração de quantidade e irá utilizar a quantidade especificada pelo código. Essa quantidade deve ser múltipla do lote do ativo.

## Sintaxe:
BuyStop(Stop : Float, Limite : Float, Quantidade : Float = '')

## Parâmetros:
Stop: Valor do tipo Float que será o gatilho da ordem; Limite: Valor do tipo Float que será o limite de preço aceito para execução. Quantidade: Quantidade da ordem.

## Retorno:
Void: Sem retorno.

## Exemplos:
No exemplo, caso a mínima do candle atual for igual a do candle anterior, será inserida uma ordem de compra tipo stop, no nível especificado na variável 'pStop'.

```
if(Low = Low[1]) then
  BuyStop(pStop, pStop, lote);
```

# Função BuyToCoverAtMarket

## Descrição:
A função BuyToCoverAtMarket realiza o envio de uma ordem de compra a mercado, caso exista uma posição de venda em aberto.

Importante: Caso o parâmetro de quantidade não seja especificado, a ordem será inserida considerando o campo Quantidade na aba de Execução do editor de estratégias, respeitando que o mínimo seja 1 lote. Na automação, a quantidade considerada é a configurada no campo "Quantidade por Ordem".

Quando o parâmetro é especificado, a estratégia ignora os campos de configuração de quantidade e irá utilizar a quantidade especificada pelo código. Essa quantidade deve ser múltipla do lote do ativo.

## Sintaxe:
BuyToCoverAtMarket(Quantidade : Float = '')

## Parâmetros:
Quantidade: Quantidade da ordem.

## Retorno:
Void: Sem retorno.

## Exemplos:
No exemplo abaixo, caso a mínima atual seja menor que a mínima anterior e exista uma posição de venda, será executada uma ordem a mercado, utilizando a função BuyToCoverAtMarket para fechar a operação.

```
if (Low > Low[1] and Issold) then
  BuyToCoverAtMarket;
```

# Função BuyToCoverLimit

## Descrição:
A função BuyToCoverLimit possui como finalidade enviar uma ordem de compra, do tipo limite, para finalizar a operação.

Importante: Caso o parâmetro de quantidade não seja especificado, a ordem será inserida considerando o campo Quantidade na aba de Execução do editor de estratégias, respeitando que o mínimo seja 1 lote. Na automação, a quantidade considerada é a configurada no campo "Quantidade por Ordem".

Quando o parâmetro é especificado, a estratégia ignora os campos de configuração de quantidade e irá utilizar a quantidade especificada pelo código. Essa quantidade deve ser múltipla do lote do ativo.

## Sintaxe:
BuyToCoverLimit(Preco : Float,  Quantidade : Float = '')

## Parâmetros:
Preco: Preço para a inserção da ordem. Quantidade: Quantidade da ordem.

## Retorno:
Void: Sem retorno.

## Exemplos:
No exemplo, caso exista uma posição de venda, será inserida a ordem no preço de fechamento para zerar a posição.

```
if (IsSold) then
 BuyToCoverLimit(Close, lote) ;
```

# Função BuyToCoverStop

## Descrição:
A função BuyToCoverStop tem como funcionalidade enviar uma ordem do tipo Stop de compra, caso exista uma posição de venda no determinado ativo.

Importante: Caso o parâmetro de quantidade não seja especificado, a ordem será inserida considerando o campo Quantidade na aba de Execução do editor de estratégias, respeitando que o mínimo seja 1 lote. Na automação, a quantidade considerada é a configurada no campo "Quantidade por Ordem".

Quando o parâmetro é especificado, a estratégia ignora os campos de configuração de quantidade e irá utilizar a quantidade especificada pelo código. Essa quantidade deve ser múltipla do lote do ativo.

## Sintaxe:
BuyToCoverStop(Stop : Float, Limite : Float,  Quantidade : Float = '')

## Parâmetros:
Stop: Valor que será o gatilho da ordem.

Limite: Valor que será o limite do preço aceito para execução.

Quantidade: Quantidade da ordem.

## Retorno:
Void: Sem retorno.

## Exemplos:
No exemplo, caso a mínima do candle atual for igual a do candle anterior e exista uma posição de venda, será inserida uma ordem de compra tipo stop, no preço armazenado na variável 'pStop'.

```
if (Low = Low[1] and IsSold) then BuyToCoverStop(pStop, pStop);
```

# Função CancelPendingOrders

## Descrição:
A função CancelPendingOrders possui como recurso efetuar o cancelamento de todas ordens enviadas até o momento de sua chamada, no fluxo atual de execução, e as ordens abertas.

## Sintaxe:
CancelPendingOrders

## Parâmetros:
Sem parâmetros.

## Retorno:
Void: Sem retorno.

## Exemplos:
No exemplo, caso existam ordens pendentes, ocorrerá o cancelamento.

```
if (HasPendingOrders) then
  CancelPendingOrders;
```

# Função ClosePosition

## Descrição:
A função ClosePosition envia ordens para encerrar a posição. Esta função cancela todas ordens enviadas até o momento de sua chamada, no fluxo atual de execução, e as ordens abertas. Após confirmação do cancelamento das ordens, será enviada uma ordem para fechar a posição.

## Sintaxe:
ClosePosition

## Parâmetros:
Sem parâmetros.

## Retorno:
Void: Sem retorno.

## Exemplos:
No exemplo a seguir, se 'revTendencia' for verdadeiro, a posição será finalizada if (revTendencia = true) then

```
  ClosePosition;
```

# Função HasPendingOrders

## Descrição:
A função HasPendingOrders retorna se há ordens pendentes.

## Sintaxe:
HasPendingOrders

Parâmetros:

if (HasPendingOrders) then

```
  CancelPendingOrders;
```

# Função HasPosition

if (HasPosition) then
  ClosePosition;

## Descrição:
A função HasPosition retorna verdadeiro se a posição não é zero.

## Sintaxe:
HasPosition

## Parâmetros:
Sem parâmetros.

Retorno:
Boolean

## Exemplos:
No exemplo, caso existam ordens pendentes, ocorrerá o cancelamento.

## Descrição:
A função HasPosition retorna verdadeiro se a posição não é zero.

## Sintaxe:
HasPosition

## Parâmetros:
Sem parâmetros.

## Retorno:
Boolean

## Exemplos:
No exemplo, caso exista posição, ocorrerá o fechamento.

# Função IsBought

## Descrição:
A função IsBought tem como funcionalidade determinar se há uma posição de compra em aberto.

## Sintaxe:
IsBought

## Parâmetros:
Sem parâmetros.

## Retorno:
Boolean:
False - Não há posição em aberto.
True - Há posição em aberto.

## Exemplos:
No exemplo, caso exista uma posição de compra, haverá a aplicação de uma coloração (verde).

```
if (IsBought) then
  PaintBar(clGreen) ;
```

# Função IsSold

## Descrição:
A função IsSold tem como funcionalidade determinar se há uma posição de venda em aberto.

## Sintaxe:
IsSold

## Parâmetros:
Sem parâmetros.

## Retorno:
Boolean:
False - Não há posição em aberto.
True - Há posição em aberto.

```
if (IsSold) then
  PaintBar(clRed) ;
```

# Função MyPrice

mPrice := MyPrice;

# Função Position

False - Não há posição em aberto.
True - Há posição em aberto.

## Exemplos:
No exemplo, caso exista uma posição de venda, haverá a aplicação de uma coloração (vermelha).

## Descrição:
A função MyPrice retorna a média entre a máxima, mínima e fechamento.

## Sintaxe:
MyPrice

## Parâmetros:
Sem parâmetros.

Retorno:
Float

## Exemplos:
No exemplo, será atribuído à variável " mPrice ", o valor da função MyPrice .

Descrição:
```
vPosition:= Position;
```

# Função PositionQty

A função Position retorna o tamanho da posição em lote, positivo para compra e negativo para venda.

## Sintaxe:
Position

## Parâmetros:
Sem parâmetros.

## Retorno:
Integer

## Exemplos:
No exemplo, será atribuído à variável "vPosition", a posição.

## Descrição:
A função PositionQty retorna o tamanho da posição em quantidade, positivo para compra e negativo para venda.

## Sintaxe:
PositionQty

## Parâmetros:
Sem parâmetros.

## Retorno:
Float

## Exemplos:
No exemplo, será atribuído à variável "vPosition", a posição.
```
vPosition:= PositionQty;
```

# Função Price

## Descrição:
A função Price retorna o preço de compra ou venda da posição, dependendo se estiver comprado ou vendido.

## Sintaxe:
Price

## Parâmetros:
Sem parâmetros.

## Retorno:
Float

## Exemplos:
No exemplo, será atribuído à variável "vPrice", o preço da posição.
```
vPrice := Price;
```

# Função ReversePosition

## Descrição:
A função ReversePosition tem como funcionalidade realizar o envio de ordens, a fim de inversão da posição. Esta função cancela todas ordens enviadas até o momento de sua chamada, no fluxo atual de execução, e as ordens abertas. Após confirmação do cancelamento das ordens, será enviada uma ordem para reverter a posição.

## Sintaxe:
ReversePosition
```
if (Low < Low[1]) and (IsBought = True) then
  ReversePosition;
```

# Função SellPosition

## Parâmetros:
Sem parâmetros.

## Retorno:
Void: Sem retorno.

## Exemplos
No exemplo, caso a mínima do candle atual for menor a do candle anterior, e exista uma posição de compra, será realizada a reversão.

## Descrição:
A função SellPosition retorna o tamanho da posição em lote de venda.

## Sintaxe:
SellPosition

## Parâmetros:
Sem parâmetros.

## Retorno:
Integer

## Exemplos:
No exemplo, a variável " sellPos " irá receber o total da posição de venda
```
sellPos := SellPosition;
```

# Função SellPositionQty

## Descrição:
A função SellPositionQty retorna o tamanho da posição em quantidade de venda.

## Sintaxe:
SellPositionQty

## Parâmetros:
Sem parâmetros.

## Retorno:
Float

## Exemplos:
No exemplo, a variável " sellPos " irá receber o total da posição de venda

```
sellPos := SellPositionQty;
```

## Função SellPrice

## Descrição:
A função SellPrice retorna o preço de venda da posição.

## Sintaxe:
SellPrice

## Parâmetros:
Sem parâmetros.

Retorno:
Float

## Exemplos:
No exemplo, será atribuído à variável " pVenda " o valor de venda da posição.

```
pVenda := SellPrice;
```

## Função SellShortAtMarket

## Descrição:
A função S ellShortAtMarket tem como funcionalidade o envio de uma ordem a mercado de venda.

Importante: Caso o parâmetro de quantidade não seja especificado, a ordem será inserida considerando o campo Quantidade na aba de Execução do editor de estratégias, respeitando que o mínimo seja 1 lote. Na automação, a quantidade considerada é a configurada no campo "Quantidade por Ordem".

Quando o parâmetro é especificado, a estratégia ignora os campos de configuração de quantidade e irá utilizar a quantidade especificada pelo código. Essa quantidade deve ser múltipla do lote do ativo.

## Sintaxe:
SellShortAtMarket(Quantidade : Float = '')

## Parâmetros:
Quantidade: Quantidade da ordem.

## Retorno:
Void: Sem retorno.

## Exemplos:
No exemplo abaixo, será executada uma ordem de venda a mercado, caso 'newOpVenda' for verdadeiro.
```
sellshortatmarket ;
```

# Função SellShortLimit

## Descrição:
A função SellShortLimit possui como finalidade enviar uma ordem de venda do tipo limite.

Importante: Caso o parâmetro de quantidade não seja especificado, a ordem será inserida considerando o campo Quantidade na aba de Execução do editor de estratégias, respeitando que o mínimo seja 1 lote. Na automação, a quantidade considerada é a configurada no campo "Quantidade por Ordem".

Quando o parâmetro é especificado, a estratégia ignora os campos de configuração de quantidade e irá utilizar a quantidade especificada pelo código. Essa quantidade deve ser múltipla do lote do ativo.

## Sintaxe:
SellShortLimit(Preco : Float,  Quantidade : Float = '')

## Parâmetros:
Preco: Preço para a inserção da ordem. Quantidade: Quantidade da ordem.

## Retorno:
Void: Sem retorno.

## Exemplos:
No exemplo, caso a média exponencial de 9 períodos for menor que a de 21, será criada a ordem de venda considerando o preço armazenado na variável 'vPreco'.
```
if (MediaExp(9, Close) < MediaExp(21, Close)) then SellShortLimit(vPreco, lote) ;
```

# Função SellShortStop

## Descrição:
A função SellShortStop tem como finalidade enviar uma ordem de venda do tipo stop.

Importante: Caso o parâmetro de quantidade não seja especificado, a ordem será inserida considerando o campo Quantidade na aba de Execução do editor de estratégias, respeitando que o mínimo seja 1 lote. Na automação, a quantidade considerada é a configurada no campo "Quantidade por Ordem".

Quando o parâmetro é especificado, a estratégia ignora os campos de configuração de quantidade e irá utilizar a quantidade especificada pelo código. Essa quantidade deve ser múltipla do lote do ativo.

## Sintaxe:
SellShortStop(Stop : Float, Limite : Float = Market,  Quantidade : Float = '')

## Parâmetros:
Stop: Valor do tipo Float que será o gatilho da ordem; Limite: Valor do tipo Float que será o limite de preço aceito para execução. Quantidade: Quantidade da ordem.

## Retorno:
Void: Sem retorno.

## Exemplos:
No exemplo, caso a máxima atual for maior do que a anterior, será inserida uma ordem de venda stop, no preço armazenado na variável 'pAux'.
```
if (High > High[1]) then
  SellShortStop(pAux, pAux);
```

# Função SellToCoverAtMarket

## Descrição:
A função SellToCoverAtMarket tem como funcionalidade realizar o envio de uma ordem de venda a mercado, caso exista uma posição de compra.

Importante: Caso o parâmetro de quantidade não seja especificado, a ordem será inserida considerando o campo Quantidade na aba de Execução do editor de estratégias, respeitando que o mínimo seja 1 lote. Na automação, a quantidade considerada é a configurada no campo "Quantidade por Ordem".

Quando o parâmetro é especificado, a estratégia ignora os campos de configuração de quantidade e irá utilizar a quantidade especificada pelo código. Essa quantidade deve ser múltipla do lote do ativo.

## Sintaxe:
SellToCoverAtMarket

## Parâmetros:
Quantidade: Quantidade da ordem.

## Retorno:
Void: Sem retorno.

## Exemplos:
No exemplo abaixo, caso a máxima atual seja maior que a máxima anterior e exista uma posição de compra, será executada uma ordem a mercado,para fechar a operação.
```
if (High > High[1]) and (Isbought) then
  SellToCoverAtMarket ;
```

# Função SellToCoverLimit

## Descrição:
A função SellToCoverLimit possui como finalidade enviar uma ordem de venda, do tipo limite, para finalizar a operação.

Importante: Caso o parâmetro de quantidade não seja especificado, a ordem será inserida considerando o campo Quantidade na aba de Execução do editor de estratégias, respeitando que o mínimo seja 1 lote. Na automação, a quantidade considerada é a configurada no campo "Quantidade por Ordem".

Quando o parâmetro é especificado, a estratégia ignora os campos de configuração de quantidade e irá utilizar a quantidade especificada pelo código. Essa quantidade deve ser múltipla do lote do ativo.

## Sintaxe:
SellToCoverLimit(Preco : Float,  Quantidade : Float = '')

## Parâmetros:
Preco: Preço para a inserção da ordem. Quantidade: Quantidade da ordem.

## Retorno:
Void: Sem retorno.

## Exemplos:
No exemplo, caso exista uma posição de compra, será inserida a ordem no preço de fechamento para zerar a posição.
```
if (IsBought) then
  SellToCoverLimit(Close) ;
```

# Função SellToCoverStop

## Descrição:
A função SellToCoverStop tem como funcionalidade enviar uma ordem do tipo stop de venda, caso exista uma posição de compra no ativo.

Importante: Caso o parâmetro de quantidade não seja especificado, a ordem será inserida considerando o campo Quantidade na aba de Execução do editor de estratégias, respeitando que o mínimo seja 1 lote. Na automação, a quantidade considerada é a configurada no campo "Quantidade por Ordem".

Quando o parâmetro é especificado, a estratégia ignora os campos de configuração de quantidade e irá utilizar a quantidade especificada pelo código. Essa quantidade deve ser múltipla do lote do ativo.

## Sintaxe:
SellToCoverStop(Stop : Float, Limite : Float,  Quantidade : Float = '')

## Parâmetros:
Stop: Valor que será o gatilho da ordem. Limite: Valor que será o limite do preço aceito para execução. Quantidade: Quantidade da ordem.

## Retorno:
Void: Sem retorno.

## Exemplos:
No exemplo, caso a máxima do candle atual for maior que a do candle anterior e exista uma posição de compra, será inserida uma ordem de venda do tipo stop, no preço de 'pAux'.
```
if (High > High[1] and Isbough) then
  SellToCoverStop(pAux, pAux, lote);
```

# Função SendOrder

## Descrição:
A partir da função SendOrder, pode-se enviar ordens customizadas, determinando o lado, tipo e quantidade.

## Sintaxe:
SendOrder(Lado : Integer, Tipo : Integer, Quantidade : Float , Limite : Float, Stop : Float)

## Parâmetros:
Lado: Determina o lado da ordem: osBuy - Compra osSell - Venda Tipo: Tipo da ordem: otMarket - A mercado otLimit - Limite otStopLimit - Stop Quantidade: Quantidade de contratos. Limite: Limite do preço aceito para execução. Stop: Valor que será o gatilho da ordem.

## Retorno:
Void: Sem retorno.

## Exemplos:
No exemplo, será efetuada a inserção de uma ordem de compra, tipo Stop, no preço 17.44, com limite de execução até o nível 17.50.
```
SendOrder(osBuy, otStopLimit, 5, 17.50, 17.44);
```

# Função DailyResult

## Descrição:
A partir da função DailyResult, pode-se verificar o resultado diário das operações.

Observação: O parâmetro OpenResult é opcional, o valor default é verdadeiro.

## Sintaxe:
DailyResult(OpenResult : Boolean = True)

## Parâmetros:
OpenResult :
Se deve retornar o resultado aberto:
Verdadeiro : Retorna o resultado fechado + aberto.
Falso : Retorna apenas o resultado fechado.

## Retorno:
Float

## Exemplos:
No exemplo, será o retornado resultado fechado + aberto das operações do dia.
```
dResult := DailyResult(True); // Retorna o resultado fechado + aberto
```

# Função OpenResult

## Descrição:
A partir da função OpenResult, pode-se verificar o resultado diário das operações em aberto.

## Sintaxe:
OpenResult

## Parâmetros:
Sem parâmetros.

## Retorno:
Float

## Exemplos:
No exemplo, será o retornado resultado aberto das operações do dia.

```
dResult := OpenResult; // Retorna o resultado aberto
```

# Descrição:
A função XRay adiciona uma variável para ser exibida no painel de Raio-X da automação, na página de detalhes.

## Sintaxe:
XRay(strName : String, bValue : Boolean, strGroup : String, dValue : Float, ColorOn : Color, ColorOff : Color) :

## Parâmetros:
Determina o grupo da variável, Caso deixado como String vazia (''), será colocado no grupo strName: Determina o nome da variável a ser exibida bValue: Determina se a variável será verdadeira ou não strGroup: Geral

dValue: Determina um valor opcional a ser associado a variável.

ColorOn: Determina a cor que o campo da variável vai ficar quando o bValue for verdadeiro. Tem valor padrao azul

ColorOff: Determina a cor que o campo da variável vai ficar quando o bValue for falso. Tem valor padrão cinza

## Retorno:
Void: Sem retorno.

```
XRay ( "BuyConditionl" bByCorditiorl Close[2] Close[l] "Buy" Close[l] Close[o] "Buy" cifellow) XRav ("SellConditionl" "Sell" Close[o] Close[l] XRay ("SellCondition2" bSellCorditiorz "Sell" Close[l] Close[2] XRar ("SellCondition3" bSellconditior3 "Sell" Exemplos: O trecho de código a seguir irá cria 6 variáveis de Raio-X, divididas nos grupos de Buy e Sell:
```

Produzindo o seguinte resultado:

Nesse caso, tanto as BuyCondition2 e SellCondition2 eram verdadeiras, deixando os respectivos grupos com 1 variável verdadeira em cada.

# Depuração

# Função ConsoleLog

## Descrição:
A função ConsoleLog Imprime uma string no terminal de console para ajudar na depuração do código.

## Sintaxe:
ConsoleLog(Content : String, Color : Integer = clBlack)

## Parâmetros:
Content: String que irá ser impressa no console de depuração. Color: Cor da string impressa.

## Retorno:
Void. Sem retorno.

## Exemplos:
No exemplo, será impresso os dias e as variações do WDOFUT em que teve variação de mais de 4%.
```
ConsoleLog("Dias e variações do WDOFUT", clBlue);
```

# Calendário

# Função BarAnnualization

## Descrição:
A função BarAnnualization retorna o fator de anualização(raiz quadrada) baseado no intervalo da barra(diário = 365, semanal = 52, mensal = 12).

## Sintaxe:
BarAnnualization

## Parâmetros:
Sem parâmetros.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "nBA" irá receber o dado de retorno da função BarAnnualization .
```
nBA := BarAnnualization;
```

# Função BarDuration

temp := BarDuration;

## Descrição:
A função BarDuration retorna, em minutos, a duração da barra atual.

## Sintaxe:
BarDuration

## Parâmetros:
Sem parâmetros.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "temp" irá receber o dado da função BarDuration .
```
temp := BarDuration;
```
# Função BarDurationF

## Descrição:
A função BarDurationF retorna, em minutos, a duração da barra atual.

## Sintaxe:
BarDurationF

## Parâmetros:
Sem parâmetros.

## Retorno:
Float

## Exemplos:
No exemplo, a variável "temp" irá receber o dado da função BarDurationF .
```
temp := BarDurationF;
```
# Função Bartype

## Descrição:
A função Bartype retorna um código numérico referente ao período utilizado.

## Sintaxe:
Bartype

## Parâmetros:
Sem parâmetros.

## Retorno:
Inteiro:
-1 - Outros
1 - Intraday
2 - Diário
3 - Semanal
4 - Mensal

## Exemplos:
No exemplo, a variável "n" irá receber um inteiro referente ao tempo determinado.
```
n := Bartype;
```

# Função CalcDate

## Descrição:
A função CalcDate retorna um valor o qual representa uma data deslocada, obtida ao adicionar ou subtrair dias de uma data de referência.

Observação: Datas são representadas pelo tipo de dado "Integer", no formato: 1AnoMêsDia.

## Sintaxe:
CalcDate(DataReferencia : Integer, DiasDeslocamento : Integer)

## Parâmetros:
DataReferencia: Determina a data que será utilizada como base para o deslocamento. DiasDelocamento: Determina quantos dias serão adicionados ou subtraídos da data de referência.

## Retorno:
Integer

## Exemplos:
No exemplo abaixo, será visualizada, graficamente, a data resultante ao subtrair 14 dias da data de 26/10/2018.
```
Plot(CalcDate(1181026, -14)) ;
```

# Funcao CalcTime

## Descrição:
A função CalcTime retorna um valor o qual representa uma hora deslocada, obtida ao adicionar ou subtrair minutos de uma hora de referência.

Observação: Horas são representadas pelo tipo de dado "Integer", no formato(24 horas): HorasMinutos.

## Sintaxe:
CalcTime(HoraReferencia : Integer, MinutosDeslocamento : Integer)

## Parâmetros:
HoraReferencia: Determina a hora que será utilizada como base para o deslocamento; MinutosDeslocamento: Determina quantos minutos serão adicionados ou subtraídos da hora de referência.

## Retorno:
Integer

## Exemplos:
No exemplo abaixo, será visualizada, graficamente, a hora resultante ao deslocar 65 minutos a partir das 14h(Resultado: 1505).
```
Plot(CalcTime(1400, 65)) ;
```

# Função CloseD

## Descrição:
A função CloseD tem como finalidade retornar o valor de fechamento de um número determinado de dias atrás. Atualmente a função não é compatível com ativo diferente do selecionado no backtest, como ativos coletados usando a função asset por exemplo.

## Sintaxe:
CloseD(QuantidadeDiasAnteriores : Integer)

## Parâmetros:
QuantidadeDiasAnteriores:

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será atribuído à variável "nFechamento" o valor de fechamento de dois dias anteriores ao dia atual.
```
nFechamento := CloseD(2);
```

# Função CloseM

## Descrição:
Determina a quantidade desejada de dias anteriores.

A função CloseM tem como finalidade retornar o valor de fechamento de um número determinado de meses atrás.

## Sintaxe:
CloseM(QuantidadeMesesAnteriores : Integer)

## Parâmetros:
QuantidadeMesesAnteriores: Determina a quantidade desejada de meses anteriores.

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será atribuído à variável "mFechamento" o valor de fechamento de três meses anteriores ao mês atual.
```
mFechamento := CloseM(3);
```

# Função CloseW

## Sintaxe:
CloseM(QuantidadeMesesAnteriores : Integer)

## Parâmetros:
QuantidadeMesesAnteriores: Determina a quantidade desejada de meses anteriores.

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será atribuído à variável "mFechamento" o valor de fechamento de três meses anteriores ao mês atual.

## Descrição:
A função CloseW tem como finalidade retornar o valor de fechamento de um número determinado de semanas atrás.

## Sintaxe:
CloseW(QuantidadeSemanasAnteriores : Integer)

## Parâmetros:
QuantidadeSemanasAnteriores: Determina a quantidade desejada de semanas anteriores.

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será atribuído à variável "wFechamento" o valor de fechamento de duas semanas anteriores à semana atual.
```
wFechamento := CloseW(2);
```

# Função CloseY

## Descrição:
A função CloseY tem como finalidade retornar o valor de fechamento de um número determinado de anos atrás.

## Sintaxe:
CloseY(QuantidadeAnosAnteriores : Integer)

## Parâmetros:
QuantidadeAnosAnteriores:

## Retorno:
Float

## Exemplos:
No exemplo a seguir, será atribuído à variável "yFechamento" o valor de fechamento do ano anterior.
```
yFechamento := CloseY(1);
```

# Função CurrentAssetDate

## Descrição:
A função CurrentAssetDate retorna a data atual do ativo no gráfico.

Observação: Datas são representadas pelo tipo de dado "Integer", no formato: 1AnoMêsDia.

## Sintaxe:
Determina a quantidade desejada de anos anteriores.

## CurrentAssetDate

## Parâmetros:
Sem parâmetros.

## Retorno:
Integer

## Exemplos:
No exemplo, será atribuído à variável "nData" a data do ativo.

```
nData := CurrentAssetDate;
```

# Função CurrentDate

## Descrição:
A função CurrentDate possui como finalidade retornar a data atual do sistema.

Observação: Datas são representadas pelo tipo de dado "Integer", no formato: 1AnoMêsDia.

## Sintaxe:
CurrentDate

## Parâmetros:
Sem parâmetros.

Retorno:
Integer

## Exemplos:
No exemplo, será atribuído à variável "nData" a data do dia atual.
```
nData := CurrentDate;
```

# Função CurrentTime

nHora := CurrentTime;

## Descrição:
A função CurrentTime possui como finalidade retornar a hora atual do sistema.

Observação: Horas são representadas pelo tipo de dado "Integer", no formato: HHMM.

## Sintaxe:
CurrentTime

## Parâmetros:
Sem parâmetros.

## Retorno:
Integer

## Exemplos:
No exemplo, será atribuído à variável "nHora" a hora atual.
```
nHora := CurrentTime;
```

# Função Date

## Descrição:
A função Date possui como finalidade retornar a data do candle que está sendo analisado.

Observação: Datas são representadas pelo tipo de dado "Integer", no formato: 1AnoMêsDia.

## Sintaxe:
Date

## Parâmetros:
Sem parâmetros.

## Retorno:
Integer

## Exemplos:
No exemplo, será atribuído à variável "nData" a data do candle atual.
```
nData := Date;
```

# Função DayOfMonth

## Descrição:
A função DayOfMonth retorna o dia do mês de uma data específica.

Observação: Datas são representadas pelo tipo de dado "Integer", no formato: 1AnoMêsDia.

## Sintaxe:
DayOfMonth(Data : Integer)

## Parâmetros:
Data: Data para obter o dia.

## Retorno:
Integer

## Exemplos:
No exemplo, a variável "dAtual" irá receber o dia atual.
```
dAtual := DayOfMonth(CurrentDate);
```

# Função DayOfWeek

## Descrição:
A função DayOfWeek retorna o dia da semana de uma data específica.

Observação: Datas são representadas pelo tipo de dado "Integer", no formato: 1AnoMêsDia.

## Sintaxe:
DayOfWeek(Data : Integer)

## Parâmetros:
Data: Data para obter o dia da semana.

## Retorno:
Integer:
Referência de dias da semana:
- 0 - Domingo
- 1 - Segunda
- 2 - Terça
- 3 - Quarta
- 4 - Quinta
- 5 - Sexta
- 6 - Sábado

## Exemplos:
No exemplo, a variável "dAtual" irá receber o dia da semana atual.
```
dAtual := DayOfWeek(CurrentDate);
```

# Função DaysToExpiration

## Descrição:
A  função DaysToExpiration é  uma  função  a  quantidade  de  dias  úteis  restantes  até  a  terceira sexta-feira de um determinado mês e ano.

## Sintaxe:
DaysToExpiration(Mes : Integer, Ano : Integer)

## Parâmetros:
Mes: Determina o mês que se deseja a informação:
- 1 - Janeiro
- 2 - Fevereiro
- 3 - Março
- 4 - Abril
- 5 - Maio
- 6 - Junho
- 7 - Julho
- 8 - Agosto
- 9 - Setembro
- 10 - Outubro
- 11 - Novembro
- 12 - Dezembro

Ano: Determina o ano desejado para análise, onde deverá estar no formato: 1AnoDesejado.

## Retorno:
Integer

## Exemplos:
No  exemplo  abaixo,  a  variável  "nQtdDias"  irá  receber  a  quantidade  de  dias  úteis  até  a  terceira sexta-feira de dezembro/2016.
```
nQtdDias := DaysToExpiration(12, 116);
```

# Função ELDate

## Descrição:
A função ELDate possui como finalidade retorna uma data em EasyLanguage format(YYYMMDD).

Observação: Datas são representadas pelo tipo de dado "Integer", no formato: 1AnoMêsDia.

## Sintaxe:
ELDate(Ano : Integer, Mes : Integer, Dia : Integer)

## Parâmetros:
Ano:
Ano no formato YYYY.
Mes:
Mes no formato MM.
Dia:
Dia no formato DD.

## Retorno:
Integer

## Exemplos:
No exemplo, será atribuído à variável "nData" a data de 13/11/2018 no formato: 1181113.
```
nData := ELDate(2018, 11, 13);
```