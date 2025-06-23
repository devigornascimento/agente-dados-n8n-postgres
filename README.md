# agente-dados-n8n-postgres

Agente de Dados com n8n e PostgreSQL
Descrição
Este repositório contém o workflow de um agente de backend construído na plataforma low-code n8n. O projeto foi desenvolvido para atuar como uma ponte inteligente e responsiva entre uma aplicação front-end e um banco de dados PostgreSQL, automatizando a busca e entrega de informações em tempo real com base nas ações do usuário.

Arquitetura do Projeto
O fluxo de dados foi desenhado para ser simples e eficiente. A comunicação é iniciada pelo front-end e orquestrada inteiramente pelo n8n, que lida com a lógica de negócio e o acesso aos dados.

[Aplicação Front-End]  -->  (Ação do Usuário dispara Webhook)  -->  [Workflow n8n]
                                                                        |
                                                                        v
                                                                    (Executa consulta SQL dinâmica)
                                                                        |
                                                                        v
[Banco de Dados PostgreSQL] <-- (Solicita e recebe dados)  <--  [Nó de Banco de Dados]
        |
        v
(Retorna resposta em JSON)
        |
        v
[Aplicação Front-End]  <-- (Recebe os dados para exibir)  <--  [Workflow n8n]
Funcionalidades Principais
Comunicação via Webhook: O workflow é ativado instantaneamente por requisições HTTP (webhooks) enviadas pela aplicação front-end.
Orquestração de Processos: O n8n gerencia todo o fluxo da requisição, desde o recebimento dos parâmetros até a devolução da resposta final.
Consultas Dinâmicas ao Banco de Dados: Executa queries SQL dinâmicas e parametrizadas no PostgreSQL, permitindo que os filtros e as buscas sejam flexíveis e baseados nos dados enviados pelo usuário.
Respostas em Tempo Real: Processa e retorna os dados em formato JSON, garantindo baixa latência e uma experiência de usuário responsiva.
Tecnologias Utilizadas
Plataforma de Automação: n8n.io
Banco de Dados: PostgreSQL
Mecanismo de Comunicação: Webhooks
Formato de Dados: JSON
Como Configurar e Usar
Para implementar este workflow em sua própria instância do n8n, siga os passos abaixo:

Pré-requisitos:

Ter uma instância do n8n ativa (Cloud ou auto-hospedada).
Ter acesso a um banco de dados PostgreSQL.
Importar o Workflow:

Faça o download do arquivo nome-do-seu-workflow.json deste repositório.
Na sua instância do n8n, vá em Workflows e clique em Import from File....
Selecione o arquivo .json para fazer o upload.
Configurar Credenciais:

Dentro do workflow importado, localize o nó do PostgreSQL.
Clique no campo de credenciais e crie uma nova (Create New) ou selecione uma existente.
Preencha os dados de conexão do seu banco: Host, Database, User, Password e Port.
Ativar o Workflow:

Salve as alterações (Save).
Ative o workflow no botão Active no canto superior direito.
Copie a URL do Webhook de teste (Test URL) para usar em sua aplicação front-end.
