# Atividade Banco de Dados
Atividade da faculdade para a criação de um banco de dados 

## :closed_book: My Books <img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif">
Vivemos em uma era em que a informação é essencial, e para uma amante de livros como eu, manter uma coleção organizada e acessível é uma tarefa significativa. Com o crescimento constante da minha biblioteca pessoal, percebi a necessidade de adotar uma abordagem mais estruturada e eficiente na gestão desses recursos valiosos.
Ao criar um banco de dados SQL dedicado à organização dos meus livros, estou buscando benefícios consideráveis em termos de acessibilidade, facilidade de busca e manutenção da coleção.
Este banco de dados foi projetado para gerenciar informações sobre minha coleção pessoal de livros, proporcionando uma estrutura organizada para armazenar dados relevantes. As entidades e relacionamentos foram cuidadosamente selecionados para representar aspectos importantes da gestão de livros, como detalhes da obra (Livro), informações sobre aquisição (Aquisicao), localização na estante (Posicao), gêneros (Genero), autores (Autor) e adaptações (Adaptacao).
<br>
<hr>

## :book: **Modelagem de Banco de Dados para Gestão de Livros**:

| **Entidades:** | **Atributos:**| **Relacionamento:** |
| :---         |     :---:      |      :---:  |
| 1. **Livro:**   |id_Livro (identificador único), nome, cor, avaliação, páginas, status, volume, formato, ilustrado, id_Aquisicao (chave estrangeira referenciando Aquisicao), id_Posicao (chave estrangeira referenciando Posicao)    | Relaciona-se com Aquisicao e Posicao para rastrear informações de aquisição e localização do livro.  |
| 2. **Autor:**    | id_Autor (identificador único), nome, nacionalidade, editora.     | Relaciona-se com Livro através da tabela intermediária Livro_Autor. |
| 3.**Livro_Autor:**    |id_LivroAutor(identificador único), id_Livro (chave estrangeira referenciando Livro), id_Autor (chave estrangeira referenciando Autor). | É uma tabela intermediária que serve para estabelecer uma relação muitos para muitos entre as tabelas Livro e Autor |
| 4. **Aquisicao:**     | id_Aquisicao (identificador único), valor, meio, ano.     | Estabelece uma relação com Livro por meio da chave estrangeira id_Aquisicao.     |
| 5. **Posicao:**     | id_Posicao (identificador único), nicho, posição.       | Vincula-se a Livro usando a chave estrangeira id_Posicao.      |
| 6. **Genero:**    | id_Genero (identificador único), genero.       |  Conecta-se a Livro por meio da tabela intermediária LivroGenero.     |
| 7.**LivroGenero:**     | id_LivroGenero (identificador único), id_Livro (chave estrangeira referenciando Livro), id_Genero (chave estrangeira referenciando Genero).      |Liga Livro e Genero, permitindo a associação de múltiplos gêneros a um livro.|
|8. **Adaptacao:**     | id_Adaptacao (identificador único), id_Livro (chave estrangeira referenciando Livro), tipo, streaming, idioma, dublado, legendado, duração, ano.      | Vincula-se a Livro por meio da chave estrangeira id_Livro.     |

## :pencil: **Modelagem Conceitual**:
<img src= /img/MC.png >

## :page_facing_up: **Modelagem Lógica**:

<img src= /img/ML.png >

## :bar_chart: **Dados**:

**1.📚 Livro:**
   
| id_Livro | Nome   | Cor | Avaliação   | Páginas | Status | Volume | Formato | Ilustrado | id_Aquisicao | id_Posicao |
|:--------:|:----------------------------------------:|:--------:|:-----------:|:-------:|:-------------:|:------:|:---------------:|:---------:|:------------:|:----------:|
|    1     | Gente Ansiosa                            | Amarelo  | Amei - 10   |  368    | Finalizado    | Único  | Capa Comum      | Não       |      14      |      5     |
|    2     | Marionete                                | Vermelho | Bom - 6     |  352    | Finalizado    | Único  | Capa Comum      | Não       |      5       |      4     |
|    3     | A Promessa                               | Azul     |             |  352    | Parado        | Único  | Capa Comum      | Não       |      5       |      1     |
|    4     | Vermelho, Branco e Sangue Azul            | Azul     | Amei- 9.5   |  416    | Finalizado    | Único  | Capa Dura       | Sim       |      16      |      5     |
|    5     | O que Aconteceu com Annie                | Preto    | Muito Bom - 8|  288    | Finalizado    | Único  | Capa Dura       | Não       |      17      |      5     |
|    6     | O homem de Giz                           | Preto    | Regular - 6 |  272    | Finalizado    | Único  | Capa Dura       | Não       |      17      |      5     |
|    7     | Mordida                                  | Vermelho | Amei - 9    |  112    | Finalizado    | Único  | Capa Dura       | Sim       |      15      |      1     |
|    8     | Belo Mundo, onde você está               | Azul     | Muito Bom - 8|  352    | Finalizado    | Único  | Capa Comum      | Não       |      10      |      5     |
|    9     | A Troca                                  | Bege     | Amei - 9    |  352    | Finalizado    | Único  | Capa Comum      | Não       |      10      |      5     |
|    10    | Verity                                   | Preto    | Muito Bom - 9.5| 320   | Finalizado    | Único  | Capa Comum      | Não       |      10      |      6     |
|    11    | Jantar Secreto                           | Branco   |             |  368    | Não Lido      | Único  | Capa Comum      | Sim       |      14      |      1     |
|    12    | Mo Dao Zu Shi (Livro 1)                  | Branco   |             |  456    | Não Lido      | Livro 1| Capa e Contra Capa | Sim    |      16      |      3     |
|    13    | Mo Dao Zu Shi (Livro 2)                  | Branco   |             |  472    | Não Lido      | Livro 2| Capa e Contra Capa | Sim    |      16      |      3     |
|    14    | Heartstopper (Livro 1)                   | Verde    | Muito Bom - 8|  288    | Finalizado    | Livro 1| Capa Dura       | Sim       |      10      |      2     |
|    15    | Heartstopper (Livro 2)                   | Laranja  | Muito Bom - 8|  320    | Finalizado    | Livro 2| Capa Dura       | Sim       |      11      |      2     |
|    16    | A Seleção (Livro 1)                      | Verde    | Muito Bom - 9.5| 363   | Finalizado    | Livro 1| Capa Comum      | Não       |      7       |      2     |
|    17    | A Elite (Livro 2)                        | Vermelho | Muito Bom - 9.5| 360   | Finalizado    | Livro 2| Capa Comum      | Não       |      7       |      2     |
|    18    | A Escolha (Livro 3)                      | Branco   | Muito Bom - 9.5| 352   | Finalizado    | Livro 3| Capa Comum      | Não       |      7       |      2     |
|    19    | Manual de Assassinato para boas garotas  | Cinza    | Muito Bom - 9.5| 448   | Finalizado    | Livro 1| Capa Comum      | Sim       |      10      |      1     |
|    20    | Estranhos à Beira-Mar (Umibe no Étranger)| Azul   | Bom - 7     |  310    | Finalizado    | Único  | Capa Comum      | Sim       |      16      |      5     |
|    21    | Orgulho e Preconceito                    | Rosa   |                |  288    | Não Lido    | Único  | Capa Dura         | Não       |      2       |      1     |
|    22    | Oliver Twist                             | Bege   |                |  744    | Não Lido    | Único  | Capa Comum        | Não       |      6       |      4     |
|    23    | É assim que acaba                        | Rosa   |                |  368    | Não Lido    | Livro 1| Capa Comum        | Não       |      8       |      4     |
|    24    | Alice no Pais da Maravilhas              | Preto  |                |  144    | Não Lido    | Único  | Capa Comum        | Sim       |      8       |      1     |
|    25    | Os Sete Maridos de Evelyn Hugo           | Verde  | Muito Bom - 8  |  360    | Finalizado  | Único  | Capa Comum        | Não       |      8       |      4     |

**2.🧑‍💻 Autor:**

| id_Autor | Nome                        | Nacionalidade | Editora               |
|:--------:|:---------------------------:|:-------------:|:----------------------:|
|    1     | Alice Oseman                | Britânica      | Seguinte               |
|    2     | Beth O’Leary                | Britânica      | Intrínseca             |
|    3     | C. J. TUDOR                 | Britânica      | Intrínseca             |
|    4     | Casey McQuiston             | Estadunidense  | Seguinte               |
|    5     | Charles Dickens             | Britânico      | Pé da Letra             |
|    6     | Colleen Hoover               | Estadunidense  | Galera                 |
|    7     | Daniel Cole                 | Britânico      | Editora Arqueiro       |
|    8     | Fredrik Backman             | Sueco          | Rocco                  |
|    9     | Harlan Coben                | Estadunidense  | Editora Arqueiro       |
|   10     | Holly Jackson               | Britânica      | Intrínseca             |
|   11     | Jane Austen                 | Britânica      | Principis              |
|   12     | Kanna Kii                   | Japonesa       | New Pop                |
|   13     | Kiera Cass                  | Estadunidense  | Seguinte               |
|   14     | Lewis Carroll                | Britânico      | Faro Editorial         |
|   15     | Mo Xiang Tong Xiu (MXTX)    | Chinesa        | New Pop                |
|   16     | Raphael Montes              | Brasileiro     | Companhia das Letras   |
|   17     | Sally Rooney                | Irlandesa      | Companhia das Letras   |
|   18     | Sarah Andersen              | Estadunidense  | Seguinte               |
|   19     | Taylor Jenkins Reid         | Estadunidense  | Paralela               |


**3.💰 Aquisição:**

| id_Aquisicao | Valor              | Meio        | Ano  |
|:------------:|:------------------:|:-----------:|:----:|
|      1       | até 20 reais       | Amazon      | 2021 |
|      2       | até 30 reais       | Amazon      | 2021 |
|      3       | até 40 reais       | Amazon      | 2021 |
|      4       | mais de 40 reais   | Amazon      | 2021 |
|      5       | até 20 reais       | Americanas  | 2021 |
|      6       | até 20 reais       | Shopping    | 2021 |
|      7       | mais de 40 reais   | Magazine    | 2021 |
|      8       | até 20 reais       | Americanas  | 2022 |
|      9       | mais de 40 reais   | Americanas  | 2022 |
|     10       | até 20 reais       | Amazon      | 2022 |
|     11       | até 30 reais       | Amazon      | 2022 |
|     12       | até 40 reais       | Amazon      | 2022 |
|     13       | mais de 40 reais   | Amazon      | 2022 |
|     14       | até 20 reais       | Amazon      | 2023 |
|     15       | até 30 reais       | Amazon      | 2023 |
|     16       | até 40 reais       | Amazon      | 2023 |
|     17       | mais de 40 reais   | Amazon      | 2023 |

**4.🗃️ Posição:**

| id_Posicao | id_Livro | Estante |
|:----------:|:--------:|:-------:|
|     1      |    1     |    A    |
|     2      |    1     |    B    |
|     3      |    2     |    B    |
|     4      |    2     |    C    |
|     5      |    3     |    C    |
|     6      |    3     |    D    |

**5.🎭 Genero:**

| id_Genero |       Genero        |
|:---------:|:-------------------:|
|     1     |       Romance       |
|     2     | Misterio e Suspense |
|     3     | Humor e comédia     |
|     4     |  Policial Crime      |
|     5     |       Thriller       |
|     6     |    Psicológico       |
|     7     |      Fantasia        |
|     8     |    Contemporâneo     |
|     9     |       Distópia       |
|     10    |         LGBT+         |
|     11    |        Novela        |
|     12    | HQs e Graphic Novel  |
|     13    |         Mangá         |
|     14    |       Ficção         |

**6.📽️ Adaptação:**

| id_Adaptacao | id_Livro |   Tipo   | Streaming  | Idioma | Dublado | Legendado | Duração |   Ano    |
|:------------:|:--------:|:--------:|:----------:|:------:|:-------:|:---------:|:-------:|:--------:|
|      1       |    2     |Não possui|            |        |         |           |         |          |
|      2       |    3     |Não possui|            |        |         |           |         |          |
|      3       |    5     |Não possui|            |        |         |           |         |          |
|      4       |    6     |Não possui|            |        |         |           |         |          |
|      5       |    7     |Não possui|            |        |         |           |         |          |
|      6       |    8     |Não possui|            |        |         |           |         |          |
|      7       |   16     |Não possui|            |        |         |           |         |          |
|      8       |   17     |Não possui|            |        |         |           |         |          |
|      9       |   18     |Não possui|            |        |         |           |         |          |
|      10      |    9     | Anunciado|            |        |         |           |         |          |
|      11      |   10     | Anunciado|            |        |         |           |         |          |
|      12      |   11     | Anunciado|            |        |         |           |         |          |
|      13      |   19     | Anunciado|            |        |         |           |         |          |
|      14      |   23     | Anunciado|            |        |         |           |         |          |
|      15      |   25     | Anunciado|            |        |         |           |         |          |
|      16      |   22     |  Filme   |  Youtube   | Inglês |   Não   |    Sim    | 01:50   |   1948   |
|      17      |   24     | Animação |  Disney    | Inglês |   Sim   |    Sim    | 01:15   |   1951   |
|      18      |   21     |  Série   |  Youtube   | Inglês |   Sim   |    Sim    | 1 temp  |   1995   |
|      19      |   21     |  Filme   |  Amazon    | Inglês |   Sim   |    Sim    | 02:10   |   2005   |
|      20      |   22     |  Filme   |  Amazon    | Inglês |   Sim   |    Sim    | 02:10   |   2005   |
|      21      |   22     |  Série   | Apple TV   | Inglês |   Não   |    Sim    | 1 temp  |   2007   |
|      22      |   24     |  Filme   |  Disney    | Inglês |   Sim   |    Sim    | 01:48   |   2010   |
|      23      |   12     | Animação |  WeTv      | Chinês |   Não   |    Sim    | 3 temp  |   2018   |
|      24      |   13     | Animação |  WeTv      | Chinês |   Não   |    Sim    | 3 temp  |   2018   |
|      25      |   12     |  Série   |  Netflix   | Chinês |   Não   |    Sim    | 40 eps  |   2019   |
|      26      |   13     |  Série   |  Netflix   | Chinês |   Não   |    Sim    | 40 eps  |   2019   |
|      27      |   20     |  Filme   | Crunchyroll | Japonês|   Não   |    Sim    | 01:00   |   2020   |
|      28      |    1     |  Série   |  Netflix   | Sueco  |   Sim   |    Sim    | 6 eps   |   2021   |
|      29      |   14     |  Série   |  Netflix   | Inglês |   Sim   |    Sim    | 3 temp  |   2022   |
|      30      |   15     |  Série   |  Netflix   | Inglês |   Sim   |    Sim    | 3 temp  |   2022   |
|      31      |    4     |  Filme   |  Amazon    | Inglês |   Sim   |    Sim    | 02:00   |   2023   |
|      32      |   22     |  Teatro  |            |Português|         |           | 02:00   |   2023   |


## ⚙️ **CRUD**:
**CREATE (criar), READ (ler), UPDATE (atualizar) e DELETE (excluir).**

**✏️ CREATE (criar)**

**📘 READ (ler)**
**:arrows_counterclockwise: UPDATE (atualizar)**
**🗑️ DELETE (excluir)**
