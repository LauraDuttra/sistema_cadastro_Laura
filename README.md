# Sistema de Cadastro e Gerenciamento de Produtos 📦

## Visão Geral
Este projeto implementa um sistema de cadastro e gerenciamento de produtos e fornecedores. O sistema permite o cadastro de novos produtos, fornecedores, listagem e exclusão de produtos, e oferece uma interface de login para garantir que apenas usuários autenticados possam acessar as funcionalidades.

## Funcionalidades 🚀
- **Autenticação de usuários**: Apenas usuários autenticados podem acessar o painel de administração.
- **Cadastro de Fornecedores**: Cadastro de novos fornecedores com informações como nome e imagem.
- **Cadastro de Produtos**: Cadastro de produtos com nome, descrição, preço e imagem, além de associação a fornecedores.
- **Listagem de Produtos**: Exibição de produtos cadastrados com a possibilidade de editar ou excluir produtos.
- **Imagens de produtos**: Suporte para upload de imagens para os produtos.
- **Design responsivo**: O sistema foi projetado para se adaptar a diferentes tamanhos de tela, oferecendo uma boa experiência em dispositivos móveis e desktop.

## Estrutura do Projeto 🗂️
- **index.php**: Página inicial do sistema, disponível apenas para usuários logados.
- **login.php**: Página de login onde o usuário pode acessar o sistema.
- **logout.php**: Função para destruir a sessão do usuário e redirecioná-lo para o login.
- **cadastro_produto.php**: Página para cadastro e edição de produtos.
- **cadastro_fornecedor.php**: Página para cadastro e edição de fornecedores.
- **listagem_produtos.php**: Página para exibir todos os produtos cadastrados, com opções para editar ou excluir.
- **valida_sessao.php**: Arquivo para validar se o usuário está autenticado antes de acessar as páginas protegidas.
- **conexao.php**: Arquivo de conexão com o banco de dados MySQL.
- **style.css**: Arquivo de estilos que define a aparência do sistema.

## Tecnologias Usadas 💻
- _PHP_
- _MySQL_
- _HTML5_
- _CSS3_

## Como Usar 🚀

### 1. Configuração do Banco de Dados
1. Crie um banco de dados chamado `sistema` no seu servidor MySQL.
2. Crie as tabelas necessárias, como `usuarios`, `produtos`, e `fornecedores`, usando os seguintes comandos SQL:

```sql
CREATE TABLE usuarios (
    id INT AUTO_INCREMENT PRIMARY KEY,
    usuario VARCHAR(50) NOT NULL,
    senha VARCHAR(255) NOT NULL
);

CREATE TABLE fornecedores (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(255) NOT NULL,
    imagem VARCHAR(255)
);

CREATE TABLE produtos (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(255) NOT NULL,
    descricao TEXT,
    preco DECIMAL(10, 2),
    imagem VARCHAR(255),
    fornecedor_id INT,
    FOREIGN KEY (fornecedor_id) REFERENCES fornecedores(id)
);
```

### 2. Configuração do Ambiente
1. Instale o PHP e o MySQL no seu servidor.
2. Conecte seu banco de dados ao sistema, configurando corretamente as credenciais no arquivo `conexao.php`.

### 3. Processo de Autenticação
1. O usuário pode acessar a página de login em `login.php`.
2. Após a autenticação bem-sucedida, o usuário será redirecionado para a página inicial (`index.php`).
3. Para sair, o usuário pode acessar a página de logout (`logout.php`).

### 4. Cadastro de Produtos e Fornecedores
1. **Cadastro de Fornecedores**: Acesse a página `cadastro_fornecedor.php` para adicionar novos fornecedores, incluindo informações como nome e imagem.
2. **Cadastro de Produtos**: Acesse `cadastro_produto.php` para adicionar novos produtos, associando-os a um fornecedor já cadastrado. É possível incluir imagens dos produtos também.
3. **Listagem de Produtos**: A página `listagem_produtos.php` permite visualizar todos os produtos cadastrados e realizar ações como editar ou excluir produtos.

## Observações ⚠️
- **Autenticação**: Apenas usuários logados podem acessar as páginas de cadastro e listagem de produtos e fornecedores.
- **Banco de Dados**: O banco de dados é necessário para armazenar informações de produtos, fornecedores e usuários.
- **Upload de Imagens**: As imagens dos produtos e fornecedores devem ser carregadas para o servidor e salvas com o caminho correto no banco de dados.
---
## Agradecimentos 🙏

Muito obrigada por acessar este repositório! Esperamos que este sistema seja útil para a sua aplicação. Qualquer dúvida ou sugestão, sinta-se à vontade para abrir uma **issue** ou **pull request**.
