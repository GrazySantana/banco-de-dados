# Comandos SQL - referência
<!-- ___________________________________________________ -->
## Modelagem física

### Criar banco de dados
```sql

CREATE DATABASE vendas CHARACTER SET utfBmb4,

```


<!-- ___________________________________________________ -->

### Criar a tabela fabricantes

```sql

CREATE TABLE fabricantes(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(45) NOT NULL
)
```
<!-- ___________________________________________________ -->

### Criar a tabela produtos

```sql

CREATE TABLE produtos(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(45) NOT NULL,
    descricao TEXT(1000) NOT NULL,
    preco DECIMAL(6,2) NOT NULL,
    quantidade TINYINT(4) NOT NULL,
)

```

<!-- ___________________________________________________ -->

### Adicionar campo/coluna em uma tabela

```sql

ALTER TABLE produtos ADD fabricante_id INT NOT NULL
AFTER quantidade;

```

<!-- ___________________________________________________ -->

### Criação da chave estrangeira (relacionamento entre tabelas)

```sql

ALTER TABLE produtos
    # CONSTRAINT é uma restrição definida no relacionamento
ADD CONSTRAINT fk_produtos_fabricantes

    # A chave estrangeira deve fazer referência a chave primária
FOREIGN KEY (fabricante_id) REFERENCES fabricantes(id)

```

