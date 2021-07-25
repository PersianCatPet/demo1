# PersianCat.Demo1
This demo shows how to configure a monolith application by the Persian Cat framework.

<div>
<h3>In this demo, we use the following plugins</h3>
</div>

- PersianCat
- PersianCat.MVC
- PersianCat.Validation
- PersianCat.Logger
- PersianCat.OpenIdConnect
- PersianCat.MangoDb
- PersianCat.Redis


# Prerequisites
* .Net5 Sdk
* A suitable editor for .net environment. (Vs Code, Visaul Studio, JetBrians Rider)

# External service requirements
Depends on activating each service
* MongoDb on docker with replSet
<div>
<pre> 
docker run -p 27017:27017 --name mongodb mongo mongod --replSet rs0

docker exec -it mongodb mongo

config = {"_id" : "rs0","members" : [{"_id" : 0,"host" : "localhost:27017"}] }

rs.initiate(config)
</pre>
</div>
* RabbitMq on Docker
<div>
<pre> 
docker run -d --name rabbitmq-server --hostname MYHOST -p 15672:15672 -p 5672:5672 rabbitmq:3-management
</pre>
</div>
* Redis on Docker
<div>
<pre> 
docker run --name redis-server -d redis
</pre>
</div>
* Ef Core on Docker
<pre> 
docker run --name sqlServer -e "ACCEPT_EULA=Y" -e "SA_PASSWORD=MyStrongPassword" -p 1433:1433 -d mcr.microsoft.com/mssql/server:2017-CU8-ubuntu
</pre>
</div>
* OpenId connect server
<pre> 
* <a href="https://demo.identityserver.io/"> identityserver demo</a>
* <a href="https://auth0.com/docs/protocols/configure-okta-as-oauth2-identity-provider"> Configure Okta as OAuth2 Identity Provider</a>
</pre>
</div>


# How to run the demo
1. Make sure the required external services are running
1. execute the command `dotnet restore`
1. execute the command `dotnet build`
1. execute the command `dotnet run`
