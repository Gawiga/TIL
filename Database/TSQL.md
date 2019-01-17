# Sumário
- [Índice](#Índice)

## Índice(https://docs.microsoft.com/pt-br/sql/relational-databases/indexes/clustered-and-nonclustered-indexes-described?view=sql-server-2017)

Um índice é uma estrutura em disco associada a uma tabela, contém chaves que são armazenadas em uma estrutura para **localizar** as linhas associadas aos **valores chave de forma rápida e eficaz**.

Tanto os índices clusterizados quanto os não clusterizados podem ser exclusivos. Isso significa que duas linhas não podem ter o mesmo valor que a chave de índice. 

### Índice Clusterizado
Classificam e armazenam as linhas de dados com base em seus valores de chave. Pode haver **apenas um índice clusterizado por tabela**, pois as linhas de dados podem ser classificadas somente em **uma única ordem**. 

O único momento em que as linhas de dados de uma tabela **são armazenadas na ordem** de classificação é **quando contém um índice clusterizado**. 

Se a tabela contiver um índice clusterizado, será denominada tabela clusterizada. 
Se a tabela **não possuir nenhum índice clusterizado**, suas linhas de dados ficarão armazenadas em uma estrutura não ordenada denominada **heap**.

### Índice Não Clusterizado
Contém os valores de chave de índice não clusterizado e cada entrada de valor de chave tem um ponteiro para a linha de dados que contém o valor de chave.

O ponteiro de uma linha de índice em um índice não clusterizado de uma linha de dados é denominado **localizador de linhas**. 
A estrutura do localizador de linhas depende de as páginas de dados serem armazenadas em um heap ou em uma tabela clusterizada.

**Para o heap, o localizador de linhas é um ponteiro para a linha. Para a tabela clusterizada, o localizador de linhas é a chave de índice clusterizado.**

Você pode adicionar colunas não chave ao nível folha do índice não clusterizado para ignorar os limites de chave de índice existente e executar consultas completamente abrangidas e indexadas. 

### Mais sobre índices
Os índices **são criados automaticamente** quando as restrições *PRIMARY KEY* e *UNIQUE* são definidas em colunas de tabelas.

Índices bem projetados podem reduzir as operações de E/S de disco e consumir menos recursos de sistema, aprimorando o desempenho das consultas. Em geral, fazer pesquisas no índice é muito mais rápido do que na tabela, porque diferentemente da tabela, o índice contém, com frequência, poucas colunas por linha e as linhas ficam na ordem de classificação.

[Guia de Arquitetura e Design de Indexes](https://docs.microsoft.com/pt-br/sql/relational-databases/sql-server-index-design-guide)

# [Funções](https://docs.microsoft.com/pt-BR/sql/t-sql/functions/functions?view=sql-server-2017)
- Funções podem ser [determínisticas ou não determinísticas](https://docs.microsoft.com/pt-BR/sql/relational-databases/user-defined-functions/deterministic-and-nondeterministic-functions?view=sql-server-2017)

## [Funções de agregação](https://docs.microsoft.com/pt-BR/sql/t-sql/functions/aggregate-functions-transact-sql?view=sql-server-2017)
- EXECUTAM 1 cálculo em 1 CONJUNTO de valores e RETORNAM 1 único valor.
- Com exceção de **COUNT()** essas funções ignoram valores NULOS
- São usadas em cláusulas SELECT com um GROUP BY e HAVING
- Todas as funções de agregação são **deterministícas**

ex: **AVG()** | **COUNT()** | **MAX()** | **SUM()** | **MIN()**

## [Funções matemáticas](https://docs.microsoft.com/pt-br/sql/t-sql/functions/mathematical-functions-transact-sql)
- Executam um cálculo e retornam um valor númerico

ex: **CEILING()** | **ROUND()** | **SIN()** | **TAN()** | **RAND()**


# [ELEMENTOS DA LINGUAGEM](https://docs.microsoft.com/pt-br/sql/t-sql/language-elements/language-elements-transact-sql)

## [CURSORES](https://docs.microsoft.com/pt-br/sql/t-sql/language-elements/cursors-transact-sql)
FETCH
- Pega um número de linhas
- Tem que ter o order by e o offset
ex: `fetch 10 rows only`;

# [CONSULTAS](https://docs.microsoft.com/pt-br/sql/t-sql/queries/queries?view=sql-server-2017)

## [TOP](https://docs.microsoft.com/pt-br/sql/t-sql/queries/top-transact-sql?view=sql-server-2017)
- TOP WITH TIES: traz os resultados do TOP que são iguais
:ex TOP 1 -> 1 registro 
WITH TIES -> n registros com valor igual

## [OVER](https://docs.microsoft.com/pt-br/sql/t-sql/queries/select-over-clause-transact-sql?view=sql-server-2017)
Determina o particionamento e ordenação de um conjuntos de linahs antes da aplicação de uma função de janela associada.

### Argumentos
- PARTITION BY: Divide o conjunto de resultados da consulta em partições. 
- UNBOUNDED PRECEDING: 

------------------------

## Artigos em Português


## Artigos em Inglês

- [Blog do Sommarskog](http://www.sommarskog.se/)