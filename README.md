# Effort extension project

������ ��� �������� ���������� Azure DevOps server, ����������� ����������� ����� ��������� �� ������ ��������� ������������, �� � ��������� ���������.
### Prerequisites

Docker Desktop for Windows or Docker Toolbox.

## Getting Started

```powershell
git clone https://github.com/Iloer/effort-extension.git
cd effort-extension
```

### Run Effort DB
```powershell
docker build -f .\LocalDB\dockerfile.postgres -t effortdb .
docker run -p 5432:5432 --name effortdb --hostname effortdb -e "POSTGRES_PASSWORD=postgres" -d effortdb
```

### Run Effort API service
```powershell
docker build -f .\EffortAPIService\Dockerfile -t effortapiservice .
docker run -p 31501:80 --name effortapiservice-dev --rm effortapiservice -e "ConnectionStrings:DefaultConnection=Host=effortdb;Port=5432;Database=postgres;Username=postgres;Password=postgres"
```
������ ����� �������� �� ������: http://localhost:31501/index.html

## Effort API service
������ ��� ������ � ������ ������ � �� ���������� ��������.

## Effort-extension
TypeScript React ���������� ��� ����������� ���������� � ��������� � ����� �������� �������.
�������� ��� � ��������, ��� � ������������� � � ���������� ��� Azure DevOps server
