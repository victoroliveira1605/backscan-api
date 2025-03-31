
# BackScan API

Projeto que coleta e envia a localização do usuário via GPS ou IP diretamente para o Telegram.

## 🚀 Funcionalidade

Quando o usuário acessa a página, o site solicita permissão para obter sua localização via GPS.
Caso ele negue, o sistema tenta obter a localização aproximada via IP.

A localização é enviada automaticamente para o bot do Telegram configurado.

---

## 🗂️ Estrutura do Projeto

```
backscan-api/
├── api
│   └── send-location.js          # Função serverless responsável pelo envio para o Telegram
├── public
│   ├── index.html                # Página que coleta a localização
│   └── styles.css                # Estilos da página
├── package.json                  # Dependências do projeto
├── package-lock.json             # Controle de versão das dependências
└── README.md                     # Este arquivo
```

---

## 📄 Configuração

### 1. Crie um Bot no Telegram
- Acesse o [@BotFather](https://t.me/BotFather) e crie um novo bot.
- Anote o **Token do Bot**.
- Envie qualquer mensagem para o bot ou adicione ele em um grupo.
- Para descobrir o **chat_id**, acesse:
  ```
  https://api.telegram.org/botSEU_BOT_TOKEN/getUpdates
  ```

### 2. Configure as Variáveis na Vercel

No painel do projeto → Settings → Environment Variables:

| Nome                | Valor                     |
|--------------------|---------------------------|
| TELEGRAM_BOT_TOKEN | Seu token do bot Telegram |
| TELEGRAM_CHAT_ID  | ID do chat ou grupo       |

---

## 🖥️ Como rodar localmente

```bash
git clone https://github.com/esojs/backscan-api.git
cd backscan-api
npm install
npm run dev
```
Acesse: [http://localhost:3000](http://localhost:3000)

---

## ☁️ Como fazer Deploy na Vercel

1. Crie um repositório público no GitHub.
2. Suba os arquivos do projeto.
3. Na Vercel, clique em **New Project → Import Git Repository**.
4. Configure as variáveis de ambiente.
5. Clique em **Deploy**.

---

## 🔒 Observação

O projeto busca localização via GPS **somente se o usuário permitir**.
Caso ele negue, o sistema tentará capturar a localização aproximada via IP.

---

## 📌 Licença

Este projeto é livre para fins de estudo e aprendizado.
