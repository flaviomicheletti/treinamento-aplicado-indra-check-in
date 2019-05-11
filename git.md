# Git

- [Site oficial](http://git-scm.com/)
- [Site oficial - docs](http://git-scm.com/docs)
- [Site oficial - Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)
- [Livro Pro Git, na web e em português](http://git-scm.com/book/pt-br/)
- [Pequeno tutorial](http://www.devfuria.com.br/git/)
- [Resumo dos principais comandos do Git](http://www.devfuria.com.br/git/resumo/)


### Missão 1

Configurar seu git para exibir corretamente seu nome email.

http://www.devfuria.com.br/git/dicas-configuracao/


### Missão 2

Configurar o proxy.

__Turn on...__

    git config --global http.proxy http://usuario-de-rede:sua-senha@proxylatam.indra.es:8080

[fonte](https://www.freecodecamp.org/forum/t/git-behind-a-proxy-server/13187)

Caso sua senha possua caracteres especiais, pode não funcionar. Mas não tema, temos uma solução.

Você deve codificar sua senha em UTF-8, de forma que ela seja aceita.

Utilize a [tabela ASCII](https://www.w3schools.com/tags/ref_urlencode.asp) da W3Schools para te ajudar a fazer essa codificação. O comando continua o mesmo, apenas sua senha que necessitará está codificada.

[fonte](https://askubuntu.com/questions/60217/apt-get-update-with-an-in-password-error)

__Turn off...__

    [https://stackoverflow.com/questions/11499805/git-http-proxy-setting]


To find out if you added the proxy entry to the global or local config files run this from the console:

    git config -l --global | grep http          # this will print the line if it is in the global file
    git config -l | grep http                   # this will print the line if it is in the repo config file

Then to remove all the http.proxy entries from either the global or the local file run this:

    git config --global --unset-all http.proxy  # to remove it from the global config
    git config --unset-all http.proxy           # to remove it from the local repo config file


### Missão 3

Clonar o repositório abaixo

https://github.com/flaviomicheletti/github-foo

Alterar o readme na seção "deixe sua marca".

Commitar e fazer push.

Realizar um Pul Request.


### Missão 4

Clonar o repositório https://github.com/minsait-veloe/check-in
