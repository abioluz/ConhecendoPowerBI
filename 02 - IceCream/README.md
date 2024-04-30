# Sobre IceCream

Algum tempo atrás, pesquisando no kaggle.com <https://www.kaggle.com/datasets/vinicius150987/ice-cream-revenue> encontrei um desafio bem interessante para treinar regressão linear. Os dados são de Vendas de Sorvetes(\$) pela Temperatura (ºC).

A primeira dificuldade que achei foi na importação dos dados. A questão é que na tabela .csv os dados possuem o ponto como separador de unidade e a virgula para separar os dados. Então na hora que importa os dados o Power BI separa as colunas e retira o ponto. Então o valor que era 45.58214 passa a ser 4558214. Para resolver isso, fui em transformar e fiz uma troca de caracteres de “.” para “,”. Provavelmente esta é a pior forma de se fazer. Pois se houvesse virgula separando a casa das dezenas o problema seria maior.

Fazer o gráfico de dispersão e colocar a linha de tendência foi mamão com açúcar. Mas a fução da reta, coeficiente de regressão… Isso tive que fazer na aba DAX usando a seguinte fórmula retirada da documentação <https://learn.microsoft.com/pt-br/dax/linestx-function-dax>:

`EVALUATE LINESTX('IceCreamData',[Vendas],[Temperatura])`

Estava sentindo, missão cumprida. Mas me lembrei…. E os gráficos de histograma? E então descobri que não tem o gráfico de histograma e nem o boxplot. Dei uma olhada e tem como baixar os gráficos, porem fiquei encucado…. O gráfico de histograma não daria para ser feito com o gráfico de barras? E sim, dá para ser feito com um pequeno trabalho. O que faltou seria a linha da normal para ser colocada junto. Mas isso terá que ficar para outro dia.

# Conclusão: 

A sensação que eu sentia com o matplotlib era que tudo tinha que ser feito na mão. Poderia já ter alguma abstração nos gráficos de dispersão em que a linha de tendência já fosse mostrada ou facilitada. Esta sensação é a mesma que senti ao fazer este desafio. No gráfico de dispersão, tive que recorrer ao DAX para poder obter a função da reta. Tem a opção de linha de tendência mas para a função tem que recorrer outro meio. Dai entra a questão, no Excel se obtêm isso clicando em uma caixinha nas configurações do gráfico. Espero que isso seja falta de experiência com a ferramenta e não uma escolha técnica dos desenvolvedores.

O gráfico boxplot não é nativo. Mas dá para relevar, pois pode ser instalado.

O Gráfico de histograma jé é diferente. Ele tem e não tem ao mesmo tempo. O que tem é um gráfico de barras que pode ser adaptado. A linha normal infelizmente tem que ser calculada para poder lançar. O que volta na discussão acima.

Bem, como tenho tempo limitado, vou voltar a este problema em outra hora.
