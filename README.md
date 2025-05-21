# Configurando-Recursos-e-Dimensionamentos-em-M-quinas-Virtuais-na-Azure

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
