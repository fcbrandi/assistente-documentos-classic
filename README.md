# Assistente de Documentos

Aplicação web inteligente para processar, organizar e consultar documentos digitais com apoio da API da OpenAI.

## Descrição geral do projeto

O Assistente de Documentos permite que usuários enviem arquivos, principalmente em PDF e DOCX, para leitura e análise. O conteúdo é processado, organizado em um índice documental e disponibilizado para consulta pela interface web.

O objetivo é reduzir o tempo gasto na leitura manual de documentos e facilitar a localização de informações relevantes.

## Arquitetura da solução

```mermaid
flowchart LR
    U[Usuário] --> W[Interface Web]
    W --> A[FastAPI]
    A --> P[Processamento de documentos]
    P --> O[OpenAI API]
    P --> I[Índice documental]
    A --> N[Nginx]
    N --> U
Fluxo da aplicação
O usuário envia documentos pela interface web.
A aplicação lê arquivos PDF e DOCX.
O conteúdo é processado e organizado em um índice documental.
A API da OpenAI auxilia na interpretação das informações.
O usuário realiza consultas sobre os documentos processados.
A aplicação é publicada em uma VM Ubuntu na Oracle Cloud Infrastructure.
Tecnologias e ferramentas utilizadas
Categoria	Tecnologias
Linguagem	Python
Framework web	FastAPI
Servidor da aplicação	Uvicorn
Inteligência artificial	OpenAI API
Processamento de PDF	PyPDF
Processamento de Word	python-docx
Configuração	python-dotenv
Infraestrutura	Oracle Cloud Infrastructure
Proxy reverso	Nginx
Versionamento	Git e GitHub
Desenvolvimento remoto	Visual Studio Code Remote SSH


Estrutura do projeto
assistente-documentos/
├── main.py          # Aplicação web FastAPI
├── documentos.py    # Leitura e processamento de documentos
├── indice.py        # Índice e consultas documentais
├── config.py        # Configurações do projeto
├── README.md        # Documentação
└── .gitignore       # Arquivos não versionados
Instruções para executar o projeto
Pré-requisitos
Python 3.10 ou superior
Chave válida da OpenAI API
Git
Clonar o repositório
git clone URL_DO_REPOSITORIO
cd assistente-documentos
Criar ambiente virtual
python3 -m venv .venv
source .venv/bin/activate
No Windows:
.venv\Scripts\Activate.ps1
Instalar dependências
pip install fastapi "uvicorn[standard]" openai pypdf python-docx python-dotenv python-multipart
Configurar a chave da OpenAI
Crie o arquivo .env.local na raiz do projeto:
OPENAI_API_KEY=sua_chave_aqui
Nunca envie o arquivo .env.local ao GitHub.

Iniciar a aplicação
uvicorn main:app --host 127.0.0.1 --port 8000
Acesse:
http://137.131.250.22
Exemplos de perguntas que o assistente consegue responder
Quais documentos foram processados?
Quais arquivos foram enviados recentemente?
Existe algum documento relacionado a uma empresa específica?
Resuma o conteúdo deste documento.
Quais informações foram encontradas neste arquivo?
Quais documentos precisam de revisão?
Localize documentos que mencionam determinado assunto.
Quais arquivos estão disponíveis para consulta?
Exemplos de respostas geradas pelo assistente
Exemplo 1
Pergunta: Quais documentos foram processados?
Resposta: Foram encontrados documentos processados no índice documental. Os arquivos estão disponíveis para consulta individual pela aplicação.
Exemplo 2
Pergunta: Resuma o conteúdo deste documento.
Resposta: O documento apresenta informações relevantes extraídas do arquivo, como datas, nomes, identificações e outros dados textuais encontrados durante o processamento.
Exemplo 3
Pergunta: Existem documentos relacionados à empresa XYZ?
Resposta: Sim. Foram encontrados documentos que mencionam a empresa XYZ. A aplicação pode apresentar os arquivos relacionados para consulta.
Exemplo 4
Pergunta: Quais documentos precisam de revisão?
Resposta: Documentos com informações incompletas ou baixa confiança na extração devem ser revisados manualmente antes de qualquer utilização definitiva.
Implantação na OCI
A aplicação é executada em uma VM Ubuntu na Oracle Cloud Infrastructure.
A implantação utiliza:
Uvicorn para executar a aplicação FastAPI;
Nginx como proxy reverso na porta HTTP;
uma chave da OpenAI armazenada somente no servidor;
GitHub para versionamento e atualização do código.
Para atualizar a aplicação após uma alteração enviada ao GitHub:
cd /home/ubuntu/assistente-documentos
git pull origin main
sudo systemctl restart assistente-documentos
Segurança
Os seguintes itens não são enviados ao GitHub:
.env.local
.venv/
uploads/
arquivos temporários
índices gerados a partir dos documentos
Status do projeto
✅ Aplicação publicada na Oracle Cloud Infrastructure
✅ Processamento de documentos com IA
✅ Consulta de documentos indexados
✅ Versionamento com Git e GitHub
✅ Proteção de chaves e dados sensíveis
Projeto desenvolvido com Python, FastAPI, Oracle Cloud Infrastructure e OpenAI API.