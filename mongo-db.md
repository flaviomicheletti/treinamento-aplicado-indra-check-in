# mongo-db


### Inicializar o serviço no Windows


1)

    window + cmd
    abrir o terminal como administrador
     "C:\Program Files\MongoDB\Server\4.0\bin\mongod.exe" --dbpath "C:\Program Files\MongoDB\Server\4.0\data"

Se você não for administrador receberá o erro "exception in initAndListen: IllegalOperation".


2)

    window + cmd
    abrir o terminal como administrador
     "C:\Program Files\MongoDB\Server\4.0\bin\mongod.exe" --dbpath "C:\pasta-qualquer\data"

3)

    window + cmd
    abrir o terminal como administrador
    net start MongoDB

Se você não for administrador receberá o erro "Acesso negado".

4)

    window + r
    services.msc
    procurar o serviço "Mongo DB"
    startar na unha
