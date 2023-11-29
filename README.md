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
| 3. **Aquisicao:**     | id_Aquisicao (identificador único), valor, meio, ano.     | Estabelece uma relação com Livro por meio da chave estrangeira id_Aquisicao.     |
| 4. **Posicao:**     | id_Posicao (identificador único), nicho, posição.       | Vincula-se a Livro usando a chave estrangeira id_Posicao.      |
| 5. **Genero:**    | id_Genero (identificador único), genero.       |  Conecta-se a Livro por meio da tabela intermediária LivroGenero.     |
| 6.**LivroGenero:**     | id_LivroGenero (identificador único), id_Livro (chave estrangeira referenciando Livro), id_Genero (chave estrangeira referenciando Genero).      |Liga Livro e Genero, permitindo a associação de múltiplos gêneros a um livro.|
|7. **Adaptacao:**     | id_Adaptacao (identificador único), id_Livro (chave estrangeira referenciando Livro), tipo, streaming, idioma, dublado, legendado, duração, ano.      | Vincula-se a Livro por meio da chave estrangeira id_Livro.     |

## :pencil: **Modelagem Conceitual**:
<img src= /img/MC.png >

## :page_facing_up: **Modelagem Lógica**:

<img src= /img/ML.png >


