## Material Teórico
# Ferramenta para Modelagem ER
    1. Introdução
    2. BrModelo
    3. Criando um Diagrama de Entidade-Relacionamento (DER)
    4. MySQL Workbench

## OBJETIVO DE APRENDIZADO
    -> Estudar um pouco sobre duas ferramentas CASE que auxiliam no desenvolvimento
    do projeto de MOdelagem de dados:
        -> BrModelo
        -> MySQL Workbench

### Introdução
    -> Estudaremos sobre duas ferramentas CASE que auxiliam
    no desenvolvimento do projeto de Modelagem de Dados: BrModelo e MySQL
    Workbench.

    /**
    *   CASE - Computer-aided software engineering (Engenharia de Software Auxiliada por Computador)
    */

    -> Uma das grandes vantagens oferecidas pelas ferramentas CASE de banco de
    dados é a possibilidade de criar scripts SQL a partir de um diagrama de 
    entidaderelacionamento (DER).

    -> O SQL (Structure Query Language) é uma linguagem de programação usada
    para armazenar e gerenciar dados no SGBD (MySql, Oracle, SqlServer). SQL foi
    a primeira linguagem comercial introduzida para o modelo relacional do E. Codd.
    Hoje, quase todo o SGBD usa o SQL como a linguagem de banco de dados padrão.
    SQL é usado para executar todo o tipo de operações de dados, como criar e excluir
    tabelas; inserir, atualizar e excluir dados, e selecionar e exibir dados em um SGBD. 


### BrModelo
    -> A ferramenta BrModelo é uma ferramenta freeware que possibilita o desenvolvimento 
    de diagramas DER, modelo lógico, e exportar esses artefatos em formato
    de script SQL para criação de tabelas no banco de dados (CÂNDIDO, 2007).

#### Criando um Diagrama de Entidade-Relacionamento (DER)
##### Gerandoo Esquema Lógico a partir do DER
    -> Para gerar o esquema lógico (modelo lógico) a partir de um DER no BrModelo,
    basta clicar com o botão direito do mouse sobre um local vazio no palco. Em
    seguida, clique na opção “Gerar esquema lógico”

    -> É, nessa etapa, que no BrModelo, temos a possibilidade de alterar o tipo de
    dado para determinado Banco de dados.

    /**
    *   IMPORTANTE
    *   Caso queira gerar um script para banco de dados Oracle, deve-se alterar os tipos de
    *   dados especifi camente para Oracle e, assim, por diante.
    */
    
##### Gerando o script SQL
    -> Para gerar o script SQL referente ao DER que criamos e o modelo lógico que
    criamos, até agora, no BrModelo, basta clicar com o botão direito do mouse sobre
    um local vazio no palco. Em seguida, clique na opção “Gerar esquema Físico”

#### MySQL Workbench 
    -> A ferramenta MySQL Workbench é uma ferramenta CASE gratuita, que
    oferece as seguintes funcionalidades:
        • Desenvolvimento SQL: Funcionalidade para consultas MySQL. Permite
        que o usuário se conecte a um banco de dados existente, edite e execute
        consultas SQL.
        • Modelagem de Dados: Permite a modelagem visual de banco de dados
        (criação do modelo lógico e físico).
        • Administração de Banco de Dados: Funcionalidade de administrador do
        MySQL. Possui uma Interface gráfica para iniciar / parar servidores, criar
        contas de usuário, editar arquivos de configuração etc.

##### Visão Geral da Ferramenta
##### Criando o Modelo Lógico
    -> Onde, cada propriedade, quando selecionada, atribui uma funcionalidade ao
    atributo, essas propriedades são:
        • PK: Chave primária (O atributo é uma chave primária).
        • NN: Não nulo (o atributo não pode ficar vazio).
        • UQ: Único (o valor do atributo deve ser único em toda a tabela)
        • BIN: Binário (o atributo só aceita valores binários).
        • UN: Unsigned (não permite valores negativos no atributo).
        • ZF: Zero fill (preenche os espaços vazios com zero à esquerda até o tamanho
        padrão do campo).
        • AI: Autoincremento (o valor do atributo é gerado automaticamente pelo SGBD).

    -> Para concluir, a configuração do atributo “id_Funcionario”, selecione as opções
    “PK” e “NN”.

##### Gerando o script SQL
    -> Para gerar o script SQL referente ao modelo lógico que criamos, clique no
    “File\ Export\ Forward Enginner SQL CREATE Script ...”.

    -> Na tela seguinte, marque as opções: 
        1. Omit Schema Qualifier in Object Names;
        2. Do Not Create Users. Only Export Privileges 
        3. Don’t create view placeholder tables.
        4. Avance
        5. clicando no botão “Next”
        6. Export MySQL Table Objects” e 
        7. avance
        8. clicando no botão “Next”.