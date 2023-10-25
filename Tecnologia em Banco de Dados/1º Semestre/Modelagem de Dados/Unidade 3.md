# UNIDADE 3  - Modelo EP - Part 1
    1. Introdução ao Modelo - ER
    2. Entidades, ENtidades Fortes e Fracas

## OBJETIVO
    -> Estudar o Modelo de Entidade relacional, o modelo de dados mais 
    utilizados no mercado. Nessa primeira parte veremos os conceitos de 
    entidades, entidades fortes e fracas.

### Introdução ao Modelo-ER
    ->  O Modelo entidade-relacionamento (Modelo-ER) é a técnica mais difundida e
    utilizada para modelagem de dados (HEUSER, 2010). O modelo ER foi proposto
    pela primeira vez por Peter Pin-Shan Chen, do Instituto de Tecnologia de
    Massachusetts (MIT), na década de 1970, e descreve o modelo conceitual de um
    banco de dados, apoiando-se principalmente na representação de entidades do
    mundo real e as associações entre elas

    /**
    *   IMPORTANTE
    *   Segundo HEUSER, 2010, podemos definir entidade como um “conjunto de objetos da
    *   realidade modelada sobre os quais se deseja manter informações no banco de dados”
    */

    ->  O Modelo-ER,tornou-se um padrão amplamente aceito para modelagem de dados.
    No modelo ER, a estrutura de um banco de dados é retratada como um diagrama,
    chamado de diagrama de entidade-relacionamento (DER), embora sejam capazes de 
    descrever qualquer sistema, os diagramas de entidaderelacionamento são mais 
    frequentemente associados a bancos de dados. Em particular, os diagramas de 
    entidade-relacionamento são comumente utilizados durante a fase de concepção 
    de um processo de desenvolvimento, a fim de identificar diferentes elementos 
    do sistema e as suas relações uns com os outros.

    /** 
    *   Os principais elementos em um DER são:
    *       • Entidade - uma classe de objetos do mundo real com características e
    *       propriedades comuns sobre as quais desejamos registrar informações.
    *       • Relacionamento - uma associação entre duas ou mais entidades.
    *       • Atributo - uma característica de uma entidade ou relacionamento.
    *
    *       No DER, as entidades são representadas por retângulos, os relacionamentos são
    *       representados por losangos e atributos por círculos.
    */  

    /**
    *   Entre as vantagens do modelo-ER, podemos destacar:
    *       • Excepcional simplicidade conceitual
    *       • Representação visual
    *       • Ferramenta de comunicação eficaz
    *       • Integrado com o modelo de banco de dados relacional
    *
    *   Em contrapartida, podemos destacar as seguintes desvantagens:
    *       • Representação limitada de restrições
    *       • Representação limitada de relacionamento
    */

### Entidades, Entidades Fortes e Fracas
    ->  Uma Entidade é um objeto de interesse para o usuário final e refere-se realmente
    ao conjunto de entidades e não a uma única entidade. Em outras palavras, entidade
    no MER corresponde a uma tabela.

    ->  Uma entidade pode ser uma pessoa, lugar, evento, objeto ou um conceito que é
    relevante para um determinado sistema para a qual estamos modelando o projeto
    de banco de dados. Por exemplo:
        • Pessoa: Estudante, Empregado, Cliente.
        • Lugar: Cidade, Sala, Armazém.
        • Evento: Festa, Casamento, Exposição, Feira.
        • Objeto: Carro, Navio, Máquina, Produto.
        • Conceito: Projeto, Conta, Curso.

    ->  Essas entidades são representadas no DER por um retângulo e nomeadas,
    usando substantivos singulares. Por exemplo, em um sistema escolar podemos ter
    as seguintes entidades:

    Aluno, Professor, Curso, Turma, Historico

    /**
    *   É importante entender a distinção entre entidade, uma instância de entidade
    *   e um conjunto de entidades. Uma entidade define uma coleção de entidades
    *   que possuem os mesmos atributos. Uma instância de entidade é um único item
    *   nesta coleção. Um conjunto de entidades é um conjunto de instâncias de entidade.
    *   Por exemplo: ALUNO é um tipo de entidade; um aluno com o número de RGM
    *   “151623” é uma instância de entidade; uma coleção de todos os alunos é um
    *   conjunto de entidades.
    *   Existem três tipos de entidades: Fortes; Fracas e Associativas.
    */

#### Entidade Forte
    -> Se uma entidade pode existir separadamente de todas as suas entidades
    relacionadas, então essa entidade é classificada como uma Entidade Forte. Como
    destaca Barbiere (1994), “além de independência de existência, normalmente
    possuem independência de identificação dada por um ou mais atributos próprios”.

    /**
    *   IMPORTANTE
    *   Segundo Barbiere (1994), as entidades fortes comumente são as primeiras a serem
    *   identificadas no processo inicial de análise do projeto de modelagem de dados.
    */

    -> Por exemplo, a entidade EMPREGADO é uma entidade forte, pois não depende
    de outra entidade para que exista uma instância.

            -> Nome_Empregado
EMPREGADO ->
            -> Id_Empregado

#### Entidade Fraca
    -> Uma entidade fraca é uma entidade que depende da existência de outra entidade.
    Em termos mais técnicos, ela pode ser definida como uma entidade que não pode
    ser identificada por seus próprios atributos. Uma entidade fraca é aquela que atende
    a duas condições:
        • A entidade fraca é dependente da existência de uma instância da entidade com
        a qual tem um relacionamento.
        • A entidade fraca tem uma chave primária que é parcial ou totalmente derivada
        da entidade-mãe no relacionamento.

    Por exemplo, temos a seguinte regra de negócio:
        • Todo dependente deve estar vinculado a um empregado.

    -> Nossa regra de negócio diz que um DEPENDENTE só pode existir/ser cadastrado
    se ele estiver vinculado a um EMPREGADO, ou seja, não podemos cadastrar um
    DEPENDENTE sem indicar à qual EMPREGADO esse dependente está vinculado.

#### Entidade Associativas
    -> Onde a entidade descreve uma conexão entre duas entidades com uma relação
    de muitos para muitos, por exemplo, atribuição de Empregado a Projeto (um
    Empregado pode ser atribuído a mais de um Projeto e um Projeto pode ser atribuído
    a mais de um Empregado).

    -> Se houver informações sobre o relacionamento, essas informações serão
    mantidas em uma entidade associativa, por exemplo, o número de horas em que
    o Empregado trabalhou em um Projeto específico é um atributo da relação entre
    Empregado e Projeto, não de Empregado ou de Projeto.

    -> Uma entidade associativa é identificada unicamente por concatenação das
    chaves primárias das duas entidades que ele conecta.