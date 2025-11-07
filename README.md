# 🏍️ Projeto OndeTáMoto? - Testes e Validação

## 📘 Descrição Geral

O projeto **OndeTáMoto?** é uma solução baseada em **IoT (Internet das Coisas)** desenvolvida para a empresa **Mottu** com o objetivo de **otimizar o controle e monitoramento em tempo real** das motos dentro de suas garagens. Cada moto é equipada com uma tag inteligente, registrando instantaneamente sua movimentação e status (dentro/fora). A solução é composta por um backend em **.NET** (Java e C# - conforme CT-003) com APIs REST e um aplicativo mobile.

Este repositório contém os artefatos de teste para validação do sistema:
- O **Plano de Testes Manuais** (documento com os Casos de Teste CT-001 a CT-005).
- A **Collection Postman** para automação de testes das principais rotas da API.

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

### 🔍 Estrutura dos Testes Manuais (Azure Boards)

| Item Obrigatório | CT-001 (Exemplo) |
|---|---|
| **1) Teste Planejado** | CT-001 - Registro de Moto com Tag Válida |
| **2) Dados de Entrada / Pré-Condições** | Tag IoT está ativa e pareada com o sistema. Moto não está previamente cadastrada. Código da tagRFID válido, Placa, Modelo e Status preenchidos. |
| **3) Dados de Saída / Resultado Esperado** | Mensagem **"Moto cadastrada com sucesso"**. |
| **4) Procedimento (Passos)** | Acessar "Cadastro de Motos" > Inserir código da tagRFID válida > Preencher informações da moto > Clicar em "Salvar". |

**Instruções de Acesso:** O plano de testes está estruturado no Azure Boards: `Test Plan` → `Plano de Testes - OndeTáMoto` → `Test Suite` → `Funcionalidades Principais`.

---

## 🤖 Parte B - Testes Automatizados (Postman)

A coleção [`OndeTaMoto-API-Tests.postman_collection.json`](./OndeTaMoto-API-Tests.postman_collection.json) cobre **4 casos de testes automatizados** (Item 5), validando as principais rotas da API REST do backend, essenciais para o funcionamento do sistema.

### 🔗 Endpoints e Casos de Teste Automatizados:

| Método | Endpoint | Caso de Teste Automatizado |
|--------|-----------|-----------|
| POST | /api/moto | **Criar nova moto** (Simula o cadastro inicial) |
| GET | /api/moto | **Listar motos** (Simula a consulta de frota, como no Mobile) |
| PUT | /api/moto/{id} | **Atualizar moto** (Simula a alteração de status/informações) |
| POST | /api/usuario | **Criar usuário** (Simula o cadastro de um novo operador Mottu) |

### ⚙️ Instruções de Execução:
1.  Garanta que a API do projeto **OndeTáMoto?** esteja rodando localmente (ex: `http://localhost:5294`).
2.  Importe o arquivo `OndeTaMoto-API-Tests.postman_collection.json` no **Postman**.
3.  Utilize o **Collection Runner** para executar os 4 testes automatizados.
4.  O resultado esperado é que todos os testes retornem **Status 200** (OK) ou **201** (Created).

---

## 🧑‍💻 Desenvolvido por
**Nicolas Guinante** (RM: 557844)  
**Murilo Capristo** (RM: 556794)  
**Guilherme Romanholi Santos** (RM: 557462)

