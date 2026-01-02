Este é um nó da comunidade n8n que permite interagir com o Microsoft Planner em seus fluxos de trabalho do n8n.

O n8n
 é uma plataforma de automação de workflows com licença fair-code
.

O Microsoft Planner
 é uma ferramenta de gerenciamento de tarefas que ajuda equipes a organizar, atribuir e colaborar em atividades.

Instalação

Siga o guia de instalação
 da documentação de nós da comunidade do n8n.

Nó da Comunidade

Vá para Settings > Community Nodes na sua instância do n8n

Selecione Install

Digite @blickwerk/n8n-nodes-microsoft-planner em Enter npm package name

Aceite os riscos
 de usar nós da comunidade

Selecione Install

Após a instalação, você poderá usar o nó como qualquer outro em seus workflows.

Instalação Manual

Para instalar manualmente:

npm install @blickwerk/n8n-nodes-microsoft-planner

Pré-requisitos

Você precisa ter:

Uma assinatura ativa do Microsoft 365

Um plano criado no Microsoft Planner

Um App registrado no Azure AD com as seguintes permissões de API:

Tasks.ReadWrite – Ler e gravar tarefas

Group.ReadWrite.All – Ler e gravar todos os grupos (necessário para o Planner)

User.Read.All – Ler todos os usuários (necessário para atribuição de tarefas por e-mail)

Configurando o App no Azure AD

Acesse o Azure Portal

Navegue até Azure Active Directory > App registrations

Clique em New registration

Dê um nome ao app (ex.: n8n Microsoft Planner Integration)

Selecione Accounts in this organizational directory only

Adicione a Redirect URI:

https://sua-instancia-n8n.com/rest/oauth2-credential/callback


Clique em Register

Configurar Permissões de API

Vá até API permissions

Clique em Add a permission

Selecione Microsoft Graph

Escolha Delegated permissions

Adicione as seguintes permissões:

Tasks.ReadWrite – Ler e gravar tarefas

Group.ReadWrite.All – Ler e gravar todos os grupos

User.Read.All – Ler perfis básicos de todos os usuários

Clique em Grant admin consent

Nota: A permissão User.Read.All é obrigatória se você quiser atribuir tarefas usando o e-mail dos usuários.

Criar Client Secret

Vá em Certificates & secrets

Clique em New client secret

Adicione uma descrição e escolha o prazo de expiração

Copie o Value (ele não será exibido novamente)

Obter Detalhes da Aplicação

Client ID: disponível na página de visão geral do app

Client Secret: valor copiado no passo anterior

Credenciais no n8n

Configure as credenciais OAuth2 do Microsoft Planner no n8n:

No n8n, vá para Credentials > New

Procure por Microsoft Planner OAuth2 API

Informe o Client ID e o Client Secret

Clique em Connect my account

Conclua o fluxo de autenticação OAuth

Funcionalidades

Interface de Localização de Recursos: escolha entre From List (lista suspensa) ou By ID (entrada manual) para Buckets

Atribuição de Usuários: atribua tarefas usando e-mails

Gerenciamento de Prioridade: seletor simples (Urgente, Importante, Médio, Baixo)

Operações CRUD completas: Criar, Ler, Atualizar e Excluir tarefas

Operações
Tarefa (Task)

Create – Criar uma nova tarefa

Get – Buscar uma tarefa pelo ID

Get Many – Buscar múltiplas tarefas de um plano ou bucket

Update – Atualizar uma tarefa existente

Delete – Excluir uma tarefa

Get Files – Obter todos os arquivos anexados a uma tarefa

Uso
Criar uma Tarefa

Informe o Plan ID (disponível na URL do Planner ou via Graph Explorer)

Selecione um Bucket no dropdown (carregado automaticamente com base no Plan ID)

Informe o Title da tarefa

Campos opcionais:

Description – Descrição detalhada

Priority – Prioridade da tarefa:

Urgente (mais alta)

Importante

Médio (padrão)

Baixo

Assigned To – Lista de e-mails separados por vírgula

user1@dominio.com, user2@dominio.com


Due Date Time – Data/hora de conclusão

Start Date Time – Data/hora de início

Percent Complete – Percentual de conclusão (0–100)

Obter Tarefas

Buscar uma única tarefa:

Informe manualmente o Task ID

Buscar várias tarefas:

Escolha o tipo de filtro: Plan ou Bucket

Informe o Plan ID

Se filtrar por Bucket, selecione na lista ou informe o ID manualmente

Defina um limite ou retorne todas as tarefas

Atualizar uma Tarefa

Informe o Task ID

Atualize qualquer um dos campos:

Título

Descrição

Prioridade

Usuários atribuídos

Datas de início e término

Percentual de conclusão

Mover para outro bucket

Obter Arquivos de uma Tarefa

Informe o Task ID

A operação retorna:

taskId – ID da tarefa

fileCount – Número de arquivos anexados

files – Lista de arquivos contendo:

url – URL do SharePoint decodificada

alias – Nome exibido

type – Tipo do arquivo (PowerPoint, Word, Excel, PDF, Outros)

previewPriority – Prioridade de visualização

lastModifiedDateTime – Última modificação

lastModifiedBy – Quem modificou

Como Encontrar o Plan ID
Pela URL do Planner
https://tasks.office.com/.../planId=SEU_PLAN_ID/...

Pelo Microsoft Graph Explorer

Acesse https://developer.microsoft.com/graph/graph-explorer

Faça login

Execute:

GET /me/planner/plans


Copie o campo id do plano desejado

Resource Locator (From List / By ID)

From List – Seleção via dropdown (carregada automaticamente)

By ID – Entrada manual do ID

Para operações Get / Update / Delete, o Task ID deve ser informado manualmente.

Compatibilidade

Testado com n8n versão 1.0.0 ou superior.

Recursos

Documentação de nós da comunidade n8n

Documentação da API do Microsoft Graph Planner

Microsoft Graph Explorer

Histórico de Versões

(Conteúdo mantido, apenas traduzido)


Licença

MIT

Autor

Desenvolvido por Blickwerk Media UG

Sobre a Blickwerk Media

Somos uma agência digital sediada na Alemanha, especializada em automação, design e soluções web para diversos setores.

Nosso foco é criar workflows eficientes, experiências de marca fortes e contribuições open-source que conectem melhor as ferramentas digitais.

Site: https://blickwerk.media

LinkedIn: https://linkedin.com/company/blickwerkmedia

Instagram: https://instagram.com/blickwerk.media

Suporte

Para problemas, dúvidas ou contribuições, visite o repositório no GitHub
.
