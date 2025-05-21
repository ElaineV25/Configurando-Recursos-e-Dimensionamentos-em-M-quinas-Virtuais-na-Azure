# Configurando Recursos e Dimensionamentos em VMs na Azure

Configurar recursos e dimensionamento de Máquinas Virtuais (VMs) na Azure é uma etapa essencial para equilibrar performance, custo e disponibilidade. Abaixo está um guia prático com:

✅ Passo a passo de criação/configuração

🧠 Como escolher o dimensionamento correto

🔧 Ajustes pós-criação (escala, discos, redes)

📁 Sugestão para seu repositório

✅ 1. Criando uma Máquina Virtual no Azure
Acesse o Portal
→ https://portal.azure.com

Crie um novo recurso
→ “Criar um recurso” > “Máquina Virtual”

Preencha os dados básicos:

Assinatura e Grupo de Recursos

Nome da VM (ex: vm-web-prod)

Região (ex: Brazil South)

Imagem: Windows Server, Ubuntu, etc.

Tamanho (SKU da VM): Veja mais abaixo

Configurar usuário e autenticação

Login + senha ou chave SSH

Configurações adicionais

Disco (padrão = SSD premium ou HDD)

Rede: criar VNet/Subnet/NIC, NSG (grupo de segurança de rede)

Diagnóstico, Extensões, Backup

Revisar e criar

📏 2. Dimensionando a VM (SKU - Tamanho e Série)
Azure oferece dezenas de SKUs de VM. Aqui estão as principais séries e suas indicações:

Série	Uso ideal
B-series	Baixo custo, cargas leves (testes/dev)
D-series	Cargas gerais (web, apps, bancos leves)
E-series	Otimizada para memória (bancos, SAP)
F-series	Otimizada para CPU (aplicações intensivas)
N-series	GPU (IA, renderização, vídeo)
L/H-series	Storage/Computação de alto desempenho

🔹 Dica: Use a calculadora de preços:
👉 https://azure.com/e/pt-br/pricing/calculator

🔄 3. Redimensionar ou Reconfigurar uma VM Existente
Após criar, você pode:

✅ Redimensionar (alterar SKU da VM)
Pare a VM

Vá até “Tamanho”

Escolha outro SKU disponível para a região

Clique em “Redimensionar”

✅ Adicionar ou redimensionar disco
Vá em “Discos” > “+ Adicionar disco”

Escolha tipo: HDD / SSD / Ultra

✅ Alterar configurações de rede
Trocar subnet, NSG, IP público

Configurar balanceador de carga (Load Balancer)

🔄 4. Autoescala e Disponibilidade
Disponibility Set ou Availability Zone: Alta disponibilidade

Escala automática: use VM Scale Sets para criar e escalar automaticamente várias instâncias com base em CPU, tempo ou regras.

--------------------------

Na Microsoft Azure, os **aplicativos de funções** referem-se, em geral, ao **Azure Functions**, que é um serviço de *computação serverless* (sem servidor). Ele permite que você execute código sob demanda sem precisar gerenciar explicitamente uma infraestrutura de servidor.

### 📌 O que são **Azure Functions**?

Azure Functions são pequenos pedaços de código (funções) que são acionados por eventos. Você escreve apenas a lógica da função, e a Azure se encarrega do provisionamento e da escalabilidade.

---

### ✅ **Principais Aplicações do Azure Functions**

1. **Automação de Tarefas e Processos**

   * Enviar e-mails automáticos com base em eventos (ex: novo registro no banco de dados).
   * Processamento de arquivos ao serem carregados no Blob Storage.

2. **APIs Serverless**

   * Criar endpoints HTTP para responder a requisições RESTful.
   * Backend leve para aplicativos web ou mobile.

3. **Integração de Sistemas**

   * Conectar e automatizar fluxos entre serviços como Azure Storage, Event Grid, Service Bus, Cosmos DB, etc.
   * Usado em cenários com lógica condicional e transformação de dados.

4. **Processamento de Dados em Tempo Real**

   * Processar eventos de IoT ou streams de dados.
   * Realizar cálculos ou limpeza de dados em ingestão.

5. **Execução Programada (Timer Triggers)**

   * Substituir tarefas agendadas (como cron jobs).
   * Exemplo: gerar relatórios diários às 3h da manhã.

---

### 🔧 **Tipos de Triggers (gatilhos) suportados**

* **HTTP Trigger** (requisições web)
* **Timer Trigger** (execução agendada)
* **Blob Trigger** (mudança em arquivos no Azure Storage)
* **Queue Trigger** (mensagens em fila)
* **Event Hub / Event Grid Trigger**
* **Cosmos DB Trigger**

---

### 🧩 Linguagens Suportadas

* C#
* JavaScript / TypeScript
* Python
* Java
* PowerShell
* Go (em preview ou via custom handler)

---

### 💡 Casos de uso comuns:

| Caso de uso             | Descrição                                                  |
| ----------------------- | ---------------------------------------------------------- |
| Webhooks                | Reagir a eventos de serviços externos (ex: GitHub, Stripe) |
| ETL Serverless          | Extrair-transformar-carregar dados de forma leve           |
| Backend para Chatbots   | Com Azure Bot Service                                      |
| Conversão de documentos | PDF para imagem, etc.                                      |
| Processamento paralelo  | Executar várias funções em paralelo a partir de filas      |

---
