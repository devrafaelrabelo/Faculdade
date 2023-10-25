## Material Teórico
# Unidade 5 - Implementando o Modelo Telacional
    1. Normalização

## OBJETIVO DE APRENDIZADO
    -> Estudaremos os concetios de Normalização do modelo relacional, 
    suas regras de implantação e seus primcipais benefícios 

### Normalização
    -> A normalização é um processo para avaliar e corrigir estruturas de tabela para
    minimizar redundâncias de dados, reduzindo, assim, a probabilidade de anomalias
    de dados. O processo de normalização envolve a atribuição de atributos a tabelas
    com base no conceito de determinação.

    -> Normalização funciona através de uma série de estágios chamados Formas normais. Os 
    três primeiros estágios são descritos como primeira forma normal (1NF),segunda 
    forma normal (2NF) e terceira forma normal (3NF). Do ponto de vista estrutural, 
    podemos afirmar 2NF é melhor do que 1NF, e 3NF é melhor que 2NF.

    /**
    *   IMPORTANTE!
    *   Um problema óbvio com informações redundantes é que usamos mais memória do que
    *   é necessário. A redundância é um exemplo de uma anomalia que pode ocorrer em um
    *   SGBD do modelo relacional.
    */

#### A Necessidade de Normalização
    -> Existem duas situações comuns em que os projetistas de banco de dados usam
    a normalização:
        • Ao projetar uma nova estrutura de banco de dados com base nos requisitos
        de negócios dos usuários finais, o projetista de banco de dados construirá um
        modelo de dados usando o diagrama de entidade-relacionamento (DER). Após
        a conclusão do projeto inicial, o projetista pode usar a normalização para 
        analisar as relações que existem entre os atributos dentro de cada entidade, 
        para determinar se a estrutura pode ser melhorada através da normalização.

        • Alternativamente, os projetistas de banco de dados são frequentemente 
        solicitados a modificar estruturas de dados existentes que podem ser na forma 
        de arquivos simples, planilhas ou estruturas de banco de dados mais antigas. 
        Novamente, por meio de uma análise das relações entre os atributos ou campos
        na estrutura de dados, o projetista de banco de dados pode usar o processo
        de normalização para melhorar a estrutura de dados existente para criar um
        projeto de banco de dados apropriado

##### Anomalias
    -> Existem três tipos de anomalias que ocorrem quando o banco de dados não é
    normalizado. Estas são: 
        • Inserção;
        • Atualização; e
        • Anomalia de Exclusão

    001 -> Manhattan    ->  1   -> João da Silva    -> Programador Sênior   -> 40.00    -> 50
    -   ->              ->  2   -> Paulo Farias     -> Analista Sênior      -> 40.00    -> 30 
    -   ->              ->  3   -> Carlos Alberto   -> Programador Sênior   -> 40.00    -> 50 
    -   ->              ->  4   -> Maria Fernanda   -> Gerente              -> 80.00    -> 50        

    -> Os problemas com a tabela acima são:
        1. O número do projeto destina-se a ser uma chave primária, mas contém nulos.
        2. A tabela exibe redundâncias de dados.
        3. As entradas de tabela permitem inconsistências de dados.
        4. As redundâncias de dados produzem as seguintes anomalias:
            a) Anomalias de Inserção: Não podemos armazenar os detalhes do Empregado até que o Projeto seja atribuído.
            b) Anomalias de Atualização: Se o nome do projeto Manhattan precisar ser
            alterado, essa alteração deverá ser realizada em todos os quatro registros.
            c) Anomalias de Exclusão: Se excluirmos o empregado 1, também iremos
            perder as informações sobre o Projeto.

        Para superar essas anomalias, precisamos normalizar os dados. Nas próximas
        seções, iremos discutir sobre a normalização. 

    /**
    *   IMPORTANTE
    *   A chave primária de uma relação em um SGBD
    *   deve ser uma chave candidata, mas pode haver
    *   várias chaves candidatas para escolher. Quando
    *   se fala de normalização, é irrelevante qual chave
    *   é escolhida como chave primária    
    */

##### 1ª Forma Normal (1FN)
    -> Definimos que uma tabela está na primeira forma normal, se e somente se, todas
    as colunas possuem um único valor, e não existam grupos repetitivos (colunas) em
    uma linha ou atributos compostos. (MACHADO, 2014).

    -> Para que uma tabela possa estar na 1FN, devemos seguir as seguintes regras:
        1. Não devem existir colunas com dados repetidos ou similares;
        2. Cada item de dados deve ser atômico (não possuir valores compostos);
        3. Cada linha deve ser única, isto é, deve possuir uma chave primária;
        4. Cada campo deve ter um nome exclusivo.

    /**
    *   IMPORTANTE
    *   "Atômico" é o termo usado para descrever que é um item de dados é único
    *   e indivisível.
    */

    -> Exemplos de dados repetidos:

    Id_CLIENTE      | Nome_Cliente      | Telefone1     |  Telefone2    | Telefone3     |
    123             | João Silva        | 1234-2356     | 8945-5689     | 2563-8996     |

    -> Neste exemplo, o banco de dados está tentando armazenar números de telefones
    de contato para cada Cliente. O projetista criou três campos para manter números
    de telefone. Esse é um exemplo de “colunas com dados repetidos”. Os números de
    telefone são o mesmo tipo de dados.

    -> Exemplos de dados "não atômicos"

    Id_CLIENTE      | Nome_Cliente      | E-Mail                                |  
    123             | João Silva        | joao@gmail.com; joaosilva@gmail.com   |   

    -> Por mais que a tabela acima possua um campo de chave primária (Id_Cliente)
    e não existam dados repetidos, essa tabela não está na primeira forma normal
    (1FN) porque, como podemos notar, o cliente possui dois endereços de e-mail
    inseridos no campo “E-mail”. Desse modo, os dados inseridos neste campo não
    são atômicos.  

    -> Levando em consideração que existe a possibilidade de o cliente possuir mais
    que um (1) e-mail, a solução para esse cenário é criar uma nova entidade chamada
    E-mail e usar o campo chave (Id_Cliente) como chave estrangeira para fazer a
    ligação entre as duas entidades. Podemos observar o resultado nas tabelas abaixo.

    Id_CLIENTE      | Nome_Cliente      |  
    123             | João da Silva     |
    125             | José Ferreira     |

    Id_Email      | Id_CLIENT       | E-Mail                   |  
    1             | 123             | joao@gmail.com;          | 
    2             | 123             | joaosilva@gmail.com;     |
    3             | 125             | josefer@gmail.com;       |

    -> Com essa solução, não há problemas quanto a inserir mais que um (1) e-mail por
    cliente e confere a fácil extração de dados de e-mail, pois, além de existir apenas
    uma coluna para e-mail, todos os dados são atômicos.

    -> Podemos afirmar que essas tabelas estão na primeira forma normal (1NF), dado
    que obedecem às seguintes regras:
        • Cada tabela tem uma chave primária;
        • Cada nome de campo é exclusivo;
        • Os dados são atômicos;
        • Não possui campos repetidos / redundantes.

##### 2ª Forma Normal (2FN)
    -> Uma tabela está na segunda forma normal (2FN) se estiver na 1FN e não
    possuir campos que sejam funcionalmente dependentes de parte da chave primária
    (MACHADO, 2014).

    -> As regras para a segunda forma normal são:
        1. A tabela deve estar já na primeira forma normal (1FN);
        2. Todos os atributos não-chave devem depender da chave primária completa,
        ou seja, não contenham dependência parcial

    /**
    *   Importante
    *   Dependência parcial ocorre quando uma coluna depende apenas de parte de uma chave
    *   primária composta (HEUSER, 2010).
    */

    Vamos a um exemplo. Considere as seguintes tabelas

    Id_Projeto      | Nome_Projeto      |
    103             | Manhattan         |
    104             | Houston           |

    Id_Projeto      | Id_Empregado      | Nome_Empregado     | Cargo_Empregado    | Valor_Hora     | Horas_Trabalhadas|
    103             | 1                 | João da Silva      | Programador Junior | 30.00          | 50               |
    103             | 2                 | Maria Fernanda     | gerente            | 80.00          | 50               |
    104             | 1                 | João da Silva      | Programador Junior | 30.00          | 20               |
    104             | 3                 | Paulo Farias       | Analista Sênior    | 40.00          | 10               |
    104             | 4                 | Gustavo Fontes     | Analista Sênior    | 40.00          | 20               |
    
    -> No cenário acima, podemos perceber que a tabela Projeto está na segunda
    forma normal, pois todos os seus atributos dependem exclusivamente de sua chave
    primária. Contudo, a tabela Empregado não, posto que os atributos “Nome_Empregado”,
    “Cargo_Empregado” e “Valor_Hora” dependem somente do campo chave “Id_Empregado”. 
    São atributos que não estão ligados diretamente do campo chave “Id_Projeto”, ou 
    seja, são atributos que não dependem da entidade Projeto.Por outro lado, o 
    atributo “Horas_Trabalhadas” depende exclusivamente da chave composta da Tabela 
    (Id_Projeto e Id_Empregado). A informação guardada nesse atributo permite saber 
    quantas horas o empregado trabalhou no projeto específico.

    -> Para que a tabela Empregado passe para a segunda forma normal (2FN), devemos 
    dividir a tabela em duas novas tabelas, criando, assim, uma nova tabela chamada 
    Projeto_Horas_Trabalhadas. 
    Podemos conferir o resultado abaixo: 

    Id_Projeto      | Nome_Projeto      |
    103             | Manhattan         |
    104             | Houston           |

    Id_Projeto      | Id_Empregado      | Horas_Trabalhadas  |    
    103             | 1                 | 50                 |
    103             | 2                 | 50                 |
    104             | 1                 | 20                 |
    104             | 3                 | 10                 |

    -> Podemos afirmar que as tabelas acima estão na segunda forma normal (2FN)
    porque todas as tabelas estão na 1FN e, além disso, os atributos não-chave de todas
    as tabelas possuem dependência exclusiva da chave primária de suas respectivas
    tabelas (sendo essas chaves primárias compostas ou não).

##### 3ª Forma Normal (3FN)
    -> Uma tabela encontra-se na terceira forma normal quando, além de estar na
    2FN, não possua dependências transitivas.

    /**
    *   IMPORTANTE
    *   Dependência transitiva ocorre quando uma coluna, além de depender da chave primária
    *   da tabela, depende de outra coluna ou conjunto de colunas da tabela (HEUSER, 2010).
    */

    -> As regras para a terceira forma normal (3FN) são:
        1. A tabela deve estar já na primeira forma normal (1FN);
        2. Não existam atributos não-chave que dependam de outros atributos não-chave

    Id_Empregado    | Nome_Empregado      | Id_Cargo         |    
    1               | João da Silva       | 1                |
    2               | Maria Fernanda      | 2                |
    3               | Paulo Farias        | 3                |
    4               | Gustavo Fontes      | 3                |

    Id_Cargo        | Cargo_Empregado       | Valor_Hora       |    
    1               | Programador Junior    | 30.00            |
    2               | Gerente               | 80.00            |
    3               | Analista Sênior       | 40.00            |

    Id_Projeto      | Nome_Projeto      |
    103             | Manhattan         |
    104             | Houston           |

    Id_Projeto      | Id_Empregado      | Horas_Trabalhadas  |    
    103             | 1                 | 50                 |
    103             | 2                 | 50                 |
    104             | 1                 | 20                 |
    104             | 3                 | 10                 |

    -> Assim, podemos concluir que as tabelas acima estão na terceira forma normal
    (3FN), já que todas as tabelas estão na 2FN e, além disso, os atributos não-chave de
    todas as tabelas não possuem dependência transitiva de outros atributos não-chave
    em suas respectivas tabelas.

###### Forma Normal Boyce/Codd (FNBC) e 4ª e 5ª Forma Normal (4FN, 5FN)
    -> Para Heuser (2010), a decomposição das tabelas até 3FN é suficiente para obter
    o esquema de um banco de dados. Contudo, na literatura, nos deparamos com a
    forma normal Boyce/Codd (FNBC) e 4ª e 5ª Forma Normal (4FN, 5FN).
    
    -> Definimos que uma tabela está na forma normal Boyce/Codd (FNBC), se e
    somente se, cada determinante é uma chave candidata. A maioria das entidades
    em 3NF já estão em BCNF.

    -> A tabela está na quarta forma normal (4FN) se nenhuma instância da tabela
    do banco de dados contiver dois ou mais dados independentes e multivalorados
    descrevendo a entidade relevante, então ela estará na quarta forma normal.
    
    -> Uma tabela está na quinta forma normal (5FN) somente se estiver em 4NF e não
    puder ser decomposta em qualquer número de tabelas menores sem perda de dados.