# 🏍️ Projeto OndeTáMoto? - Testes e Validação

## 📘 Descrição Geral

O projeto **OndeTáMoto?** é uma solução baseada em **IoT (Internet das Coisas)** desenvolvida para a empresa **Mottu** com o objetivo de **otimizar o controle e monitoramento em tempo real** das motos dentro de suas garagens. Cada moto é equipada com uma tag inteligente, registrando instantaneamente sua movimentação e status (dentro/fora). A solução é composta por um backend em **.NET** (Java e C# - conforme CT-003) com APIs REST e um aplicativo mobile.

Este repositório contém os artefatos de teste para validação do sistema:
- O **Plano de Testes Manuais** (documento com os Casos de Teste CT-001 a CT-005).
- A **Api** para testes das principais rotas 

---

## Link do Video 
https://www.youtube.com/watch?v=kZWXGFVOh-M

---

## 🧩 Parte A - Plano de Testes Manuais (Azure Boards)

Os testes manuais de nível de sistema para as funcionalidades principais do projeto foram planejados e executados na plataforma **Azure Boards**, conforme os critérios obrigatórios.

| ID | Caso de Teste | Objetivo Principal | Status | Data de Execução |
|----|----------------|----------------------------------|--------|--------------------|
| CT-001 | Registro de Moto com Tag Válida | Cadastrar uma nova moto e parear com a tag IoT. | Aprovado | 03/10/2025 |
| CT-002 | Localização em Tempo Real | Exibir a localização atualizada da moto no módulo de monitoramento. | Aprovado | 04/10/2025 |
| CT-003 | Teste de Backend (Java e C#) | Validar as operações CRUD (GET, POST, PUT, DELETE) no backend e banco de dados. | Aprovado | 03/10/2025 |
| CT-004 | Login de Mobile (Cenário de Falha) | Impedir o login com e-mail válido e senha incorreta. | Aprovado | 03/10/2025 |
| CT-005 | Visualização de Mobile e IOT | Garantir que o Mobile receba todas as tags das motos ativas do IOT. | Aprovado | 03/10/2025 |


**Instruções de Acesso:** O plano de testes está estruturado no Azure Boards: `Test Plan` → `Plano de Testes - OndeTáMoto` → `Test Suite` → `Funcionalidades Principais`.
**Possui o PDF com os testes Manuais caso precise com nome de Casos-de-Teste-OndeTaMoto (2).pdf no proprio Github** 

---

## 🤖 Parte B - Testes Automatizados (Swagger)

Use o Swagger (http://191.235.235.207:5294/swagger/index.html) e os exemplos a baixo 

## Exemplos para rodar

```json



Criar uma nova moto

POST /api/Moto
Content-Type: application/json

{
  "id": 1,
  "nome": "mottu",
  "tag": "alomottu2",
  "placa": "1236784"
}


Atualizar moto por ID

PUT /api/Moto/1
Content-Type: application/json

{
  "id": 1,
  "nome": "Honda atualizado",
  "tag": "aloHonda123",
  "placa": 1234567
}






```


### 🔗 Endpoints e Casos de Teste Automatizados:

| Método | Endpoint | Caso de Teste Automatizado |
|--------|-----------|-----------|
| POST | /api/moto | **Criar nova moto** (Simula o cadastro inicial) |
| PUT | /api/moto/{id} | **Atualizar moto** (Simula a alteração de status/informações) |
| POST | /api/usuario | **Criar usuário** (Simula o cadastro de um novo operador Mottu) |

### ⚙️ Instruções de Execução:
1.  Abra o link do Swagger
2.  Use os exemplos acima 
3.  O resultado esperado é que todos os testes retornem **Status 200** (OK) ou **201** (Created).

---

## 🧑‍💻 Desenvolvido por
**Nicolas Guinante** (RM: 557844)  
**Murilo Capristo** (RM: 556794)  
**Guilherme Romanholi Santos** (RM: 557462)

