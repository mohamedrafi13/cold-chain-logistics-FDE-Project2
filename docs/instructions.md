#  Ingesting data
- Download dataset from 'C:\Users\Ayeshafia\Project\Cold-Chain_Logistics_AI-Assistant\data\source\dynamic_supply_chain_logistics_dataset.csv'
- create EC2 Instance > docker container > mcr.microsoft.com/mssql/server:2022-latest
- Spin up the legacy  MSSQL Server
````
docker run -e "ACCEPT_EULA=Y" -e "MSSQL_SA_PASSWORD=FdeEnterprisePass123!" -p 1433:1433
--name legacy-mssql -d mcr.microsoft.com/mssql/server:2022-latest
# Multi-line volume inside EC2
- docker run -v mssql_data:/var/opt/mssql \
  -e "ACCEPT_EULA=Y" \
  "MSSQL_SA_PASSWORD=FdeEnterprisePass123!" \
  -p 1433:1433 \
  --name legacy-mssql \
  -d mcr.microsoft.com/mssql/server:2022-latest

Install the req > pip install -r requirements.txt