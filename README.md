# SQL

This image describes what the architecture looks like in a typical database software ecosystem.
![image](https://user-images.githubusercontent.com/78498035/233303739-3d5a104f-7de0-429a-82d5-0bace217bf71.png)

  * Database Software : common database software, such as MySQL, Postgre SQL, MsSQL, etc.
  * Database : We can divide different databases' structures into database software. In general, we   can seperate data entities with different `commerical meaning`.
  For instance, US stock data -> one database / UK stock data -> another database
  * Schema : This is a collection of tables, which can be split and grouped according to logic and some table details meta settings can be set on this layer, like blueprint.
   But in some database software (MySQL), Schema and Database are intergrated into one.
  * Table : The Key section of the database. Tables record different data entities (users, products)
  Each table is responsible for recording the column size, type, default value of each row data in database.
  * Data : The most valuable part of the database is the data itself. Different types of data can be stored. 

## Schema 
* Create a Schema 
```
CREATE SCHEMA `new_schema` DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```
* All capital part -> `keyword`, which is the vocabulary that the SQL programming language needs to use. (special meanings in SQL language)

* We set a common character 4-byte UTF-8 Unicode Encoding series -> `utf8mb4` and 'utf8mb4_unicode_ci`, which is included emoji-related symbols.

--------
### UTF-8
In order to store information, computers uses a binary system. In binary, all data is represented in sequences of 1s and 0s. The most basic unit of binary is `bit`, which is just a single 0 and 1. The next largest unit of binary, a `byte`, consists of 8 bits. Text is one of many assets that computers store and process. Text is made up of individual characters, each of which is represented in computers by a string of bits.
* Encoding : the process of converting characters in human languages -> binary sequences that computer can process.
* ASCII -> Unicode (assigns a unique code `code point` to each character.
But, Unicode alone doesn't store words in binary. Computers need a way to translate Unicode into binary so that its characters can be stored in text files. Here's where UTF-8 comes in.
* UTF-8 : It is a encoding system for Unicode.

1. Computers store data, including text characters, as binary (1s and 0s).
2. ASCII was an early way of encoding, or mapping characters to binary code so that computers could store them. However, ASCII did not provide enough room for non-Latin characters and numbers to be represented in binary.
3. Unicode was the solution to this problem. Unicode assigns a unique “code point” to every character in every human language.
4. UTF-8 is a Unicode character encoding method. This means that UTF-8 takes the code point for a given Unicode character and translates it into a string of binary. It also does the reverse, reading in binary digits and converting them back to characters.
5. UTF-8 is currently the most popular encoding method on the internet because it can efficiently store text containing any character.
6. UTF-16 is another encoding method, but is less efficient for storing text files (except for those written in certain non-English languages).
--------
A practical table SQL : 
```
id | name |	age
1	 | John	| 40
2	 | May  | 30
3	 | Tim	| 25
```
* Create table
```
CREATE SCHEMA `new_schema` DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;

CREATE TABLE `new_schema`.`new_table` (
  `id` INT NOT NULL COMMENT 'This is a primary index',
  PRIMARY KEY (`id`)
);
```
* Check whether the column settings are as we expected.
```
SHOW FULL COLUMNS FROM `new_schema`.`new_table`;
```
* Drop to remove a table in the database
```
DROP TABLE `new_schema`.`new_table`;
```
* Clean Table
```
TRUNCATE 'new_schema'.'new_table';
```

