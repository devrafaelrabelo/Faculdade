Orientação / Dicas

https://view.genial.ly/61a13c4dcbd5940d7a611df0

# UNIDADE 1  - Banco de Dados
    1. Evalução Historia de Banco de Dados
    2. O que é um Banco de Dados
    3. O que é um Sistema Gerenciador de Banco de Dados
    4. A importância dos Bancos de Dados
    
## OBEJTIVO 
    -> Apresentar o histórico e a evolução dos bancos de dados, 
    suas utilizações, modelos e os principais bancos de dados 
    em uso no mercado

/** Banco mais usados no mundo são
*
*   1 - Microsoft SQL Server
*   2 - Oracle
*   3 - IBM DB2 LUW
*   4 - Mongo DB
*
*/

SGBD -> É o nome dado aos softwares que gerenciam banco de dados, e 
        não o tipo do banco de dados

## Modelos de SGBD

### Hierárquico (SGBD) ->  
    Representada por uma árvore de cabeça para baixo
    Relação de (1:M) -> 1 PAI pode ter varios FILHOS 
    mas 1 FILHO pode ter somente 1 PAI

/**
*   O editor de registro do Windows (figura 1) é um exemplo de um banco 
*   e dados hierárquico.
*/

Vantagens 
    Simplicidade Conceitual
    Segurança de banco de dados
    Independência dos dados
    Integridade do banco de dados
    Eficiência em lidar com uma grande base de dados
    
Desvantagens
    Implementação Complexa
    Dificil gerenciamento
    Falta de independência estrutural
    Limitação de Implementação
    Falta de normas e padrões bem definidos 

/**
*   Exemplos de SGBD Hierárquico incluem 
*   s Information Management System (IMS)
*   SYSTEM 2000
*/


### Rede (SGBD) ->
    Organiza os dados em uma estrutura de rede, geralmente resulta em complexas 
    estruturas de banco de dados, O registro FILHO pode ter diversos PAIS
    pois em uma rede os nós podem ter tantas conexões quanto possivel

Vantagens
    Simplicidade conceitual
    Permite gerenciar uma grande quantidade de relações
    Possibilita a flexibilidade de acesso a dados
    Promove a integridade do banco de dados
    Favorece a independência dos dados
    Possui normas e padrões bem definidos

Desvantagens
    Complexidade do sistema
    Falta de independência estrutural

/**
*   O RDM Server, IDMS e TOTAL são exemplos de sistemas de gerenciamento
*   de banco de dados que implementam o modelo de rede.
*/

### Relacional (SGBD-R) ->
    Ao contrário do SGBD de rede, o tipo relacional
    não suporta relacionamentos do tipo muitos para 
    muitos, base do modelo relacional é um conceito 
    matemático conhecido como relação. O modelo de dados 
    relacional executa as mesmas funções básicas fornecidas 
    pelos SGBDs dos tipos hierárquico e de rede, além de 
    uma série de outras funções que tornam o modelo de dados 
    relacional mais fácil de entender e implementar

/**
*    Outra grande vantagem é a sua linguagem de consulta poderosa e flexível, o
*    Structured Query Language (SQL), que permite ao usuário especificar o que deve
*    ser feito sem especificar como deve ser feito. O SGBD-R usa o SQL para traduzir
*    consultas de usuários em instruções para recuperar os dados solicitados. O SQL
*    torna possível recuperar dados com muito menos esforço do que qualquer outro
*    banco de dados ou ambiente de arquivos. 
*/

Vantagens
    A independência estrutural
    Melhor simplicidade conceitual
    Projeto, implementação, gerenciamento e uso mais simples de banco de dados
    Sistema de gerenciamento de banco de dados poderoso

Desvantagens
    Sobrecarga substancial de hardware e software de sistema
    Possibilidade de má concepção e implementação

/**    
*   Exemplos de sistemas de gerenciamento de banco de dados relacional incluem
*   banco de dados MySQL, Oracle e Microsoft SQL Server.
*/

### Orientado a Objetos (SGBD-OO) ->
    No SGBD orientado a objetos (SGBD-OO), tanto os dados como suas relações
    estão contidos em uma única estrutura conhecida como objeto. Este modelo de
    dados é outro método de representar objetos do mundo real. Considera cada objeto
    no mundo como objetos e os isola uns dos outros.

#### O SGBD-OO baseia-se nos seguintes componentes:

/**
*    • Um objeto é uma abstração de uma entidade do mundo real. Em termos
*    gerais, um objeto pode ser considerado equivalente a uma tabela do SGBDRelacional. 
*    Mais precisamente, um objeto representa apenas uma ocorrência
*    de uma entidade.
*
*    • Atributos descrevem as propriedades de um objeto. Por exemplo, um objeto
*    PESSOA inclui os atributos Nome, Número de Segurança Social e Data de
*    Nascimento.
*
*    • Objetos que compartilham características semelhantes são agrupados em
*    classes. Uma classe é uma coleção de objetos semelhantes com estrutura
*    compartilhada (atributos) e comportamento (métodos). O método de uma classe
*    representa uma ação no mundo real, como encontrar o nome de uma pessoa
*    selecionada, alterar o nome de uma pessoa ou imprimir o endereço de uma
*    pessoa. Em outras palavras, os métodos são o equivalente a procedimentos
*    em linguagens de programação tradicionais. Em termos orientado a objetos,
*    os métodos definem o comportamento de um objeto.
*
*    • As classes são organizadas em uma hierarquia de classes. A hierarquia de
*    classe se assemelha a uma árvore invertida na qual cada classe tem apenas um
*    pai. Por exemplo, a classe CLIENTE e a classe EMPREGADO compartilham
*    uma classe pai PESSOA, o que chamamos de herança.
*
*    • A herança é a capacidade de um objeto dentro da hierarquia de classe herdar
*    os atributos e métodos das classes acima dele. Por exemplo, duas classes,    
*    UNIDADE Banco de Dados CLIENTE e EMPREGADO, podem ser criadas como 
*    subclasses da classe PESSOA. Nesse caso, CLIENTE e EMPREGADO herdarão 
*    todos os atributos e métodos de PESSOA.
*/

Vantagens
    Apresentação visual inclui conteúdo significativo
    Alta integridade do banco de dados
    Independência estrutural e de dados

Desvantagens
    Falta de normas e padrões bem definidos
    Acesso complexo aos dados de navegação
    Curva de aprendizagem íngreme

/**
*   Exemplos de sistemas de gerenciamento de banco de dados orientados a
*   objetos incluem os bancos de dados CACHÉ, DB4Objects, VERSANT, JASMIN
*   e MATISSE.
*/