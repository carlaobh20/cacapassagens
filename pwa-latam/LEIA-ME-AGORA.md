# 🚀 Como aplicar as melhorias (2 minutos)

Carlos, o app foi atualizado com:

✅ Botão **"⚡ Buscar agora"** que roda na nuvem do GitHub (não precisa do seu PC ligado)
✅ Mostra **"🔄 Buscando..."** com cronômetro enquanto roda
✅ Recarrega sozinho quando acaba e te notifica com push no celular
✅ **Gráfico de evolução** dos preços (sempre visível a partir da 2ª busca)
✅ **Mini-tabela de histórico** expansível com as últimas 10 buscas
✅ **3 caixinhas** mostrando Mínimo / Atual / Máximo
✅ Setinha verde/vermelha mostrando se subiu ou caiu vs busca anterior
✅ Destaque **"📉 -X%"** ou **"🔥 mín histórico!"** quando aparece preço bom

---

## ⚠️ ATENÇÃO antes de aplicar

Seu **Token GitHub** atual provavelmente só tem permissão de **Contents**. Pra o botão "Buscar agora" funcionar ele precisa ALSO de permissão **Actions: Read and write**.

### Como atualizar o token (1 min)

1. Abre [github.com/settings/tokens](https://github.com/settings/tokens) (Fine-grained)
2. Clica no token **cacapassagens-pwa** (que você já criou)
3. Em **Repository permissions**, encontra **Actions** → muda pra **Read and write**
4. Clica em **Save**

(Não precisa criar token novo — o que você já tem continua valendo, só ganha mais um poder)

---

## 📤 Como aplicar as mudanças (escolha 1):

### Opção A — Mais fácil (pelo navegador, ~2 min)

1. Abre [github.com/carlaobh20/cacapassagens/blob/main/pwa-latam/index.html](https://github.com/carlaobh20/cacapassagens/blob/main/pwa-latam/index.html)
2. Clica no ícone de **lápis** ✏️ no canto superior direito (Edit this file)
3. Apaga TUDO que tá ali (Ctrl+A → Delete)
4. Abre o arquivo `index.html` da sua pasta `ENCORPEI VIAGENS/pwa-latam/` no Bloco de Notas
5. Copia TUDO (Ctrl+A → Ctrl+C) e cola lá no GitHub (Ctrl+V)
6. Rola pra baixo, clica em **Commit changes...** (botão verde)
7. Confirma **Commit changes**
8. Pronto. Em ~30 segundos o Vercel publica e seu app fica novo

### Opção B — Powershell (mais rápido, ~30s)

1. Abre a pasta `ENCORPEI VIAGENS\pwa-latam` no Explorer
2. Clica com botão direito em `deploy.ps1` → **Executar com PowerShell**
3. Espera ele terminar (vai fazer commit + push automático)

---

## ✅ Depois que aplicar

1. Abre o app no celular (cacapassagens.vercel.app) — **arrasta pra baixo pra forçar refresh**
2. Vai aparecer um botão grande **"⚡ Buscar"** logo abaixo do header
3. Clica nele e espera 1–2 min
4. Vai aparecer "🔄 Buscando preços na LATAM... (45s)" — pode até fechar o app
5. Quando acabar: push no celular + app atualiza sozinho

---

## ❓ Se der erro

- **"Falha ao disparar busca (HTTP 403)"** → token sem permissão de Actions. Volta no passo do token acima.
- **"Configure o token GitHub primeiro"** → vai em ⚙️ → 🔑 Configurar Token e cola o token (mesmo se já tinha colado antes, recola pra garantir).
- **Botão "Buscar" não aparece** → você não fez refresh forte do app. No iPhone: pressiona ↻ na barra do Safari e segura → "Recarregar sem cache".
