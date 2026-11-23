# 📋 Registro de Alterações (Changelog) — Repositório Oficial RicardTech

Todas as alterações notáveis, adições de pacotes, atualizações e correções no repositório de pacotes Linux da **RicardTech** (`repo.ricardtv.top`) serão documentadas neste arquivo.

O formato é baseado nas diretrizes de [Keep a Changelog](https://keepachangelog.com/pt-BR/1.1.0/) e segue as convenções de [Conventional Commits](https://www.conventionalcommits.org/pt-br/v1.0.0/).

---

## [v2.6.1] - 2026-11-23

### 🔄 Atualizado
- **Ricard Hub Desktop (v2.4.6-1):** Atualizado pacote `ricardhub-desktop-2.4.6-1-x86_64.pkg.tar.zst` na árvore `x86_64/`.
  - Correção definitiva de tela em branco em iframes sobrepostos (Dokploy, Dozzle) via aprimoramento de detecção de visibilidade no DOM.
  - Otimização do auto-login para SPAs assíncronas com janela de polling estendida para 30s e suporte a navegação por rotas.
  - Atualizadas as bases de dados oficiais do repositório ALPM (`ricardtech.db` e `playmax.db`).

---

## [v2.6.0] - 2026-11-20

### 🚀 Adicionado
- **Base de Dados Oficial `ricardtech.db`:** Criado banco de dados oficial unificado (`ricardtech.db` e `ricardtech.files`) indexando todos os aplicativos da RicardTech.
- **Ricard Hub Desktop (v2.4.4-1):** Adicionado pacote `ricardhub-desktop-2.4.4-1-x86_64.pkg.tar.zst` na árvore `x86_64/`.
  - Cliente e navegador nativo ultraleve desenvolvido em **Rust** puro com **WebKitGTK / Wry** dedicado para a Central Operacional **Ricard Hub** (`https://hub.ricardtech.top`).
  - **Eficiência Extrema:** Executável leve (~480 KB) e consumo reduzido de memória RAM (40 MB a 60 MB), substituindo navegadores pesados.
  - **Bypass de iFrames e Resolução de Cookies:** Implementação de `CookieAcceptPolicy::Always`, permitindo navegação sem loops em iframes (Dokploy, Aptabase, Omni Gestor).
  - **Integração Desktop:** Arquivo `.desktop` registrado no menu de aplicativos, ícones hicolor e persistência de sessão e cookies em `~/.config/ricardhub-desktop/`.
- **Compatibilidade Retroativa:** Mantida base `playmax.db` e `playmax.files` para não quebrar configurações existentes.
- **Espelho Oficial Forgejo:** Adição documentada do espelho auto-hospedado `https://git.ricardtech.top/RicardTech/repo/raw/branch/main/$arch`.

### 🗑️ Removido
- **Limpeza da Raiz:** Removido arquivo binário `.deb` duplicado na raiz do repositório (mantido em `x86_64/` e anexado nas Releases).
- **PaperPlane Next:** Descontinuação e remoção definitiva do pacote `paperplane-next` do repositório ALPM e de todas as referências na documentação oficial.

---

## [v2.5.1] - 2026-11-19

### 🚀 Adicionado
- **RP - Play Max (v2.5.1):** Adicionado pacote `.deb` para Debian/Ubuntu e derivados (`rp-play-max-linux_2.5.1_amd64.deb`).
- **RP - Play Max (v2.5.1):** Adicionado pacote `.pkg.tar.xz` para Arch Linux / BigLinux / Manjaro (`rp-play-max-linux-2.5.1.pkg.tar.xz`).
- Base de dados inicial `playmax.db` e portal web em Astro.
