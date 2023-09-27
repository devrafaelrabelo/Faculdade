# UNIDADE 2  - Etapas de um projeto de Banco de Dados
    1. Introdução à Modelagem de Dados
    2. Levantamento de Requisitos e Regras de Negócios
    3. Níveis de Modelagem: Modelos Conceitual, Lógico e Físico
    
## OBEJTIVO 
    -> Apresetar o conceito de modelagem de dados e seus níveis de 
    abstração, bem como a importância do levantamento de requisitos 
    e regras de negócio para o processo de desenvolvimento do
    projeto de bancos de dados.


### 1. Introdução à Modelagem de Dados
    -> Modelagem de dados é um passo essencial no processo de  
    criação de qualquer software complexo.  No centro da modelagem de 
    banco de dados está a ideia de projetar uma estrutura de banco 
    de dados que define como as informações armazenadas podem ser 
    acessadas, categorizadas e manipuladas e, em última análise, 
    qual história essa informação dirá.

    As técnicas e ferramentas de modelagem de dados capturam e 
    traduzem projetos de sistemas em representações de fácil 
    compreensão dos fluxos e processos de dados.

    As escolhas de modelagem de dados precisarão ser feitas no 
    início de qualquer implantação de software e terão grande 
    impacto no sucesso geral do projeto.

    /**
    *   A modelagem de dados tem como objetivos:
    *       • Identificar os diferentes componentes de dados - considerar dados brutos e
    *       processados, bem como entidades.
    *       • Identificar as relações entre os diferentes componentes de dados (estes são
    *       chamados associações).
    *       • Identificar os usos antecipados dos dados (chamados requisitos), com o
    *       reconhecimento de que os dados podem ser mais valiosos no futuro para usos
    *       não previstos.
    *       • Identificar os pontos fortes e restrições da tecnologia (hardware e software) 
    *       que você planeja usar durante o projeto.
    *       • Construir um modelo preliminar das entidades e suas relações, tentando
    *       manter o modelo independente de quaisquer usos específicos ou restrições
    *       de tecnologia
    */

    -> O modelo de dados é quivalente aos planos de construção de um arquiteto

#### Modelo de Dados
    -> Um modelo de dados é uma representação simplificada de como os dados se 
    relacionam e se transformam em um sistema. Ele é crucial na modelagem de 
    sistemas, permitindo que sejam visualizados e validados antes da programação.
    O analista de dados, como um arquiteto de casas, precisa coletar e entender 
    os dados do mundo real para criar um modelo. O modelo de dados guia o 
    comportamento dos dados no sistema, sendo um ponto-chave no processo de modelagem.

    /**
    *   Em Síntese
    *   É nesse momento em que o analista responsável pelo planejamento
    *   do banco de dados valida junto ao seu cliente o que ele observou
    * e se o que foi observado condiz com a realidade
    */

    Vamos a um exemplo prático. Imagine que temos a tarefa de planejar um modelo 
    de banco de dados para um cliente que possui uma loja de Petshop. Para
    o contexto desse nosso primeiro exemplo, em nossa primeira entrevista com o
    cliente, temos que investigar e analisar como o negócio de nosso cliente funciona
    em nível estrutural, ou seja, quais são os departamentos, suas relações e funções.
    
    -> Cliente: Minha loja possui dois setores. Um setor é a loja, onde vendo diversos
    produtos para animais. No outro setor, eu ofereço os serviços de Veterinário,
    banho e tosa.

                             PETSHOP
                        |               |                       
                        |               |
                        |               |                                                
                       LOJA       Banho e Tosa
                                        &
                                   Veterinário


### 2. Levantamento de Requisitos e Regras de Negócios

#### Levantamento de Requisitos
    -> O objetivo do levantamento de requisitos é identificar a situação do mundo
    real em detalhes suficientes para ser capaz de definir componentes de banco de
    dados, coletando principalmente dois tipos de dados: dados naturais (entrada para
    o banco de dados) e processamento de dados (saída do banco de dados).

    /**
    *   O analista responsável deve buscar basicamente o seguinte:
    *       • Delinear os requisitos de dados da empresa em termos de elementos de dados básicos.
    *       • Descrever as informações sobre os elementos de dados e as relações entre eles
    *       necessários para modelar esses requisitos de dados
    *       • Determinar os tipos de transações que se pretende executar no banco de
    *       dados e a interação entre as transações e os elementos de dados
    *       • Definir quaisquer restrições de desempenho, integridade, segurança ou
    *       administrativas que devem ser impostas ao banco de dados resultante.
    *       • Especificar quaisquer restrições de projeto e de implementação, como 
    *       tecnologias específicas, hardware e software, linguagens de programação, 
    *       políticas, padrões ou interfaces externas
    */

    -> Essas informações podem ser reunidas de várias maneiras:
        • Revisão de documentos existentes: tais documentos incluem formulários
        e relatórios existentes, diretrizes escritas, descrições de cargos, narrativas
        pessoais e memorandos. A documentação em papel é uma boa maneira de
        se familiarizar com a organização ou atividade que você precisa para modelar.
        • Entrevistas com usuários finais: podem ser uma combinação de reuniões
        individuais ou em grupo. Tente manter as sessões com grupos de até seis pessoas. 
        Se possível, com pessoas que tenham/pertençam à mesma função ou cargo em uma reunião.
        • Revisão de sistemas automatizados existentes: se a organização já possui
        um sistema automatizado, revise as especificações de projeto do sistema e a
        documentação.

    -> A análise e o levantamento de requisitos geralmente é feita ao mesmo tempo
    que a modelagem de dados. Se o modelo não estiver correto, ele é modificado, o que
    às vezes requer informações adicionais a serem coletadas. O ciclo de revisão e
    edição continua até que o modelo seja certificado como correto.

    Na dinâmica do levantamento e análise de requisitos, temos que ter em mente
    três pontos

    1. Converse com os usuários finais sobre seus dados em termos de “mundo real”.
    Os usuários não pensam em termos de entidades, atributos e relacionamentos,
    mas sobre as pessoas, coisas e atividades reais que lidam diariamente.

    2. Aproveite o tempo para aprender o básico sobre a organização e as atividades
    que você deseja modelar. Ter um entendimento sobre os processos tornará
    mais fácil a construção do modelo.

    3. Os usuários finais normalmente pensam e visualizam dados de diferentes
    maneiras de acordo com sua função ou cargo dentro de uma organização. Portanto, 
    é importante entrevistar o maior número de pessoas que o tempo permite.


    /**
    *   É válido ressaltar que o levantamento de requisitos aborda somente a identificação
    *   dos objetos (entidades, atributos ou relacionamentos), o que o sistema deve fazer.
    *   Como e quando os dados serão armazenados está a sob a responsabilidade da
    *   identificação das regras de negócios.
    */

#### Regras de Negócios
    -> Uma regra de negócios é independente do paradigma de modelagem, software
    ou hardware. Uma regra de negócios é uma declaração que define ou restringe
    alguns aspectos do negócio.

    Regras de Negócios dão a classificação adequada de entidades, atributos, relações
    e restrições. Fontes de regras de negócios são gerentes, gerentes de departamento,
    documentação escrita, procedimentos, padrões, manuais de operação e entrevistas
    com usuários finais.
        
    /**
    *   Alguns exemplos de regras de negócio:
    *   • Todo cliente deve estar cadastrado em nosso sistema.
    *   • O CPF e e-mail devem ser campos obrigatórios no cadastro do cliente.
    *   • Toda venda deve gerar um cupom fiscal.
    *   • O campo CPF é obrigatório para a geração do cupom fiscal.
    *   • Uma venda deve ser realizada somente por funcionários do departamento de
    *   frente de caixa.
    */

    /**
    *   Regras de negócios faz referência a como o processo é executado e suas restrições.
    *   Regras de negócios são independentes de sistemas informatizados, elas pertencem ao negócio.
    */
    
    -> É preciso ter em mente que se as regras de negócios estiverem incorretas, o
    modelo de dados será incorreto e, em última instância, o sistema que irá consumir
    no banco de dados não funcionará como esperado pelos usuários.

### 3. Níveis de Modelagem: Modelos Conceitual, Lógico e Físico
    -> O processo de modelagem de dados começa com uma visão abstrata do ambiente
    geral de dados (Modelo conceitual) e ganha detalhes (Modelos lógico e Físico) à
    medida que o projeto se aproxima da implementação do banco de dados.

#### Modelo Conceitual
    -> Um modelo de dados conceitual identifica as relações de nível mais alto entre as
    diferentes entidades.

    /**
    *   Características do modelo de dados conceitual incluem:
    *       • Entidades importantes e as relações entre elas.
    *       • Nenhum atributo é especificado.
    *       • Nenhuma chave primária é especificada.

#### Modelo Lógico
    -> Um modelo de dados lógico descreve os dados com o máximo de detalhes
    possível, independentemente do modo como será a implementação física no banco
    de dados. As características do modelo de dados lógico incluem:

    /**
    *   Todas as entidades e relações entre elas.
    *       • Todos os atributos para cada entidade especificados.
    *       • A chave primária para cada entidade especificada.
    *       • Especificadas as chaves estrangeiras (chaves que identificam a relação entre
    *       diferentes entidades).
    *       • A normalização ocorre neste nível.
    *
    *   As etapas para projetar o modelo de dados lógico são as seguintes:
    *       1. Especifique chaves primárias para todas as entidades.
    *       2. Encontre as relações entre entidades diferentes.
    *       3. Encontre todos os atributos para cada entidade.
    *       4. Resolva relacionamentos muitos-para-muitos.
    *       5. Normalização
    */

    -> Comparando o modelo de dados lógico, mostrado acima, com o diagrama do
    modelo de dados conceitual, vemos as principais diferenças entre os dois:
        • Em um modelo de dados lógico, chaves primárias estão presentes, enquanto
        que em um modelo de dados conceitual, nenhuma chave primária está presente.
        • Em um modelo de dados lógico, todos os atributos são especificados dentro
        de uma entidade. Nenhum dos atributos são especificados em um modelo
        conceitual de dados.
        • As relações entre entidades são especificadas usando chaves primárias e 
        chaves estrangeiras em um modelo de dados lógico. Em um modelo de dados
        conceitual, os relacionamentos são simplesmente declarados, não especificados, 
        simplesmente sabemos que duas entidades estão relacionadas, mas não
        especificamos quais atributos são usados para essa relação.

#### Modelo Físico
    -> O modelo de dados físico representa como o modelo será construído no banco
    de dados. Um modelo de banco de dados físico mostra todas as estruturas de
    tabela, incluindo nome da coluna, tipo de dados da coluna, restrições de coluna,
    chave primária, chave externa e relações entre tabelas. Os recursos de um modelo
    de dados físicos incluem:

    /**
    *  • Especificar todas as tabelas e colunas.
    *       • Chaves estrangeiras são usadas para identificar relações entre tabelas.
    *       • Considerações físicas podem fazer com que o modelo de dados físico seja
    *       bastante diferente do modelo de dados lógicos.
    *       • O modelo de dados físico será diferente para diferentes SGDBs. Por exemplo,
    *       o tipo de dados para uma coluna pode ser diferente entre o MySQL, ORACLE,
    *       FIREBIRD e o SQL Server.
    */

    /**
    *   As etapas para projetar o modelo de dados físico são as seguintes:
    *       1. Converter entidades em tabelas.
    *       2. Converter relações em chaves estrangeiras.
    *       3. Converter atributos em colunas.
    *       4. Modificar o modelo de dados físicos com base em restrições/requisitos físicos.
    */

    • Os nomes das entidades são agora nomes de tabelas.
    • Os atributos são agora nomes de colunas.
    • O tipo de dados para cada coluna é especificado. Tipos de dados 
    podem ser diferentes dependendo do banco de dados real sendo usado.
