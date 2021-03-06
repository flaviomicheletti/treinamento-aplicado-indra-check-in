
# DynamoDB

[Getting Started DynamoDB](https://docs.aws.amazon.com/pt_br/amazondynamodb/latest/developerguide/GettingStarted.Java.html)

### Download DynamoDB Local

[Download DynamoDB local](https://docs.aws.amazon.com/pt_br/amazondynamodb/latest/developerguide/DynamoDBLocal.DownloadingAndRunning.html)

Para rodar o Dynamo no local entre pelo terminal na pasta do seu download e rode o comando

	java -Djava.library.path=./DynamoDBLocal_lib -jar DynamoDBLocal.jar -sharedDb

Caso esteja utiliando o PowerShell:

	java -D"java.library.path=./DynamoDBLocal_lib" -jar DynamoDBLocal.jar
	
Mantenha o dynamo rodando para criação de tabelas, itens no local


### Criando Credenciais
Entre no [painel IAM do AWS](https://console.aws.amazon.com/iam/home#/home)

Entre em Usuários

Adicionar Usuario

Crie um nome de Usuario e marque a opção de **Tipo de Usuario**: Acesso Programático

Na próxima tela clique em **Anexar políticas existentes de forma direta**

Selecione a opção **Administrator Acess**

De próximo e depois revisar

Salve o ID e a Chave de Acesso

### Baixar AWS Toolkit for Eclipse

Abra o Eclipse, entre em Help → Install New Software

Clique em 'Add...'

Adicione o nome e o link: https://aws.amazon.com/eclipse 

Selecione **AWS Core Management Tools** e dê next

### Baixar AWS Cli

[Download AWS Cli](https://aws.amazon.com/pt/cli/)

Adicionar o caminho do aws.exe nas variaveis de ambiente Path

*No meu caso o caminho foi: C:\Program Files\Amazon\AWSCLI\aws.exe*

**aws --version** mostra se foi instalado e a versão

**aws configure** para adicionar as configurações de credenciais

Adicione seu ID, sua chave, região e tipo de saída

Exemplo:

	$ aws configure
	AWS Access Key ID [None]: AKIAIOSFODNN7EXAMPLE
	AWS Secret Access Key [None]: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
	Default region name [None]: us-east-2
	Default output format [None]: json


### Comandos AWS Cli

[Usar o Amazon DynamoDB com a AWS CLI](https://docs.aws.amazon.com/pt_br/cli/latest/userguide/cli-services-dynamodb.html)

Alguns terminais não aceitam a \ para pular linha, então ou deixe tudo na mesma linha ou veja qual o simbolo para pular linha do seu teminal

Exemplo do cmd que não aceita a \:

	aws dynamodb create-table --table-name MusicCollection --attribute-definitions AttributeName=Artist,AttributeType=S AttributeName=SongTitle,AttributeType=S --key-schema AttributeName=Artist,KeyType=HASH AttributeName=SongTitle,KeyType=RANGE --provisioned-throughput ReadCapacityUnits=5,WriteCapacityUnits=5

Para criar as tabelas/itens ... no local utilize o comando **--endpoint-url http://localhost:8000** no final de outros comandos

Exemplo:

	aws dynamodb create-table --table-name MusicCollection --attribute-definitions AttributeName=Artist,AttributeType=S AttributeName=SongTitle,AttributeType=S --key-schema AttributeName=Artist,KeyType=HASH AttributeName=SongTitle,KeyType=RANGE --provisioned-throughput ReadCapacityUnits=5,WriteCapacityUnits=5 --endpoint-url http://localhost:8000
	
Para mais comandos do dynamodb digite **aws dynamodb help** 

Link para comandos do aws dynamodb: https://docs.aws.amazon.com/cli/latest/reference/dynamodb/index.html
	
## Criando Projeto Java com DynamoDB

Eclipe → New ... → Other ... → AWS → AWS Java Project 

Caso não tenha, adicione no Pom.xml a dependência:

	<dependency>
		<groupId>com.amazonaws</groupId>
		<artifactId>aws-java-sdk-dynamodb</artifactId>
		<version>1.11.438</version>
	</dependency>
	
### Criando classe de configuração 

Para utilização local: 

	static AmazonDynamoDB client = AmazonDynamoDBClientBuilder.standard()
		.withEndpointConfiguration(new AwsClientBuilder.EndpointConfiguration("http://localhost:8000", "us-west-2"))
		.build();

	static DynamoDB dynamoDB = new DynamoDB(client);
	
Para utilizar com o web:

	static BasicAWSCredentials awsCreds = new BasicAWSCredentials("Key Id", "Secret Key"); //seta credenciais aws
		static AmazonDynamoDB client = AmazonDynamoDBClientBuilder.standard()
			.withCredentials(new AWSStaticCredentialsProvider(awsCreds)) //puxa credenciais
			.withRegion(Regions.SA_EAST_1) //seta a regiao
			.withClientConfiguration(clientConfig()) //puxa configuração de proxy
			.build();
	
	static DynamoDB dynamoDB = new DynamoDB(client);
	
Código para configuração do proxy:

	static public ClientConfiguration clientConfig(){

			// Variável com as configurações do cliente
			ClientConfiguration cli_config = new ClientConfiguration();

			// Setando configurações de proxy
			cli_config.setProxyHost("proxylatam.indra.es");
			cli_config.setProxyPort(8080);

			return cli_config;
	}

*As próximas classes deverão ser criados extendendo a classe de configuração**

## Criando classes do projeto

Link para o repositório com as classes: https://github.com/palomaslima/DynamoDB/tree/master/DynamoProject

Link para o arquivo JSON para carregar itens: https://docs.aws.amazon.com/pt_br/amazondynamodb/latest/developerguide/samples/moviedata.zip
