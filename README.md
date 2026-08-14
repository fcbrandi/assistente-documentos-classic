Assistente de Documentos

Aplicação web para leitura, organização e consulta de documentos com apoio de inteligência artificial.

Funcionalidades

Envio e processamento de documentos.

Leitura de arquivos PDF e DOCX.

Extração de informações com a API da OpenAI.

Organização e consulta de documentos processados.

Interface web desenvolvida com FastAPI.

Tecnologias

Python

FastAPI e Uvicorn

OpenAI API

PyPDF e python-docx

Oracle Cloud Infrastructure

Nginx

Segurança

A chave da OpenAI fica somente no arquivo .env.local do servidor. Esse arquivo, a pasta uploads, o ambiente virtual e os índices gerados não são enviados ao GitHub.

Estrutura

main.py — aplicação web.

documentos.py — leitura de documentos.

indice.py — índice e consultas.

config.py — configurações.