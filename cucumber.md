# Cucumber


No __Gherkin__ cada um dos steps devem ser definidos principalmente com palavras chaves “Dado”, “Quando” e “Então”.

    (given) Dado   que eu tenha X
    (when)  Quando eu faço Y
    (then)  Então  eu recebo Z

A ideia é que quem a utilize tenha o mindset do __BDD__, pois cada uma dessas palavras propõe um mindset diferente.

### Dado (Given)

O propósito do “Dado” é colocar o sistema em um estado conhecido antes que o usuário comece a interagir com o sistema.
Pensando nos cenários tradicionais de teste, cada step que possui “Dado” seria uma pré-condição do caso de teste.


### Quando (When)

O Propósito do “Quando” é descrever uma ação chave que o usuário executa, resumidamente seria qualquer ação de interação
 do usuário com o sistema. Comparando novamente a casos de testes tradicionais, cada “Quando” seria um step do que fazer no caso de teste.


### Então (Then)

O “Então” visa mostrar as saidas, os resultados das ações executadas, seriam basicamente os resultados esperados em
casos de testes tradicionais.



## Fonte

https://cafecomteste.wordpress.com/category/gherkin/