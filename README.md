# PrecisionRecall-ImageFeatureExtractor
Algoritmo para Gerar Gráficos de Precision/Recall em arquivos de descritores de características de imagens. Autor: Marcela Xavier Ribeiro

Entrada

Nome arquivo entrada (ver formato de arquivo de entrada, no próximo slide)
Número de colunas do arquivo (incluindo coluna de id e coluna de categoria).
String no formato [+i1,i2,...,ik] com índices dos atributos que serão usados em uma das linhas do gráfico de precision/recall. O índice do primeiro atributo do vetor de característica é 1.  Colocar sempre na ordem ik < iL para L>k.

Arquivo de Entrada

Cada item deve estar separado por espaço;
Cada transação deve estar em uma linha diferente;
As linhas contem as transações ou objetos a serem analisados
O primeiro atributo é o identificador da imagem;
O segundo atributo é o identificador da categoria da imagem.
Os demais atributos são os dados dos vetores de características da imagem;

Exemplo:
1 1 0.87 0.987 0.11
2 0 0.77 0.787 0.71

Arquivo de Saída: out.plt

set title “Precision x Recall
set xlabel “Recall"
set ylabel “Precision"
plot '-' title 'attribs=natrib1’  with linespoints 1

####################
#attribs=natrib1
1 0.8
2 0.2
3 0.2
End

pause -1

Arquivo - Saída
Precisão= TRO/TO
Revocação = TRO/TR 
TRO -> total de relevantes obtidas
TR -> total de relevantes da base
TO -> total de obtidas

Algoritmo eficiente:
  -Para cada pivô da base
    Faça um ranking das imagens de acordo com a distancia em relação ao pivô
    Faça TO variar de 1 até N (todos os objetos da base)
      -Calcule os valores de precisão e revocação para cada TO
    Para cada intervalo de Recall encontre a média-aritmética do valor de precision e coloque nos pontos do gráfico
