# DuckDuckGo Chat CLI (duck)

Este script (`duck`) é uma ferramenta de linha de comando para interagir com a API de Chat do DuckDuckGo diretamente do seu terminal. Ele permite enviar mensagens e receber respostas de vários modelos de IA suportados pelo DuckDuckGo.

## 📋 Descrição

O script envia suas mensagens para a API do DuckDuckGo Chat, recupera a resposta e a exibe no terminal. Ele também mantém um histórico da conversa atual em um arquivo temporário (`/tmp/duck_messages`) e armazena em cache o token VQD necessário para a comunicação com a API (`/tmp/duckduckgo_vqd`).

## ✨ Funcionalidades

- Interação com a API de Chat do DuckDuckGo.
- Suporte para seleção de diferentes modelos de IA.
- Mantém o histórico da conversa entre execuções (armazenado em `/tmp/duck_messages`).
- Armazena em cache o token VQD para otimizar requisições (`/tmp/duckduckgo_vqd`).
- Aceita entrada via argumentos de linha de comando ou via pipe (`stdin`).

## ⚙️ Pré-requisitos

- **Bash:** O script é escrito em Bash.
- **curl:** Usado para fazer requisições HTTP para a API.
- **jq:** Usado para processar dados JSON da API e formatar payloads.

## 🛠️ Como Usar

Execute o script passando sua mensagem como argumento:

```bash
duck "Qual a capital da França?"
```
