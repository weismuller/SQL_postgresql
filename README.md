### 📘 Projeto SQL — Gerenciamento Básico de Usuários

Este projeto demonstra operações essenciais em SQL para criação, consulta, atualização e exclusão de dados em uma tabela de usuários.
É um guia simples e direto para quem está começando a trabalhar com bancos de dados relacionais.


### 📝 Descrição

Este repositório contém um conjunto de comandos SQL utilizados para manipular uma tabela chamada usuarios.
O objetivo é demonstrar, de forma clara e didática, como realizar operações básicas de CRUD:

    Create (Criar)
    Read (Ler)
    Update (Atualizar)
    Delete (Excluir)

### 🛠️ Tecnologias utilizadas


| PostgreSQL |
|-----|
| <p align="center"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/postgresql/postgresql-original.svg" width="70"></p> |


---
    
### 🏗️ Criação da Tabela

  ```sql
    CREATE TABLE usuarios(
        id SERIAL PRIMARY KEY,
        nome VARCHAR(50) NOT NULL,  --campo não pode ser vazio
        email VARCHAR(50) UNIQUE NOT NULL, --obrigatório e não pode se repetir
        data_nascimento DATE NOT NULL, 
        data_criacao TIMESTAMP DEFAULT CURRENT_TIMESTAMP  --registra automaticamente o momento da criação do registro 
    );
```

---
    

### 📝 Inserindo Dados na Tabela
Insere múltiplos usuários de uma só vez, preenchendo nome, e‑mail e data de nascimento.
  ```sql
    INSERT INTO usuarios (nome, email, data_nascimento)
    VALUES
    ('Ana Souza', 'ana.souza@exemplo.com', '1988-03-12'),
    ('Carlos Pereira', 'carlos.pereira@exemplo.com', '1979-11-02'),
    ('Mariana Lima', 'mariana.lima@exemplo.com', '1995-07-21'),
    ('João Silva', 'joao.silva@exemplo.com', '1983-01-09'),
    ('Fernanda Alves', 'fernanda.alves@exemplo.com', '1992-05-30');
```

<img width="774" height="237" alt="image" src="https://github.com/user-attachments/assets/1d3d75a2-561f-44a1-8b68-9303791a5d9d" />


---

### 🗑️ Excluindo a Tabela
Remove completamente a tabela e todos os dados.

  ```sql
      DROP TABLE usuarios;
  ```

---

### 🔍 Filtros de Pesquisa
Buscar nomes que começam com "M"


  ```sql
  SELECT * FROM usuarios WHERE nome LIKE 'M%';
  ```


  ```sql
  SELECT * FROM usuarios WHERE nome LIKE 'M%' OR nome LIKE 'm%';
  ```

*O caractere % representa qualquer sequência de caracteres.  

<img width="767" height="195" alt="image" src="https://github.com/user-attachments/assets/1e937277-55ef-4a98-b1dc-260cb0bd4e5c" />

---

### 📚 Ordenação de Resultados

Ordem crescente (A → Z)

  ```sql
  SELECT * FROM usuarios ORDER BY nome ASC;
  ```
  Ordem decrescente (Z → A)
  ```sql
  SELECT * FROM usuarios ORDER BY nome DESC;
  ```

<img width="771" height="235" alt="image" src="https://github.com/user-attachments/assets/cdf0ccd8-87bd-45af-b64c-b72287986795" />

---

### 🎯 Limitando a Quantidade de Registros

  ```sql
  SELECT * FROM usuarios ORDER BY nome LIMIT 2;
  ```

Explicação:  
Retorna apenas os 2 primeiros registros após a ordenação.

<img width="1021" height="237" alt="image" src="https://github.com/user-attachments/assets/5088728a-c87d-4ec8-a1f1-7ced8b5f7aae" />


Explicação:  
Retorna apenas os 2 primeiros registros após a ordenação.


---


### ✏️ Atualizando um Registro

  ```sql
  UPDATE usuarios SET email = 'ana.souza@gmail.com' WHERE id = 1;
   ```


⚠️ Sempre use WHERE para evitar alterar todos os registros.

<img width="796" height="235" alt="image" src="https://github.com/user-attachments/assets/2b22069e-4d52-43dd-8ab2-0d312402e7f9" />

Explicação:  
Atualiza apenas o usuário com id = 1.

---

### ❌ Deletando um Registro

```sql
DELETE FROM usuarios WHERE id = 3;
```


<img width="831" height="233" alt="image" src="https://github.com/user-attachments/assets/56853e68-7475-43e9-b478-3f8a90ffcdd3" />
Explicação:  
Remove apenas o usuário com id = 3.

---

### ➕ Adicionando uma Coluna

```sql
ALTER TABLE usuarios ADD COLUMN idade SMALLINT NOT NULL DEFAULT 0;
```

<img width="848" height="268" alt="image" src="https://github.com/user-attachments/assets/274e76e1-8f01-4c83-af12-f7c80253e3f3" />

Explicação:  
Cria a coluna idade com valor padrão 0.


---


### ➖ Removendo uma Coluna

```sql
ALTER TABLE usuarios DROP COLUMN idade;
```

Explicação:  
Exclui a coluna idade da tabela.


---

<p align="center">
  Feito por <b>Weismuller Silva Santos</b>
</p>
