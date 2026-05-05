# Projeto de Pesquisa - DAO + JDBC MySQL em Java/VSCode

## O que é DAO?
O DAO (Data Acess Object) é um padrão que separa o acesso ao banco de dados do restante da aplicação. Ele centraliza operações como inserir, consultar, atualizar e deletar dados, deixando o código mais organizado e fácil de manter. Também melhora a segurança e evita repetição de SQL. Em resumo, torna o sistema mais limpo e estruturado.
### Exemplo prático de DAO:

Imagine uma aplicação de cadastro de usuários. No começo, para ser mais rápido, o desenvolvedor colocou os comandos SQL diretamente nas telas e nas classes principais. O sistema funcionava, mas conforme cresceu, ficou difícil de entender, manter e atualizar, já que tudo estava misturado. Para resolver isso, foi aplicado o padrão DAO, criando uma classe responsável apenas por acessar o banco de dados. Assim, o restante do sistema passou a apenas chamar métodos dessa classe, deixando tudo mais organizado.

### Antes do DAO

* SQL direto nas telas ou classes principais
* Código misturado (interface + lógica + banco)
* Difícil manutenção
* Alterações afetam várias partes do sistema
* Maior risco de erros
### Depois do DAO

* Classe específica para acesso ao banco (ex: `UsuarioDAO`)
* Sistema usa métodos como `salvar()` e `listar()`
* Código separado e organizado
* Alterações centralizadas
* Sistema mais seguro e fácil de evoluir
  

## E o que é JDBC?
O JDBC (Java Database Connectivity) é uma tecnologia do Java que permite que um programa se conecte a um banco de dados, como o MySQL, e realize operações com os dados. Ele funciona como uma ponte entre a aplicação e o banco, possibilitando enviar comandos SQL e receber os resultados dessas operações.
