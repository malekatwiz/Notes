# Docker commands

## MS SQL Server

* Run MS SQL Server Linux image: ```docker run -e "ACCEPT_EULA=Y" -e "SA_PASSWORD=MyP@ssword!" -p [host port]]:1433 -d --name=[Container Name] microsoft/mssql-server-linux:2017-latest```

* Run command on SQL Server: ```docker exec -it [Container Name] /opt/mssql-tools/bin/sqlcmd -S localhost -U sa -P MyP@ssword!```