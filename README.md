## Modelagem do banco de dados

&nbsp;&nbsp;&nbsp;&nbsp;O modelo relacional de banco de dados foi feito no site `https://sql.toad.cz/` organizando as informações de forma que se relacionem de acordo com o propósito do projeto. O modelo apresenta cada tabela como uma entidade que possui uma lista de atributos, estabelecendo relações entre elas. Abaixo estão detalhadas as tabelas e seus respectivos atributos, sendo eles as chaves primárias e chaves estrangeiras:

<div align="center">
<sub>Figura 1 - Estrutura do banco de dados em XML</sub>
<img src="personaldb.jpg" width="100%">
<sup>Fonte: Material produzido pelo autor (2024)</sup>
</div>

### Tabela: `User`

- **id** (INTEGER, CHAVE PRIMÁRIA)
- **name** (TEXT)
- **email** (TEXT)
- **password** (TEXT)
- **gender** (TEXT)
- **birthday** (DATE)
- **country** (INTEGER)
- **type** (BINARY)

### Tabela: `Extra_user_info`

- **id** (INTEGER, CHAVE PRIMÁRIA)
- **user_id** (INTEGER, CHAVE ESTREANGEIRA referenciando `User(id)`)
- **education_level** (VARCHAR)
- **university** (VARCHAR)

### Tabela: `Student`

- **id** (INTEGER, CHAVE PRIMÁRIA)
- **user_id** (INTEGER, CHAVE ESTRANGEIRA referenciando `User(id)`)
- **country_text_** (TEXT)
- **profile_type** (VARCHAR)
- **happiness_meter** (INTEGER)

### Tabela: `Group`

- **id** (INTEGER, CHAVE PRIMÁRIA)
- **name** (TEXT)
- **tutor_id** (INTEGER, CHAVE ESTRANGEIRA referenciando `User(id)`)
- **student_id** (BINARY, CHAVE ESTRANGEIRA referenciando `Student(id)`)
- **student_id** (BINARY, CHAVE ESTRANGEIRA referenciando `Student(id)`)
- **student_id** (BINARY, CHAVE ESTRANGEIRA referenciando `Student(id)`)
- **student_id** (BINARY, CHAVE ESTRANGEIRA referenciando `Student(id)`)
- **student_id** (BINARY, CHAVE ESTRANGEIRA referenciando `Student(id)`)
- **student_id** (BINARY, CHAVE ESTRANGEIRA referenciando `Student(id)`)
- **student_id** (BINARY, CHAVE ESTRANGEIRA referenciando `Student(id)`)

### Tabela: `Question`

- **id** (INTEGER, CHAVE PRIMÁRIA)
- **question_text** (INTEGER)
- **alternatives** (VARCHAR)
- **question_type** (VARCHAR)

### Tabela: `QuestionAnswer`

- **id** (INTEGER, CHAVE PRIMÁRIA)
- **student_id** (INTEGER, CHAVE ESTRANGEIRA referenciando `Student(id)`)
- **question_id** (INTEGER, CHAVE ESTRANGEIRA referenciando `Question(id)`)
- **question_answer** (VARCHAR)
- **answer_date_time** (DATETIME)

## Relacionamentos

- A tabela `User` é central, conectando-se com `Group`, `Message` e `Student` através de chaves estrangeiras.
- `Question` e `QuestionAnswer` ligam perguntas às respostas dos usuários.
- `Student` se conecta a `Group`, relacionando jogadores com seus grupos e conecta-se à `question_answer` para mostrar qual estudante forneceu determinada resposta.

&nbsp;&nbsp;&nbsp;&nbsp;As linhas desempenham o papel de conectar as tabelas, relacionando informações e atributos. Por exemplo, a tabela "User" se relaciona com a tabela "Group" através do atributo "group_id", indicando que todos os usuários pertencem a um grupo. Esta estrutura facilita o entendimento e a visualização do processo interno de dados, ajudando na implantação de um banco de dados para um projeto ou servindo como material de consulta para compreender o fluxo de informações.