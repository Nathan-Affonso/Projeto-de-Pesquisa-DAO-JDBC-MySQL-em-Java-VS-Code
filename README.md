# Projeto de Pesquisa - DAO + JDBC + MySQL em Java/VSCode

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

Para simplificar esta explicação, imagine o JDBC como se fosse um tradutor entre o Java e o banco de dados. O seu programa fala “Java”, enquanto o banco (como o MySQL) entende comandos SQL. O JDBC entra no meio justamente para fazer essa comunicação acontecer de forma correta.

### Exemplo prático de JDBC:

Imagine uma aplicação de cadastro de usuários onde é necessário salvar e listar dados no banco MySQL. Para isso, o sistema utiliza o JDBC para se conectar ao banco, enviar comandos SQL e receber os resultados. Assim, sempre que um usuário é cadastrado ou consultado, o JDBC faz toda a comunicação entre o Java e o banco.

### Antes (sem uso correto de JDBC)

* Conexões mal gerenciadas (não são fechadas)
* SQL montado diretamente com texto (risco de erro e **SQL Injection**)
* Código desorganizado
* Dificuldade para manter e identificar problemas

### Depois (uso correto de JDBC)

* Conexão aberta e fechada corretamente
* Uso de **PreparedStatement** para maior segurança
* Execução organizada de INSERT e SELECT
* Código mais confiável e fácil de manter


## Mas o que é SQL Injection? E PreparedStatement?

O SQL Injection é uma falha de segurança que acontece quando o sistema monta comandos SQL usando diretamente dados digitados pelo usuário na aplicação, permitindo que alguém insira códigos maliciosos e altere o funcionamento da consulta sem ter acesso direto ao banco de dados.

Já o PreparedStatement é uma forma mais segura e organizada de executar comandos SQL no Java usando JDBC. Em vez de montar a consulta juntando textos (por exemplo, concatenando o que o usuário digitou), você escreve o SQL com parâmetros (?) e depois passa os valores separadamente.

Por exemplo, em vez de fazer algo como:
> "SELECT * FROM usuarios WHERE nome = '" + nome + "'"

Você usa: 
> "SELECT * FROM usuarios WHERE nome = ?"
