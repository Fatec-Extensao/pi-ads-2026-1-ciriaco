# 🗄️ Banco de Dados I
**Disciplina:** Banco de Dados I
**Professor:** Prof. Luiz Fernando de Oliveira Silva

## 📂 Descrição da Pasta
Esta pasta armazena toda a modelagem de dados e os scripts SQL necessários para a criação e manipulação do banco de dados do sistema.

## 📄 Conteúdos Esperados
* Modelos Conceitual (DER) e Lógico (MER) em formato de imagem/PDF.
* `schema.sql`: Script DDL para criação de tabelas, chaves e relacionamentos.
* `queries.sql`: Scripts DML de inserção de dados de teste e consultas analíticas.
*  ## Normalização

O modelo foi organizado considerando as três primeiras formas normais:

- *1ª Forma Normal (1FN):* os atributos armazenam valores únicos e atômicos, sem listas ou grupos repetidos em uma mesma coluna.
- *2ª Forma Normal (2FN):* os atributos não chave dependem integralmente da chave primária. Todas as tabelas possuem chaves primárias simples.
- *3ª Forma Normal (3FN):* os atributos não chave não possuem dependências transitivas de outros atributos não chave. Na tabela RESPOSTA, removemos id_pergunta, pois a pergunta já é identificada por id_alternativa, por meio da tabela ALTERNATIVA.

Essa organização reduz a redundância e evita inconsistências na atualização dos dados.
