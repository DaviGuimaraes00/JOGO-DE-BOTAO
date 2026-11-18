# ⚽ Mini Soccer

Jogo de futebol multiplayer em tempo real no navegador, desenvolvido com **Vite**, **JavaScript** e **Supabase Realtime**. A arquitetura utiliza modelo autoritativo no cliente do host (onde roda a física e simulação da partida), enquanto os demais jogadores enviam inputs e recebem o estado sincronizado em tempo real.

<p align="left">
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" />
  <img src="https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white" />
  <img src="https://img.shields.io/badge/Supabase-3ECF8E?style=for-the-badge&logo=supabase&logoColor=white" />
  <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" />
</p>

## ✨ Funcionalidades
- **Multiplayer em tempo real:** Criação de lobbies e partidas sincronizadas via Supabase Realtime.
- **Substituição inteligente por Bots:** Caso um jogador desconecte durante a partida, um bot assume automaticamente seu lugar (`Bot (nome)`) para não interromper o jogo.
- **Sistema de Ranking e Autenticação:** Persistência de pontuação e login de jogadores integrados ao banco PostgreSQL do Supabase.
- **Testes Automatizados e CI/CD:** Suíte de testes da simulação executada automaticamente via GitHub Actions e deploy contínuo com Docker.

---

## 🛠️ Pré-requisitos
- **Node.js >= 22** (exigido pela versão atual do `@supabase/supabase-js`)
- Conta e projeto criados no [Supabase](https://supabase.com/)

---

## 🗄️ Configuração do Banco (Supabase)
1. **Projeto novo:** Execute o script `supabase/schema.sql` no **SQL Editor** do Supabase.
   - *Caso já tenha executado uma versão anterior do `schema.sql`, rode `update-v2.sql` e em seguida `update-v3.sql` para atualizar a estrutura e criar o ranking.*
2. Em **Authentication > URL Configuration**, adicione a URL pública da aplicação (ex.: `https://app.<SEU_IP>.nip.io`) nos campos **Site URL** e **Redirect URLs**.

---

## 🚀 Rodando Localmente

```bash
# 1. Clone o repositório
git clone [https://github.com/SEU-USUARIO/SEU-REPOSITORIO.git](https://github.com/SEU-USUARIO/SEU-REPOSITORIO.git)
cd SEU-REPOSITORIO

# 2. Configure as variáveis de ambiente (preencha URL e Anon Key do Supabase)
cp .env.example .env

# 3. Instale as dependências e inicie o servidor
npm install
npm run dev

# 4. Para rodar os testes da simulação
npm test
