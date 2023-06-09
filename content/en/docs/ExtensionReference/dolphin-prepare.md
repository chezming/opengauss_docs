# PREPARE<a name="ZH-CN_TOPIC_0289900448"></a>

## Function<a name="en-us_topic_0283137542_en-us_topic_0237122167_en-us_topic_0059778902_s86b6c9741c7741d3976c5e358e8d5486"></a>

**PREPARE** creates a prepared statement.

A prepared statement is a performance optimizing object on the server. **PREPARE** is executed to parse, analyze, and rewrite the specified query. **EXECUTE** is executed to plan and execute the prepared statement. This avoids repetitive parsing and analysis. After the PREPARE statement is created, it exists throughout the database session. Once it is created (even if in a transaction block), it will not be deleted when a transaction is rolled back. It can only be deleted by explicitly invoking DEALLOCATE or automatically deleted when the session ends.

## Precautions<a name="en-us_topic_0283137542_en-us_topic_0237122167_en-us_topic_0059778902_sdd2da7fe44624eb99ee77013ff96c6bd"></a>
Compared with the original openGauss, Dolphin modifies the PREPARE syntax as follows:

1. The PREPARE FROM syntax is supported.

2. A statement can be enclosed in single quotation marks, and the statement in the single quotation marks must be a single query. In scenarios where single quotation marks are added, in addition to SELECT, INSERT, UPDATE, DELETE, MERGE INTO, and VALUES statements, other statements that will be converted to SelectStmt are supported, for example, some SHOW statements.

3. The question mark (`?`) can be used as a binding parameter in a statement. You need to set `b_compatibility_mode` to `on` first, and `$` and `?` cannot be used as parameter placeholders in the same statement at the same time. After `b_compatibility_mode` is set to `on`, `?` cannot be used as an operator.

## Syntax<a name="en-us_topic_0283137542_en-us_topic_0237122167_en-us_topic_0059778902_se242be9719f44731b261539dbd42d7b9"></a>

```
PREPARE name [ ( data_type [, ...] ) ] { AS | FROM } statement;
PREPARE name [ ( data_type [, ...] ) ] { AS | FROM } 'statement';
```

## Parameter Description<a name="en-us_topic_0283137542_en-us_topic_0237122167_en-us_topic_0059778902_s06dfa4f09bfd4e0d9826a80e6a91b0a6"></a>

- **name**

    Specifies the name of a prepared statement. It must be unique in the session.

- **data_type**

    Specifies the data type of the parameter.

- **statement**

    Specifies a SELECT, INSERT, UPDATE, DELETE, MERGE INTO, or VALUES statement.

## Examples<a name="en-us_topic_0283137542_en-us_topic_0237122167_en-us_topic_0059778902_sfff14489321642278317cf06cd89810d"></a>

```
openGauss=# CREATE TABLE test(name text, age int);
CREATE TABLE
openGauss=# INSERT INTO test values('a',18);
INSERT 0 1
openGauss=# PREPARE stmt FROM SELECT * FROM test;
PREPARE
openGauss=# EXECUTE stmt;
 name | age 
------+-----
 a    |  18
(1 row)
openGauss=# set b_compatibility_mode to on;
SET
openGauss=# PREPARE stmt1 FROM 'SELECT sqrt(pow(?,2) + pow(?,2)) as test';;
PREPARE
openGauss=# EXECUTE stmt1 USING 6,8;
 test
------
   10
(1 row)
```
