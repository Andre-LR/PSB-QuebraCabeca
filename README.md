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

Imagem Resultado

<img src = "https://github.com/bramos013/PSB-QuebraCabeca/blob/main/resultado.jpg" height = "150em" />

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


OBS: O código leva um tempo para obter o resultado final. Usando os valores do bloco de código comentado, obtem-se resultados satisfatórios de maneira mais otimizada.
