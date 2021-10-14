## Quebra-Cabeca Digital

Repositório desenvolvido para implementação de um quebra cabeça digital em C

### Objetivo

O objetivo deste trabalho é a implementação de um algoritmo para a resolução de um “quebra-cabeça digital”. Imagine que você tem duas imagens coloridas: as imagens não precisam ter necessariamente o mesmo tamanho, mas precisam ter a mesma área, ou seja, a mesma quantidade de pontos (pixels).

O algoritmo deverá reposicionar os pixels da primeira imagem (origem) para produzir uma nova imagem que seja o mais parecida possível   com a segunda (desejada). O detalhe é que cada pixel da imagem de origem só pode ser utilizado exatamente uma vez, ou seja, é como se fosse um gigantesco quebra cabeça, onde o objetivo é colocar os pixels em uma determinada ordem.

Exemplo:
Imagem de Origem

<img src = "https://github.com/bramos013/PSB-QuebraCabeca/blob/main/dali2.jpg" height = "150em" />

Imagem Desejada

<img src = "https://github.com/bramos013/PSB-QuebraCabeca/blob/main/dali1.jpg" height = "150em" />

Imagem Resultado(Em processamento)

<img src = "https://github.com/bramos013/PSB-QuebraCabeca/blob/main/resultado.jpg" height = "150em" />

### Pesquisa

Colorimetria é a ciência que investiga o fenômeno de percepção de cores pelos seres humanos. Em sua etimologia temos do latim COLOR (cor) e METRIA (medida) sugerindo que se trata da mensuração da temperatura da cor, seu grau de matiz, saturação e luminosidade.

Na Colorimetria, o termo Espaço de Cores Absoluto corresponde a um espaço de cores em que a diferença de percepção entre as cores está diretamente relacionada com as distâncias entre as cores representadas por pontos no espaço de cores. 

Para reposicionarmos os pixels de modo a ocuparem uma posição em que a cor da imagem de SAIDA é semelhante a da imagem DESEJADA, basicamente, devemos selecionar os pixels que possuem a menor diferença de cor possível. Para isso, temos que calcular uma métrica de distância, considerando as dimensões lineares R, G, B definindo o espaço de cores.

Grande parte das definições usam a distância euclidiana para calcular essa métrica. Um dos melhores métodos para comparar duas cores pela percepção humana é o CIE76, que utiliza a fórmula abaixo, onde R, G e B correspondem às dimensões RGB de cada imagem. A diferença é chamada Delta-E, e uma curiosidade é que quando a diferença é menor que 1, o olho humano não consegue reconhecer a diferença.


<p align=center>distância² = (R2 - R1)² +  (G2 - G1)² + (B2 - B1)²<p> 


Essa métrica funcionará nos casos em que uma cor deve ser comparada a apenas uma outra cor simplesmente para saber a diferença(distância) entre elas. Quanto menor a distância, mais semelhantes elas são.


## Raciocínio 
- A imagem de ORIGEM foi copiada para a imagem de SAIDA, a fim de que pudessemos manipular os pixels da SAIDA;
- Selecionamos um pixel da imagem de SAIDA para ser o ponto de referência da comparação;
- Para cada comparação de um Pixel de ORIGEM, verificamos a semelhança dele com cada pixel da imagem DESEJADA através do método DistanciaRGB;
- O pixel de SAIDA será posicionado na mesma posição do pixel da imagem DESEJADA que for mais semelhante com ele, ou seja, o que tiver menor DistanciaRGB;
- A comparação é repetida 1000 vezes a fim de deixar mais preciso o resultado da troca;

## Validação
Para fins de testes, utilizamos o método de validação e obteve-se o seguinte resultado:


Validando...
[04 01 0A] [04 01 0C] [05 02 0B] [05 02 0B] [05 02 0B] [05 02 0B] [05 02 0B] [05 02 0B] 
[04 01 0A] [04 01 0C] [05 02 0B] [05 02 0B] [05 02 0B] [05 02 0B] [05 02 0B] [05 02 0B] 
>>>> TRANSFORMAÇÃO VÁLIDA <<<<< 


OBS: O código com as imagens originais leva um tempo para obter o resultado final. Utilizando imagens com resoluções menores, obtem-se resultados satisfatórios de maneira mais otimizada.
