Coletando informações do workspace```markdown
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

Você também pode enviar texto via pipe:

```bash
cat meu_arquivo.txt | duck "Resuma este texto:"
```

### Selecionando um Modelo

Use a opção `--model` para especificar qual modelo de IA usar. O padrão é `o3-mini`.

```bash
duck --model gpt-4o-mini "Escreva um poema sobre programação."
```

Modelos disponíveis (conforme comentários no script):

- `o3-mini` (padrão)
- `gpt-4o-mini`
- `meta-llama/Llama-3.3-70B-Instruct-Turbo`
- `mistralai/Mistral-Small-24B-Instruct-2501`
- `claude-3-haiku-20240307`

## 📝 Notas

- **Histórico:** O histórico da conversa é armazenado em duck_messages. Para iniciar uma nova conversa, remova este arquivo (`rm /tmp/duck_messages`).
- **Cache VQD:** O token VQD é armazenado em duckduckgo_vqd. Se encontrar problemas de autenticação, tente remover este arquivo para forçar a obtenção de um novo token.
