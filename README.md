n8n-nodes-microsoft-planner








🚀 Nó da comunidade n8n para integração completa com o Microsoft Planner, permitindo criar, gerenciar e automatizar tarefas diretamente nos seus workflows.

📌 Visão Geral

Este pacote adiciona um nó do Microsoft Planner ao n8n
, permitindo:

Criar e gerenciar tarefas

Atribuir usuários por e-mail

Trabalhar com buckets e planos

Recuperar arquivos anexados às tarefas

Executar operações CRUD completas

🔗 Tecnologias

Plataforma: n8n (workflow automation)

API: Microsoft Graph (Planner)

Autenticação: OAuth2

📚 Índice

Instalação

Pré-requisitos

Configuração no Azure AD

Credenciais no n8n

Funcionalidades

Operações Disponíveis

Exemplos de Uso

Compatibilidade

Histórico de Versões

Licença

Autor

Suporte

📦 Instalação
🔹 Instalação via Community Nodes (Recomendado)

Acesse Settings > Community Nodes no n8n

Clique em Install

Informe:

@blickwerk/n8n-nodes-microsoft-planner


Aceite os riscos dos nós da comunidade

Finalize clicando em Install

✅ Após a instalação, o nó estará disponível como qualquer outro no editor de workflows.

🔹 Instalação Manual
npm install @blickwerk/n8n-nodes-microsoft-planner


⚠️ Importante: Reinicie o n8n após a instalação manual.

🔐 Pré-requisitos

Antes de começar, você precisa de:

✔️ Assinatura ativa do Microsoft 365

✔️ Um plano criado no Microsoft Planner

✔️ Um App registrado no Azure AD com as permissões corretas

Permissões obrigatórias da API
Permissão	Descrição
Tasks.ReadWrite	Criar e editar tarefas
Group.ReadWrite.All	Acesso aos grupos (obrigatório para Planner)
User.Read.All	Buscar usuários para atribuição por e-mail

💡 Dica: Sem User.Read.All, a atribuição de tarefas por e-mail não funcionará.

☁️ Configuração no Azure AD
🧩 Criar App Registration

Acesse o Azure Portal

Vá em Azure Active Directory > App registrations

Clique em New registration

Nome sugerido: n8n Microsoft Planner Integration

Tipo de conta:

Accounts in this organizational directory only

Redirect URI:

https://SUA-INSTANCIA-N8N/rest/oauth2-credential/callback


Clique em Register

🔑 Configurar Permissões de API

Acesse API permissions

Clique em Add a permission

Selecione Microsoft Graph

Escolha Delegated permissions

Adicione:

Tasks.ReadWrite

Group.ReadWrite.All

User.Read.All

Clique em Grant admin consent

🚨 Atenção: Sem o consentimento do administrador, o nó não funcionará corretamente.

🔒 Criar Client Secret

Vá em Certificates & secrets

Clique em New client secret

Defina descrição e validade

Copie o Value imediatamente

❗ O valor do secret não pode ser recuperado depois.

🔑 Credenciais no n8n

Vá em Credentials > New

Busque por Microsoft Planner OAuth2 API

Preencha:

Client ID

Client Secret

Clique em Connect my account

Complete o fluxo OAuth2

✅ Pronto! Suas credenciais estão configuradas.

✨ Funcionalidades

🧭 Resource Locator UI

Seleção via lista ou ID manual

👤 Atribuição de usuários por e-mail

🚦 Controle de prioridade

Urgente | Importante | Médio | Baixo

🗂️ Gerenciamento de Buckets

📎 Recuperação de arquivos anexados

🔄 CRUD completo de tarefas

🔧 Operações Disponíveis
📝 Tarefas (Task)
Operação	Descrição
Create	Criar nova tarefa
Get	Buscar tarefa por ID
Get Many	Buscar várias tarefas
Update	Atualizar tarefa
Delete	Excluir tarefa
Get Files	Listar arquivos anexados
🚀 Exemplos de Uso
Criar uma Tarefa

Campos obrigatórios

Plan ID

Bucket

Title

Campos opcionais

Descrição

Prioridade

Usuários (por e-mail)

Datas de início e término

Percentual de conclusão

📧 Exemplo de usuários:

usuario1@empresa.com, usuario2@empresa.com

📎 Obter Arquivos de uma Tarefa

Retorno da operação:

taskId

fileCount

files[]

URL decodificada do SharePoint

Nome do arquivo

Tipo

Última modificação

🧩 Compatibilidade

✔️ Testado com n8n 1.0.0 ou superior

🗂️ Histórico de Versões

📌 Histórico completo mantido conforme versão original do pacote.

📄 Licença

Distribuído sob licença MIT
Veja o arquivo LICENSE

👨‍💻 Autor

Desenvolvido por Blickwerk Media UG

🌍 Sobre a Blickwerk Media

Agência digital sediada na Alemanha, especializada em automação, design e soluções web.

🌐 https://blickwerk.media

💼 https://linkedin.com/company/blickwerkmedia

📸 https://instagram.com/blickwerk.media

🆘 Suporte

💬 Dúvidas, problemas ou contribuições?
Acesse o repositório no GitHub:

👉 https://github.com/blickwerk/n8n-nodes-microsoft-planner
