## Material Teórico
# Unidade 4 - Modelo ER - Part 2
    1. Introdução
    2. Relacionamento
    3. Atributo
    4. Notação Graficas ER

## OBJETIVO DE APRENZIDADO
    -> Apresentar os conceitos de relacionamento, atributos 
    e as notações gráficas para representação do MER

### Introdução
    -> Nessa unidade daremos sequencia ao estudo do modelo entidade-relacionamento
    (Modelo-ER), estudaremos os conceitos e características de relacionamentos,
    atributos e um pouco mais sobre a notação gráfica criada por Peter Chen na
    década de 1970. 

### Relacionamento
    -> Um relacionamento descreve uma associação entre entidades. Isto é, um
    relacionamento representa a quantidade de instâncias de uma entidade em relação
    à outra entidade. Por exemplo, existe uma relação entre clientes e vendedores que
    pode ser descrita da seguinte forma: um vendedor pode atender muitos clientes e
    cada cliente pode ser atendido por um vendedor.

        /**
        *   TROCANDO IDEIAS
        *   Relacionamento é um conjunto de associações entre ocorrências de entidades
        *   (HEUSER, 2010).
        */

    -> Antes devemos saber quais tipos de relações podem existir entre um determinado
    par de entidades. Saber identificá-los adequadamente é uma habilidade inestimável
    para projetar um banco de dados com êxito.    

    -> Para entender como representar um relacionamento em um modelo entidaderelacionado, 
    serão apresentados os conceitos de Grau de relacionamento (unário, binário e ternário) 
    e Cardinalidade (Máxima e Mínima).

#### Grau de Relacionamento 
    -> O número de conjuntos de entidades que participam de um relacionamento
    é chamado de grau de relacionamento. Os três graus mais comuns de um
    relacionamento em um banco de dados são: unário, binário e ternário.

        • Relação Unária: Uma relação unária R é uma associação entre duas instâncias do 
        mesmo tipo de entidade (isto é, R ∈ E1 × E1). Por exemplo, todo empregado em uma 
        determinada empresa possui um supervisor, e todo supervisor é um empregado.

        • Relação binária: Uma relação binária R é uma associação entre duas instâncias
        de dois tipos de entidade diferentes (isto é, R ∈ E1 × E2). Por exemplo, numa
        loja, existe uma relação binária entre um vendedor (entidade VENDEDOR) e
        um cliente (entidade CLIENTE): 
            ->Um vendedor atende um cliente.

        • Relação Ternária: Uma relação ternária R é uma associação entre três
        instâncias de três diferentes tipos de entidade (isto é, R ∈ E1 × E2 × E3). 
        Por exemplo, considere um professor que leciona diversas disciplinas em 
        diversas turmas em uma Universidade. Neste caso, os tipos de entidade PROFESSOR,
        TURMA e DISCIPLINA se relacionam entre si com relacionamentos ternários:
            -> Um professor leciona uma disciplina em uma turma.

#### Cardinalidade
    -> Quando dizemos cardinalidade de um relacionamento, queremos dizer a
    capacidade de contar o número de entidades envolvidas nesse relacionamento.
    Por exemplo, se instâncias das entidades A e B estiverem conectadas por uma
    relação, então a cardinalidade máxima representa o número máximo de instâncias
    da entidade B que podem ser associadas a qualquer instância da entidade A.

    -> Não é necessário atribuir um valor de número para cada nível de
    conexão em um relacionamento. Na verdade, o termo cardinalidade máxima 
    referese a apenas dois valores possíveis: um (1) ou muitos (N).

    -> Embora isso possa parecer muito simples o valor máximo de cardinalidade de
    uma relação, nos permite definir os três tipos de relações possíveis entre os tipos de
    entidade A e B: um-para-muitos (1:N), muitos-para-muitos (N:M) e um-para-um (1:1).

    /**
    *   TROCANDO IDEIAS
    *   Cardinalidade é uma propriedade que especifica a quantidade de ocorrências associadas
    *   entre duas entidades dentro de uma relação.
    */

##### Relação UM-PARA-MUITOS (1:N)
    -> Uma relação 1:N descreve que uma instância do conjunto A se relaciona com
    diversas instâncias do conjunto B; e uma instância do conjunto B se relacionado
    com apenas uma instância do conjunto A.

    Inst1 -> Inst1, Inst2, Inst3
    Inst2 -> Inst4
    Inst3 -> Inst5, Inst6
    Inst4 -> Inst7

    PESSOA -> CARRO

    PESSOA¹ -> (POSSUI) -> n^CARROS
    CLIENTE¹ -> (POSSUI) -> n^PEDIDOS

    -> Lemos esse diagrama como: “Um cliente pode possuir vários pedidos e um
    pedido pertence a um cliente”.

##### Relação MUITOS-PARA-MUITOS (N:M) 
    -> Uma relação N:M descreve que uma instância do conjunto A se relaciona com
    diversas instâncias do conjunto B; e uma instância do conjunto B se relaciona com
    diversas instâncias do conjunto A.


    Inst1 -> Inst1, Inst2, Inst3
    Inst2 -> Inst3, Inst4, Inst5
    Inst3 -> Inst2, Inst5, Inst6, Inst7
    Inst4 -> Inst5, Inst7

    AUTOR -> LIVRO

    AUTOR^n -> (ESCREVE) -> m^LIVRO
    EMPREGADO^n -> (TRABALHA) -> m^PROJETOS

    -> Lemos esse diagrama como “Um empregado pode trabalhar em vários projetos
    e um projeto pode alocar vários empregados”.    

##### Relação UM-PARA-UM (1:1)
    -> Uma relação 1:1 descreve que uma instância do conjunto A se relaciona com
    apenas com uma instância do conjunto B; e uma instância do conjunto B se
    relaciona apenas com uma instância do conjunto A.

    Inst1 -> Inst2
    Inst2 -> Inst3
    Inst3 -> Inst4
    Inst4 -> Inst1

    CLIENTE¹ - (POSSUI) -> ¹LOGIN
    EMPREGADO¹ -> (GERENCIA) -> ¹DPARTAMENTO
    
    -> Podemos ler esse diagrama como: “Empregado gerência um departamento e
    um departamento é gerenciado por um empregado”.

#### Cardinalidade Mínima
    -> O termo cardinalidade mínima refere-se ao número mínimo de instâncias de uma
    entidade que deve estar associada a uma única instância de uma entidade relacionada.
    Utilizamos a representação de cardinalidade mínima para expressar as restrições
    mínimas de uma ocorrência em uma dada entidade. Ou seja, as cardinalidades
    mínimas irão representar a obrigatoriedade ou não de uma ocorrência em uma
    entidade. As cardinalidades mínimas possuem os seguintes valores possíveis: 0 e 1.
   
##### Cardinalidade mínima um (0)
    -> Considere a seguinte regra de negócio:
        • Um cliente pode possuir diversos pedidos, contudo, todo pedido deve
        pertencer à somente um cliente.
    
    -> Nesse cenário, sabemos que esse tipo de relacionamento é do tipo “um-paramuitos”, 
    ou seja, 1:N, porque um (1) cliente pode possuir diversos (N) pedidos. Já
    temos a informação da cardinalidade máxima de cada entidade. Agora para obter
    as informações a respeito das cardinalidades mínimas de cada entidade, devemos
    nos atentar à regra de negócio e identificar às palavras que denotam restrições, que
    nesse caso são: “... pode possuir...” e “... deve... somente um cliente.”. Essa
    análise resulta em: 
        • O cliente pode ou não possuir um pedido (mínimo 0), mas todo pedido deve
        pertencer a um cliente (mínimo 1).
    
    CLIENTE(¹,¹) -> (POSSUI) -> (0,N)^PEDIDO

    -> Mais uma vez é preciso lembrar que as cardinalidades máximas e mínimas de
    uma entidade em relação à outra, são representadas no lado oposto à da entidade.
    Lemos esse diagrama do seguinte modo:
        • Um cliente pode possuir no mínimo zero (0) e no máximo diversos pedidos (N).
        • Um pedido deve pertencer à no mínimo um (1) cliente e no máximo a um
        (1) cliente

    /**
    * TROCANDO IDEIAS
    * O grau da cardinalidade de uma entidade é sempre representado ao lado oposto
    * da entidade. 
    */

##### Cardinalidade mínima um (1)
    -> Considere a seguinte regra de negócio:
        • Todo cliente deve possuir um login e um login deve pertencer à somente
        um cliente

    -> Sabemos que a cardinalidade (máxima) dessa relação é um-para-um. Contudo,
    quais são as cardinalidades mínimas? As cardinalidades representam as restrições
    mínimas de uma ocorrência, então, nesse caso, ao ler a sentença do cenário, 
    podemos perceber que existem restrições mínimas para a ocorrência de LOGIN e
    USUÁRIO (deve possuir um login... deve pertencer à somente um...). Nesse caso,
    as cardinalidades representadas são 1:1 e 1:1.

    CLIENTE(¹,¹) -> (POSSUI) -> (¹,¹)^LOGIN

    -> As cardinalidades máximas e mínimas de uma entidade em relação à outra, são
    representadas no lado oposto a da entidade. 
    Lemos esse diagrama do seguinte modo:
        • Um cliente possui no mínimo um (1) login e no máximo um (1) login.
        • Um Login pertence à no mínimo um (1) usuário e no máximo à um (1) usuário.

### Atributo 
    -> Um atributo é uma propriedade ou característica de uma entidade, ou uma
    relação. Por exemplo, o atributo Nome na ficha de um aluno é um atributo da
    entidade ALUNO. Uma entidade pode ter tantos atributos quanto necessário. Em
    um Diagrama de entidade-relacionamento (DER), representamos um atributo por
    meio de uma elipse ou um circulo. No diagrama abaixo, temos um exemplo de
    representação de atributos.

    ENTIDADE    -> Atributo 1
                -> Atributo 2
                -> Atributo 4
                -> Atributo 2
    
    -> Segundo Machado (2014), podemos classificar os atributos em dois tipos:
    Descritores e Identificadores.

#### Atributo Descritores 
    -> Todo e qualquer atributo que seja capaz de identificar e representar uma 
    característica de um objeto. Para Cougo (1997), todo atributo pode ser 
    considerado um atributo descritivo, o que faz o atributo ser classificado 
    com outro tipo é a presença de características funcionais adicionais, 
    por exemplo, um atributo identificador.

#### Atributo Identificadores 
    -> Um identificador (ou atributo-chave) é um único atributo ou uma combinação
    de atributos que identificam de forma única uma instância individual de um tipo de
    entidade. Por exemplo, na entidade ALUNO temos o atributo RGM como atributo
    identificador (ou atributo-chave), pois esse atributo, o RGM é único para cada Aluno
    (instância). No DER abaixo, vemos a representação desse cenário.

    ALUNO   -> NrCelular
            -> Endereço
            -> Nome
            -> *RGM

    -> O atributo Nome, por exemplo, não pode ser um identificador porque dois
    alunos podem ter o mesmo nome.

    -> Considere as entidades EMPREGADO e DEPENDENTE, onde um empregado
    pode possuir vários dependentes e um dependente deve pertencer à apenas um e
    no máximo um empregado. Nesse cenário, para identificar uma ocorrência única
    da entidade DEPENDENTE, utilizamos um atributo composto, formado por um
    atributo-chave de cada uma das entidades. O DER abaixo apresenta esse quadro.

    EMPREGADO(¹,¹) -> Nome           -> (POSSUI) -> DEPEDENTE -> Idade
              -> *Id_Empregado                                -> Nome
                                                              -> *Id_Empregado
                                                              -> *Id_Departamento

    -> Utilizamos os atributos “Id_Departamento” e “Id_Empregado” para formar a
    chave composta da entidade DEPENDENTE.  

    /**
    *   Ainda sobre o exemplo do relacionamento Empregado x Dependente. O atributo composto
    *   servirá para tornar mais rápida e eficiente a busca de informações referentes à entidade Forte,
    *   que nesse contexto é a entidade EMPREGADO. Em uma futura pesquisa no banco de dados,
    *   podemos nos deparar com a necessidade em se buscar informações do Empregado, contudo,
    *   temos inicialmente apenas informações do Dependente, e por meio da chave composta,
    *   podemos identificar o Empregado e diante disso, todas as outras informações necessárias.  
    */

### Notação Gráficas ER
    -> As notações gráficas para se desenvolver um Diagrama de entidaderelacionamento mais 
    comumente utilizadas são as notações criadas por Peter Chen (1990). A seguir, apresentamos 
    os principais símbolos utilizados em um DER.

    ° Retangulo Limpo -> Entidade
    ° Oval Atributo Limpo -> Descrito
    ° Bolinha Limpo -> Descrito
    ° Oval Atributo Limpo -> Identificador
    ° Bolinha Preenchida -> Identificador
    º Losango -> Relacionamento