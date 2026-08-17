# Assistente de Documentos

Aplicação web para leitura, organização e consulta de documentos com apoio da inteligência artificial.

O sistema permite enviar documentos, extrair seus conteúdos, organizar informações importantes e realizar consultas sobre os arquivos processados.

## Visão geral

O Assistente de Documentos foi desenvolvido para centralizar documentos digitais em uma interface web simples. A aplicação utiliza a API da OpenAI para apoiar a interpretação dos conteúdos e mantém um índice com informações dos documentos enviados.

O projeto está publicado na Oracle Cloud Infrastructure (OCI) e pode ser acessado pelo navegador.

## Arquitetura da solução

A solução é composta por quatro partes principais:

- **Interface web:** local onde o usuário envia documentos e realiza consultas.
- **Aplicação FastAPI:** recebe as solicitações, processa arquivos e devolve as respostas.
- **API da OpenAI:** auxilia na análise e interpretação do conteúdo textual.
- **Servidor OCI com Nginx:** mantém a aplicação disponível pela internet.

Fluxo básico:

1. O usuário envia um documento pela interface.
2. A aplicação lê e extrai o conteúdo do arquivo.
3. As informações são organizadas no índice documental.
4. A API da OpenAI apoia a análise quando necessário.
5. O sistema apresenta a resposta ou os dados encontrados ao usuário.

## Tecnologias e ferramentas

- Python
- FastAPI
- Uvicorn
- OpenAI API
- PyPDF
- python-docx
- python-dotenv
- Nginx
- Oracle Cloud Infrastructure (OCI)
- Git e GitHub
- Visual Studio Code

## Como executar o projeto localmente

Clone o repositório:

```bash
git clone URL_DO_SEU_REPOSITORIO
cd assistente-documentos
```

Crie e ative o ambiente virtual:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

Instale as dependências:

```bash
pip install fastapi "uvicorn[standard]" openai pypdf python-docx python-dotenv python-multipart
```

Crie o arquivo `.env.local` e informe sua chave:

```text
OPENAI_API_KEY=sua_chave_aqui
```

Inicie a aplicação:

```bash
uvicorn main:app --host 127.0.0.1 --port 8000
```

Abra no navegador:

```text
http://127.0.0.1:8000
```

## Como atualizar a versão publicada na OCI

Depois de enviar as mudanças ao GitHub, conecte-se à máquina OCI e execute:

```bash
cd /home/ubuntu/assistente-documentos
git pull origin main
sudo systemctl restart assistente-documentos
```

## Exemplos de perguntas que o assistente pode responder

- Quais documentos foram processados?
- Resuma o conteúdo deste documento.
- Existem documentos relacionados a uma empresa específica?
- Quais arquivos contêm determinada palavra ou assunto?
- Quais documentos precisam de revisão?
- Quais informações principais aparecem neste arquivo?

## Exemplos de respostas geradas

**Pergunta:** Quais documentos foram processados?

**Resposta:** Foram identificados documentos PDF e DOCX no sistema. Os arquivos disponíveis podem ser consultados pela interface.

**Pergunta:** Resuma este documento.

**Resposta:** O documento apresenta as informações principais do arquivo, incluindo tema, dados relevantes e pontos que exigem atenção.

**Pergunta:** Existem documentos relacionados à empresa XYZ?

**Resposta:** Foram encontrados documentos com referências à empresa XYZ. A consulta pode indicar os arquivos e os trechos relacionados.

## Segurança

Informações sensíveis não devem ser enviadas ao repositório:

- Chave da API da OpenAI
- Arquivo `.env.local`
- Arquivos enviados pelos usuários
- Índices gerados localmente
- Ambiente virtual `.venv`

Esses itens estão protegidos pelo arquivo `.gitignore`.

## Status do projeto

O Assistente de Documentos está publicado na OCI, integrado à API da OpenAI e versionado em repositório privado no GitHub.