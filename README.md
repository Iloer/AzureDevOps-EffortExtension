# Effort extension project

������ ��� �������� ���������� Azure DevOps server, ����������� ����������� ����� ��������� �� ������ ��������� ������������, �� � ��������� ���������.
### Prerequisites

Docker Desktop for Windows or Docker Toolbox.

## Getting Started
�������� ���������
```powershell
git clone https://github.com/Iloer/effort-extension.git
cd effort-extension
```

������� � ��������� �������
```powershell
docker build -f .\LocalDB\dockerfile.postgres -t effortdb .
docker build -f .\EffortAPIService\Dockerfile -t effortapiservice .
docker-compose up
```

��������� ������ ���� ������
```powershell
docker run -p 5432:5432 --name effortdb --hostname effortdb -e "POSTGRES_PASSWORD=postgres" -d effortdb
```

��������� ������ API ������
```powershell
docker run -p 31501:80 --name effortapiservice-dev --rm effortapiservice -e "ConnectionStrings:DefaultConnection=Host=effortdb;Port=5432;Database=postgres;Username=postgres;Password=postgres"
```
������ ����� �������� �� ������: http://localhost:31501/index.html

> !!!�����: � ������ ������� �� ����������� ���� ������ � �������, �� �� ����� �������� �� HostName, ����� ���������� ��������� IP ����� ������ � �� � ���������� ��� � DefaultConnection. �������� �������� "docker inspect effortdb"


## Effort API service
������ ��� ������ � ������ ������ � �� ���������� ��������.

## Effort-extension
TypeScript React ���������� ��� ����������� ���������� � ��������� � ����� �������� �������.
�������� ��� � ��������, ��� � ������������� � � ���������� ��� Azure DevOps server
