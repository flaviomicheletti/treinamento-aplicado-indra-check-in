# Quebrando o gelo com Maven


Documentação oficial https://maven.apache.org/index.html


### Missão 1

Download https://maven.apache.org/download.cgi

Instalação https://maven.apache.org/install.html

Maven foi instalado corretamente ?

Execute no Gitbash e no PowerShell

    mvn --version


### Missão 2

Você acessa o repositório maven ?

Primeiro, teste pelo navegador.

http://repo.maven.apache.org/maven2/

Segundo, teste pelo terminal.

    curl http://repo.maven.apache.org/maven2/

Mais um teste pelo terminal

    ping repo.maven.apache.org


### Missão 3

Leitura rápida https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html

Os próximas missões dependem deste artigo.


### Missão 4

Veja a seção "Creating a Project" e execute o linha de comando `mvn archetype:generate...` com sucesso.

Dica 1: Você criou o arquivo `pom.xls` ?

Dica 2:

+ https://www.linkedin.com/pulse/construindo-seu-pr%C3%B3prio-maven-archetype-roner-damaso-junior/
+ https://superuser.com/questions/1422212/apache-maven-generate-fails-to-create-project-using-the-command-provided-at-the


### Missão 5

Entenda detalhes do Maven.

Ábra o Explorer na pasta `${user.name}/.m2/repository/` e delete o que estiver por lá.

Execute novamente o comando `mvn archetype:generate...` e veja as pastas sendo criadas.


### Missão 6

Executar todos os comandos da seção "Build the Project".


Dica 1:

Caso receba esse erro `No compiler is provided in this environment. Perhaps you are running on a JRE rather than a JDK?`

Tente criar a variável de usuário (não precisa ser de ambiente) `JAVA_HOME`.


### Missão 7

Executar todos os comandos da seção "Running Maven Tools".

No final, abrir o site `my-app/target/site` e me mostrar o resultado.


### Missão 8

Dar uma navegada pela documentação.

Fique atento para o conceito de "Build Lifecycle".


### Missão 9

Atacar a lista de [missões do spring]("../spring.md").

Começar pela missão 4 [Building Java Projects with Maven](https://spring.io/guides/gs/maven/)

Caso você tenha iniciado a lista de missões do spring com gradle, execute tudo novamente com __mavem__.

