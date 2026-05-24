# 📱 PWA Caça-passagem LATAM — Guia rápido

Este PWA (Progressive Web App) mostra no seu celular os preços diários em milhas LATAM Pass para a viagem **GRU ↔ Orlando (setembro/2026)**.

---

## 🚀 Como colocar no ar (Vercel)

### Opção A — Drag & Drop (mais rápido, sem conta GitHub)

1. Acesse https://vercel.com/new
2. Faça login (pode usar email, GitHub ou Google)
3. Na página inicial, procure por **"deploy a template"** ou role até o final pra encontrar **"Upload a folder"** (ou use https://vercel.com/new/upload)
4. Arraste a pasta inteira **`pwa-latam`** pra dentro do navegador
5. Em ~30s o Vercel gera uma URL tipo `https://pwa-latam-xxxx.vercel.app`
6. Abra essa URL no celular → vai aparecer "Adicionar à tela inicial" → **vira app!**

### Opção B — Com GitHub (recomendado pra atualização automática)

1. Crie um repositório novo no GitHub (público ou privado)
2. Faça upload dos arquivos desta pasta `pwa-latam` pro repo
3. Em https://vercel.com/new, clique em **"Import Git Repository"**
4. Selecione o repo, clique **Deploy**
5. Pronto! Toda vez que você fizer push no GitHub, o Vercel atualiza o site sozinho.

---

## 🔄 Como funciona a atualização diária

A tarefa agendada **"caca-passagem-latam-diaria"** (configurada no Cowork) roda todo dia às 09:00 e:

1. Pesquisa na LATAM os preços do dia
2. Atualiza o arquivo **`data.json`** nesta pasta
3. O PWA no celular busca esse `data.json` toda vez que você abre o app

**Para que o celular veja os dados novos**, o `data.json` precisa estar publicado no Vercel. Por isso:

### Se usou Opção A (Drag & Drop):
Sempre que quiser ver atualizado, faça um novo drag & drop da pasta no Vercel. ⚠️ Não é automático.

### Se usou Opção B (GitHub) — automatização total:
Configure um script pra dar `git commit` + `git push` automático quando o `data.json` mudar. Posso te ajudar a montar isso depois.

### Solução intermediária (sem GitHub):
Você pode usar **Vercel CLI**:
```bash
npm install -g vercel
cd "C:\Users\Familia\ENCORPEI VIAGENS\ENCORPEI VIAGENS\pwa-latam"
vercel login
vercel --prod
```
A partir daí, basta rodar `vercel --prod` (a tarefa diária pode fazer isso automaticamente se você quiser).

---

## 📲 Instalando no celular

**iPhone (Safari):**
1. Abra a URL do Vercel
2. Toque no botão de compartilhar (□↑)
3. Role e toque em **"Adicionar à Tela de Início"**
4. Toque em **Adicionar**

**Android (Chrome):**
1. Abra a URL do Vercel
2. Toque no menu (⋮) → **"Adicionar à tela inicial"** OU
3. Quando aparecer o banner azul no rodapé do app, toque em **Instalar**

---

## 📂 Arquivos desta pasta

| Arquivo | O que é |
|---------|---------|
| `index.html` | A página principal do PWA |
| `manifest.webmanifest` | Define ícone, cor, nome do app |
| `sw.js` | Service Worker — cache offline |
| `data.json` | **Atualizado todo dia pela tarefa agendada** |
| `icon-192.png` | Ícone (uso em Android, favicon) |
| `icon-512.png` | Ícone grande (splash screen) |
| `LEIA-ME.md` | Este arquivo |

---

## ❓ Dúvidas comuns

**"O app não tá atualizando no celular"**
→ O Service Worker faz cache agressivo. Force atualização: feche o app, abra de novo, ou clique no botão **"↻ Atualizar agora"** no topo.

**"Onde vejo se a tarefa diária tá rodando?"**
→ No Cowork, vá na barra lateral em **"Scheduled"**. Lá tem a tarefa `caca-passagem-latam-diaria`.

**"Quero adicionar mais datas/destinos"**
→ Me peça pra editar a tarefa agendada. Posso ajustar os parâmetros.

**"O Vercel cobra alguma coisa?"**
→ Não pra esse uso. O plano Hobby (free) cobre PWAs estáticos com largura folgada.
