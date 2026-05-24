# ✈️ Caça-passagem LATAM — PWA

Progressive Web App que mostra diariamente os preços em milhas LATAM Pass para a viagem **GRU ↔ Orlando (setembro/2026)**, com volta saindo de SFO ou LAX 30 dias após a ida.

Instalável como app no celular (iOS + Android). Funciona offline (cache).

## 🚀 Deploy no Vercel

### Via GitHub (recomendado — auto-deploy quando o `data.json` atualiza)

1. Faça push deste repositório pro GitHub
2. Acesse https://vercel.com/new
3. Clique em **"Import Git Repository"** e selecione este repo
4. Clique **Deploy** (sem configuração extra — o `vercel.json` já está aqui)
5. Em ~30s o Vercel dá uma URL tipo `https://seu-projeto.vercel.app`

### Via Drag & Drop (sem GitHub)

1. Acesse https://vercel.com/new/upload
2. Arraste essa pasta inteira no navegador
3. Pronto

## 📲 Instalando no celular

**iPhone (Safari):** abre a URL → compartilhar (□↑) → **"Adicionar à Tela de Início"**

**Android (Chrome):** abre a URL → menu (⋮) → **"Adicionar à tela inicial"** (ou clique no banner azul "Instalar")

## 🔄 Como funciona a atualização diária

Uma tarefa agendada no Cowork (`caca-passagem-latam-diaria`) roda todo dia às 09:00 (Brasília):

1. Pesquisa preços diretamente no site da LATAM via browser automation
2. Atualiza o arquivo **`data.json`** desta pasta
3. Faz `git commit` + `git push` automático no repo (configurar separado)
4. Vercel detecta o push e republica em segundos
5. O PWA no celular busca o novo `data.json` quando você abrir o app

> ⚠️ O auto `git push` da tarefa é um setup adicional. Sem ele, você pode rodar `git push` manualmente quando quiser refletir os preços novos no celular.

## 📂 Arquivos

| Arquivo | Função |
|---------|--------|
| `index.html` | Página principal (a UI) |
| `manifest.webmanifest` | Metadata PWA (nome, ícones, cor) |
| `sw.js` | Service Worker (cache offline) |
| `data.json` | **Histórico de preços — atualizado diariamente** |
| `icon-192.png`, `icon-512.png` | Ícones do app |
| `vercel.json` | Config de cache do Vercel |
| `LEIA-ME.md` | Guia completo (PT-BR) |

## 🛠️ Stack

- HTML/CSS/JS puro (sem build step)
- [Chart.js 4](https://www.chartjs.org/) via CDN para o gráfico
- Service Worker pra cache offline
- Web App Manifest pra instalabilidade

## 📜 Licença

Uso pessoal. Dados extraídos do site público da LATAM Airlines.
