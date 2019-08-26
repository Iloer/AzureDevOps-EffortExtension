# Effort extension project

������ ��� �������� ���������� Azure DevOps server, ����������� ����������� ����� ��������� �� ������ ��������� ������������, �� � ��������� ���������.
### Prerequisites

Docker Desktop for Windows or Docker Toolbox.

## Getting Started

```bash
git clone https://github.com/Iloer/effort-extension.git
cd effort-extension
docker build -f .\EffortAPIService\Dockerfile -t effortapiservice .
docker run -p 31501:80 --name effortapiservice-dev --rm effortapiservice
```
������ ����� �������� �� ������: http://localhost:31501/index.html

## Effort API service
������ ��� ������ � ������ ������ � �� ���������� ��������.

## Effort-extension
TypeScript React ���������� ��� ����������� ���������� � ��������� � ����� �������� �������.
�������� ��� � ��������, ��� � ������������� � � ���������� ��� Azure DevOps server
