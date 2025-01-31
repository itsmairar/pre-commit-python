# Configuração do pre-commit

## O que é o pre-commit?

O **pre-commit** é uma ferramenta que ajuda a garantir a qualidade do código ao executar verificações automáticas antes de cada commit. Ele impede que código mal formatado ou com problemas seja enviado ao repositório, seguindo os padrões da PEP 8.

## Arquivos utilizados

Para configurar o pre-commit no projeto, utilizamos três arquivos principais:

### 1. `.pre-commit-config.yaml`

Este arquivo contém a configuração dos hooks do pre-commit. Aqui são definidos quais verificações serão executadas antes de cada commit.

### 2. `pyproject.toml`

Este arquivo contém configurações personalizadas para ferramentas de formatação, como Black e isort.

### 3. `.flake8`

Este arquivo define regras específicas para o **flake8**, que é um analisador de código Python.

## O pre-commit é exclusivo para Python?

Não! Embora nesta configuração ele esteja configurado apenas para ferramentas Python, o pre-commit pode ser usado para qualquer linguagem. Basta adicionar novos hooks no arquivo `.pre-commit-config.yaml`. Por exemplo:

-   **ESLint** para JavaScript/TypeScript:
    
    ```yaml
    - repo: https://github.com/pre-commit/mirrors-eslint
      rev: v8.0.1
      hooks:
        - id: eslint
    
    ```
    
-   **Prettier** para formatação de código:
    
    ```yaml
    - repo: https://github.com/pre-commit/mirrors-prettier
      rev: v2.3.0
      hooks:
        - id: prettier
    
    ```
    
-   **ShellCheck** para scripts Shell:
    
    ```yaml
    - repo: https://github.com/koalaman/shellcheck-precommit
      rev: v0.8.0
      hooks:
        - id: shellcheck
    
    ```
    

## Como instalar e configurar o pre-commit

### 1. Instalar o pre-commit

Se ainda não tiver o pre-commit instalado, execute:

```sh
pip install pre-commit

```

### 2. Instalar os hooks do pre-commit

No diretório do seu projeto, execute:

```sh
pre-commit install

```

Isso irá configurar o pre-commit para rodar automaticamente antes de cada commit.

### 3. Rodar os hooks manualmente (opcional)

Caso queira testar os hooks antes de fazer um commit, use:

```sh
pre-commit run --all-files

```

### 4. Atualizar os hooks do pre-commit

Para manter as ferramentas sempre atualizadas, você pode rodar:

```sh
pre-commit autoupdate

```

Isso atualizará as versões dos hooks definidos no `.pre-commit-config.yaml`.

## Personalização do pre-commit

Cada projeto pode ter regras e ferramentas diferentes, e o pre-commit é altamente customizável. Algumas dicas para personalizar:

-   **Defina padrões claros**: Use ferramentas como Black, Isort e Flake8 para manter um estilo consistente.
-   **Adapte às necessidades do projeto**: Se você trabalha com outras linguagens, adicione hooks correspondentes.
-   **Respeite a PEP8**: Configure ferramentas para seguir as boas práticas do Python.
-   **Ajuste as regras conforme necessidade**: Altere configurações no `pyproject.toml` e `.flake8` para melhor se adequar as suas necessidades.