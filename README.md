# Similaridades entre textos - Caso COH-PIAH

## Introdução

John é monitor na matéria de Introdução à Produção Textual I na Penn State University (PSU). Durante esse período, John descobriu que uma epidemia de COH-PIAH estava se espalhando pela PSU. Esses doença rara e altamente contagiosa faz com que as pessoas contaminadas produzam textos extremamente semelhantes de forma involuntária. Após a entrega da primeira redação, John desconfiou que alguns alunos estavam sofrendo de COH-PIAH. John, se preocupando com a saúde da turma, resolveu buscar um método para identificar os casos de COH-PIAH. Para isso, ele necessita da sua ajuda para desenvolver um programa que o auxilie a identificar os alunos contaminados.

## Detecção de autoria

Utilizando diferentes estatísticas do texto, é possível identificar aspectos que funcionam como uma “assinatura” do autor. Diferentes pessoas possuem diferentes estilos de escrita, algumas preferindo sentenças mais curtas, outras preferindo sentenças mais longas.

Essas “assinatura” pode ser utilizada para detecção de plágio, evidência forense, ou nesse caso, para detectar a grave doença COH-PIAH.

## Traços linguísticos

Nesse exercício utilizaremos as seguintes estatísticas para detectar a doença:

* Tamanho médio de palavra: Média simples do número de caracteres por palavra.
* Relação Type-Token: Número de palavras diferentes utilizadas em um texto divididas pelo total de palavras.
* Razão Hapax Legomana: Número de palavras utilizadas uma vez dividido pelo número total de palavras.
* Tamanho médio de sentença: Média simples do número de caracteres por sentença.
* Complexidade de sentença: Média simples do número de frases por sentença.
* Tamanho médio de frase: Média simples do número de caracteres por frase.

## Funcionamento do programa

Diversos estudos foram compilados e hoje se conhece precisamente a assinatura de um portador de COH-PIAH. Seu programa deverá receber diversos textos e calcular os valores dos diferentes traços linguísticos da seguinte forma:

* Tamanho médio de palavra é a soma dos tamanhos das palavras dividida pelo número total de palavras.
* Relação Type-Token é o número de palavras diferentes dividido pelo número total de palavras. Por exemplo, na frase "O gato caçava o rato", temos 5 palavras no total (o, gato, caçava, o, rato) mas somente 4 diferentes (o, gato, caçava, rato). Nessa frase, a relação Type-Token vale 45=0.8
* Razão Hapax Legomana é o número de palavras que aparecem uma única vez dividido pelo total de palavras. Por exemplo, na frase "O gato caçava o rato", temos 5 palavras no total (o, gato, caçava, o, rato) mas somente 3 que aparecem só uma vez (gato, caçava, rato). Nessa frase, a relação Hapax Legomana vale 35=0.6
* Tamanho médio de sentença é a soma dos números de caracteres em todas as sentenças dividida pelo número de sentenças (os caracteres que separam uma sentença da outra não devem ser contabilizados como parte da sentença).
* Complexidade de sentença é o número total de frases divido pelo número de sentenças.
* Tamanho médio de frase é a soma do número de caracteres em cada frase dividida pelo número de frases no texto (os caracteres que separam uma frase da outra não devem ser contabilizados como parte da frase).
Após calcular esses valores para cada texto, você deve comparar com a assinatura fornecida para os infectados por COH-PIAH. O grau de similaridade entre dois textos, a e b, é dado pela fórmula:

Sab=∑6i=1||fi,a−fi,b||6

Onde:

* Sab é o grau de similaridade entre os textos a e b;
* fi,a é o valor de cada traço linguístico i no texto a; e
* fi,b é o valor de cada traço linguístico i no texto b.

Perceba que quanto mais similares a e b forem, menor Sab será. Para cada texto, você deve calcular o grau de similaridade com a assinatura do portador de COH-PIAH e no final exibir qual o texto que mais provavelmente foi escrito por algum aluno infectado.

Exemplo:
```
$ > python3 coh_piah.py

Bem-vindo ao detector automático de COH-PIAH.


Entre o tamanho medio de palavra: 4.79
Entre a relação Type-Token: 0.72
Entre a Razão Hapax Legomana: 0.56
Entre o tamanho médio de sentença: 80.5
Entre a complexidade média da sentença: 2.5
Entre o tamanho medio de frase: 31.6

Digite o texto 1 (aperte enter para sair): Navegadores antigos tinham uma frase gloriosa:"Navegar é preciso; viver não é preciso". Quero para mim o espírito [d]esta frase, transformada a forma para a casar como eu sou: Viver não é necessário; o que é necessário é criar. Não conto gozar a minha vida; nem em gozá-la penso. Só quero torná-la grande,ainda que para isso tenha de ser o meu corpo e a (minha alma) a lenha desse fogo. Só quero torná-la de toda a humanidade;ainda que para isso tenha de a perder como minha. Cada vez mais assim penso.Cada vez mais ponho da essência anímica do meu sangueo propósito impessoal de engrandecer a pátria e contribuirpara a evolução da humanidade.É a forma que em mim tomou o misticismo da nossa Raça.

Digite o texto 2 (aperte enter para sair): Voltei-me para ela; Capitu tinha os olhos no chão. Ergueu-os logo, devagar, e ficamos a olhar um para o outro... Confissão de crianças, tu valias bem duas ou três páginas, mas quero ser poupado. Em verdade, não falamos nada; o muro falou por nós. Não nos movemos, as mãos é que se estenderam pouco a pouco, todas quatro, pegando-se, apertando-se, fundindo-se. Não marquei a hora exata daquele gesto. Devia tê-la marcado; sinto a falta de uma nota escrita naquela mesma noite, e que eu poria aqui com os erros de ortografia que trouxesse, mas não traria nenhum, tal era a diferença entre o estudante e o adolescente. Conhecia as regras do escrever, sem suspeitar as do amar; tinha orgias de latim e era virgem de mulheres. 

Digite o texto 3 (aperte enter para sair): NOSSA alegria diante dum sistema metafisico, nossa satisfação em presença duma construção do pensamento, em que a organização espiritual do mundo se mostra num conjunto lógico, coerente a harmônico, sempre dependem eminentemente da estética; têm a mesma origem que o prazer, que a alta satisfação, sempre serena afinal, que a atividade artística nos proporciona quando cria a ordem e a forma a nos permite abranger com a vista o caos da vida, dando-lhe transparência.

Digite o texto 4 (aperte enter para sair):

O autor do texto 2 está infectado com COH-PIAH
```
