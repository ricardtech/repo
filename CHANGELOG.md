# 📋 Registro de Alterações (Changelog) — Repositório Oficial RicardTech

Todas as alterações notáveis, adições de pacotes, atualizações e correções no repositório de pacotes Linux da **RicardTech** (`repo.ricardtv.top`) serão documentadas neste arquivo.

O formato é baseado nas diretrizes de [Keep a Changelog](https://keepachangelog.com/pt-BR/1.1.0/) e segue as convenções de [Conventional Commits](https://www.conventionalcommits.org/pt-br/v1.0.0/).

---

## [2026-11-20] - Adição do Ricard Hub Desktop (v2.4.4-1)

### 🚀 Adicionado
- **Novo Pacote no Repositório (v2.4.4-1):** `ricardhub-desktop-2.4.4-1-x86_64.pkg.tar.zst` adicionado à árvore `x86_64/`.
  - Cliente e navegador nativo ultraleve em **Rust** e **WebKitGTK / Wry** dedicado para a Central Operacional **Ricard Hub** (`https://hub.ricardtech.top`).
  - **Eficiência Extrema:** Executável leve (~480 KB) e consumo reduzido de memória RAM (40 MB a 60 MB), substituindo navegadores pesados.
  - **Bypass de iFrames e Resolução de Cookies:** Implementação de `CookieAcceptPolicy::Always`, permitindo navegação sem loops em iframes (Dokploy, Aptabase, Omni Gestor).
  - **Integração Desktop:** Arquivo `.desktop` registrado no menu de aplicativos, ícones hicolor e persistência de sessão e cookies em `~/.config/ricardhub-desktop/`.
- **Indexação na Base de Dados ALPM:** Execução do `repo-add` para atualizar `playmax.db.tar.gz` e `playmax.files.tar.gz` contendo as entradas do `ricardhub-desktop`.
- **Compatibilidade Multi-Mirror:** Bancos binários preservados como arquivos regulares para suporte idêntico no GitHub Pages (`repo.ricardtv.top`) e Forgejo (`git.ricardtech.top`).

---

## [2026-11-17] - Menu Lateral Telegram Desktop, Modo Noturno e Preferências Expandidas (v0.1.0-4)

### 🚀 Adicionado
- **Menu Lateral Oficial Estilo Telegram Desktop:**
  - Adicionados atalhos rápidos para **Contas / Alternar Sessão**, **Chats Arquivados**, **Contatos** e **Mensagens Salvas** (seleção direta do chat privado pessoal).
  - Interruptor rápido de **Alternar Modo Noturno** com persistência nas configurações do Libadwaita (`adw::StyleManager`).
- **Janela de Preferências Expandida (5 Páginas):**
  - **Geral:** Esquema de cores (Seguir sistema / Tema escuro) e comportamento de chat (Enviar com Enter / Quebra com Shift+Enter).
  - **Notificações:** Controles para chats privados, grupos e canais.
  - **Privacidade & Segurança:** Atalho para gerenciar sessões ativas de outros dispositivos e aviso de 2FA.
  - **Armazenamento:** Indicador de tamanho de cache em tempo real e botão com estilo destacado para limpeza de cache.
  - **Idioma:** Exibição com badge de seleção de Português (Brasil).
- **Novo Pacote no Repositório (v0.1.0-4):** `paperplane-next-0.1.0-4-x86_64.pkg.tar.zst` na árvore `x86_64/` com binário Rust compilado com LTO (*Link-Time Optimization*).

---

## [2026-11-17] - Adição do PaperPlane Next e Correção de Inicialização (v0.1.0-3)

### 🐛 Corrigido
- **Correção Crítica no Template GTK4 (`chat_history.ui`):** Removida propriedade não-padrão `reversed` do `GtkListView`, que causava encerramento abrupto (crash) logo após a autenticação bem-sucedida ao carregar a tela principal de conversas.

### 🚀 Adicionado
- **Novo Pacote no Repositório (v0.1.0-3):** `paperplane-next-0.1.0-3-x86_64.pkg.tar.zst` adicionado à árvore `x86_64/`.
  - Cliente nativo do Telegram construído em **Rust**, **GTK4** e **Libadwaita**, revivido e mantido ativamente pela comunidade RicardTech.
  - **Empacotamento 100% Autocontido:** Bibliotecas essenciais `libtdjson.so.1.8.19` (TDLib do Telegram) e `librlottie.so.0` (suporte a animações e stickers Lottie) embutidas nativamente em `/usr/lib/`, eliminando qualquer necessidade de compilação demorada pelo AUR.
  - Suporte completo a traduções em Português do Brasil (PT-BR).
  - Inclui binário otimizado, arquivos `.desktop`, ícones hicolor e serviço de integração com notificações do sistema.
- **Indexação na Base de Dados:** Execução do `repo-add` para atualizar os bancos `playmax.db.tar.gz` e `playmax.files.tar.gz` contendo as entradas do `paperplane-next`.
- **Documentação Oficial em PT-BR:**
  - `README.md` reestruturado com tabelas comparativas, instruções completas para instalação direta via `pacman` e download avulso.
  - `CHANGELOG.md` em Português Brasileiro registrando todo o histórico do repositório.
  - `LICENSE` em Português Brasileiro definindo as regras de distribuição e software livre.

### 🔄 Modificado
- **Redundância Git (Dual-Push):** Configuração obrigatória de espelhamento com envio simultâneo para o GitHub (`https://github.com/ricardtech/repo.git`) e GitLab (`https://gitlab.com/ricard-tech/repo.git`).

---

## [2026-10-18] - Atualização do RP - Play Max Linux v2.5.1

### 🚀 Adicionado
- Pacotes binários atualizados da versão **v2.5.1**:
  - `x86_64/rp-play-max-linux-2.5.1.pkg.tar.xz` (para distribuições baseadas em Arch Linux).
  - `x86_64/rp-play-max-linux_2.5.1_amd64.deb` (para distribuições Debian/Ubuntu).

### ⚡ Melhorado
- Atualização do portal web estático desenvolvido em **Astro**, facilitando a navegação entre abas de distribuições e links rápidos de download.

---

## [2026-09-14] - Lançamento Inicial do Repositório (repo.ricardtv.top)

### 🚀 Adicionado
- Criação da infraestrutura do repositório com suporte a pacotes Arch Linux (ALPM).
- Configuração do domínio personalizado `repo.ricardtv.top` com Cloudflare Pages e DNS seguro.
- Primeiro pacote publicado: `rp-play-max-linux-2.2.2`.
- Geração da base de dados inicial `playmax.db.tar.gz`.

---

© 2026 **RicardTech** • Todos os direitos reservados.
