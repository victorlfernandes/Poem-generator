# Álgebra Linear e Aplicações (SME0142) - Trabalho Final

Nome: Victor Lucas de Almeida Fernandes


Número USP: 12675399

Link do vídeo de apresentação: [aqui](https://drive.google.com/file/d/19L_05i7I27-dgnMWjJLzR7eSMVQVAJlk/view?usp=share_link)

# Cadeias de Markov

## Introdução

Escolhi desenvolver o trabalho sobre as cadeias de Markov pois, ao pesquisar sobre o tema, achei muito interessante as suas aplicações.
As principais que encontrei foram no motor de pesquisa do Google (PageRank), na teoria de filas, na modelagem genética de populações e na composição de músicas algorítimicas.

Ademais, por elas estarem intimamente relacionadas com a matéria de estatística, que estou cursando, e de processos estocásticos, do próximo semestre, acredito que além de auxiliar na consolidação dos aprendizados de Álgebra Linear, o trabalho também ajuda em outras disciplinas da graduação.

No entanto, a maior motivação para a escolha desse tópico foram os geradores de texto de Markov, aplicação sobre a qual o trabalho será desenvolvido.

## Parte teórica

### Propriedade de Markov
Um processo estocástico satisfaz a propriedade de Markov quando podemos fazer previsões sobre o seu futuro somente com base no seu estado atual. Assim, desconsideramos a sequência de eventos precedentes no cálculo da distribuição de probabilidade do próximo estado.

### Cadeia de Markov
Denotamos como cadeia de Markov um processo estocástico que segue a propriedade de markoviana.

### Aplicação da definição nos geradores de texto de Markov

Vamos usar um gerador probabilístico de textos para exemplificar o conceito apresentado.

Considere as seguintes frases como banco de treinamento do nosso algoritmo:
- Oi , tudo bem ?
- Oi , está certo ?
- Oi , está bem ?

Seja cada palavra um estado do nosso processo. Conseguimos definir a distribuição de probabilidade de transição de uma palavra para outra na nossa amostra.

Por exemplo, se o estado atual é a palavra *Oi*, temos 100% de certeza que o próximo estado será uma vírgula.

Se o estado atual é uma vírgula, temos 33% de chance de ir para o estado *tudo* e 67% para o estado *está*.

E assim sucessivamente. Repare que a probabilidade que calculamos para o estado da vírgula não depende do passado do processo, ou seja, da probabilidade do estado *Oi*. Por isso, podemos considerar que estamos tratando de um processo de Markov.

Com base nessa lógica, conseguimos montar a seguinte cadeia de Markov:

![picture](https://drive.google.com/uc?id=1mqU3s-s3mvn4_z2skRmM2eFO4AVX9Ihn)

A aplicação desse conceito que será desenvolvida consiste em um gerador de poemas.

O banco de frases será obtido com base em diversos poemas de amor com palavras semelhantes. O algoritmo irá criar um poema original baseado nas probabilidades de transição de estados de Markov derivadas desse textos.

Ao representar as cadeias computacionalmente, seguindo o nosso exemplo, teríamos o seguinte:
- Oi: [vírgula]
- Vírgula: [está, está, tudo]
- tudo: [bem]
- está: [bem, certo]
- bem: [?]
- certo: [?]


Ao sortear aleatóriamente uma palavra dessa lista de estados sucessores, obtemos a probabilidade desejada.

## Exemplos de resultados obtidos

### Exemplo 1

![image](https://github.com/victorlfernandes/Poem-generator/assets/87901904/683d2115-de10-4558-8a6f-c19079fa9d21)

### Exemplo 2

![image](https://github.com/victorlfernandes/Poem-generator/assets/87901904/bc2858f5-3d3d-4663-8746-402c1cd14a58)
