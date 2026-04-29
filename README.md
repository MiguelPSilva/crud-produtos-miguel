# API REST - Catálogo de Produtos

**Integrantes:**
- Miguel

## Instalação e Execução

1. Clone o repositório:
   `git clone <link-do-repositorio>`
2. Instale as dependências:
   `pip install fastapi uvicorn sqlalchemy pydantic`
3. Execute a API:
   `uvicorn main:app --reload`

## Justificativas das Decisões

- **Campos Obrigatórios vs Opcionais:** Na criação (POST) e na substituição (PUT), todos os campos são obrigatórios. Na atualização parcial (PATCH), todos os campos são opcionais.
- **Códigos de Status HTTP:** Utilizado 200 para GET/PUT/PATCH, 201 para POST e 204 para DELETE. Quando um ID não existe, retorna-se o erro 404.
- **Produto Não Encontrado:** A API retorna uma exceção HTTP 404 informando que o produto não foi localizado.
- **Estrutura de Arquivos e Banco:** Optamos pela estrutura single-file (main.py) pela simplicidade do CRUD exigido. Foi utilizado o SQLite em disco para persistência.
