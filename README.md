# 🚀 Repositório Oficial Linux — RicardTech (repo.ricardtv.top)

[![Versão](https://img.shields.io/badge/Versão-v2.6.0-blue.svg)](CHANGELOG.md)
[![GitHub](https://img.shields.io/badge/GitHub-ricardtech%2Frepo-181717?logo=github)](https://github.com/ricardtech/repo)
[![GitLab](https://img.shields.io/badge/GitLab-ricard--tech%2Frepo-FC6D26?logo=gitlab)](https://gitlab.com/ricard-tech/repo)
[![Forgejo](https://img.shields.io/badge/Forgejo-RicardTech%2Frepo-orange?logo=forgejo)](https://git.ricardtech.top/RicardTech/repo)
[![Licença](https://img.shields.io/badge/Licença-GPL--3.0-blue.svg)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Ativo-success.svg)](https://repo.ricardtv.top)

Repositório oficial de pacotes binários pré-compilados e instaladores para distribuições **Linux (Arch Linux, Manjaro, BigLinux, EndeavourOS, Debian, Ubuntu e derivados)**, mantido pela organização **RicardTech**.

🌐 **Acesse o portal oficial do repositório:** [https://repo.ricardtv.top](https://repo.ricardtv.top)

---

## 📦 Pacotes Disponíveis no Repositório

| Pacote | Versão Atual | Descrição | Arquitetura |
| :--- | :--- | :--- | :--- |
| **`ricardhub-desktop`** | `2.4.4-1` | Cliente e navegador desktop nativo ultraleve em **Rust** e **WebKitGTK** dedicado para a Central Operacional Ricard Hub (`https://hub.ricardtech.top`). | `x86_64` |
| **`rp-play-max-linux`** | `2.5.1` | Player multimídia de alta performance para reprodução de streaming, canais ao vivo, filmes e séries. | `x86_64` / `amd64` |

---

## ⚡ 1. Instalação no Arch Linux, Manjaro, BigLinux e Derivados

Com o repositório adicionado ao seu `/etc/pacman.conf`, todos os pacotes são instalados e atualizados automaticamente pelo gerenciador de pacotes nativo (`pacman`, `pamac` ou `yay`), sem necessidade de compilar localmente.

### Forma Rápida (1 Comando no Terminal)

Adicione o repositório oficial da RicardTech com redundância (GitHub Pages CDN + Espelho Forgejo) e atualize as listas:

```bash
echo -e "\n[playmax]\nSigLevel = Optional TrustAll\nServer = https://repo.ricardtv.top/\$arch\nServer = https://git.ricardtech.top/RicardTech/repo/raw/branch/main/\$arch" | sudo tee -a /etc/pacman.conf && sudo pacman -Sy
```

### Instalação dos Aplicativos

Após adicionar o repositório, instale diretamente via terminal:

- **Para instalar o Ricard Hub Desktop (Rust / WebKitGTK):**
  ```bash
  sudo pacman -S ricardhub-desktop
  ```

- **Para instalar o RP - Play Max:**
  ```bash
  sudo pacman -S rp-play-max-linux
  ```

---

### Configuração Manual (Passo a Passo)

Caso prefira editar manualmente:

1. Abra o arquivo `/etc/pacman.conf` no editor com privilégios de administrador:
   ```bash
   sudo nano /etc/pacman.conf
   ```
2. Adicione as seguintes linhas ao final do arquivo:
   ```ini
   [playmax]
   SigLevel = Optional TrustAll
   Server = https://repo.ricardtv.top/$arch
   Server = https://git.ricardtech.top/RicardTech/repo/raw/branch/main/$arch
   ```
3. Salve o arquivo (`Ctrl + O`, `Enter` e `Ctrl + X`).
4. Atualize a base de dados:
   ```bash
   sudo pacman -Sy
   ```

---

## 🛍️ 2. Instalação via Interface Gráfica (Big Store, Pamac ou Octopi)

1. Adicione o repositório conforme as instruções acima.
2. Abra a central de aplicativos do seu sistema (**Big Store**, **Adicionar/Remover Programas (Pamac)** ou **Octopi**).
3. Busque por **`ricardhub-desktop`** ou **`Play Max`**.
4. Clique em **Instalar** ou **Aplicar**.
5. As atualizações subsequentes serão oferecidas normalmente junto com as atualizações do sistema operacional.

---

## 📥 3. Downloads Diretos de Binários (`x86_64`)

Se preferir realizar o download avulso dos pacotes ou utilizar distribuições baseadas em Debian/Ubuntu:

| Aplicativo | Formato | Compatibilidade | Download Direto |
| :--- | :--- | :--- | :--- |
| **Ricard Hub Desktop** | `.pkg.tar.zst` | Arch Linux, Manjaro, BigLinux | [Baixar v2.4.4-1](https://repo.ricardtv.top/x86_64/ricardhub-desktop-2.4.4-1-x86_64.pkg.tar.zst) |
| **RP - Play Max** | `.pkg.tar.xz` | Arch Linux, Manjaro, BigLinux | [Baixar v2.5.1](https://repo.ricardtv.top/x86_64/rp-play-max-linux-2.5.1.pkg.tar.xz) |
| **RP - Play Max** | `.deb` | Ubuntu, Debian, Linux Mint, Pop!_OS | [Baixar v2.5.1 .deb](https://repo.ricardtv.top/x86_64/rp-play-max-linux_2.5.1_amd64.deb) |

---

## 🛠️ Manutenção e Administração do Repositório ALPM

Para administradores e mantenedores que atualizam os pacotes da base de dados:

1. Coloque o novo pacote pré-compilado dentro da pasta `x86_64/`:
   ```bash
   cd x86_64
   ```
2. Atualize o banco de dados do repositório Pacman (`playmax.db`):
   ```bash
   repo-add -n -R playmax.db.tar.gz ricardhub-desktop-2.4.4-1-x86_64.pkg.tar.zst
   # Garanta a cópia regular para compatibilidade com mirrors estáticos
   rm -f playmax.db playmax.files
   cp -f playmax.db.tar.gz playmax.db
   cp -f playmax.files.tar.gz playmax.files
   ```
3. Realize o commit e envie via Git com o Triplo-Push simultâneo:
   ```bash
   git add .
   git commit -m "feat: atualizar pacote e base de dados"
   git push origin main
   ```

---

## 🔄 Redundância e Espelhamento Git (Triplo-Push)

Este repositório é publicado simultaneamente sob a organização oficial **RicardTech**:

- **GitHub (Principal / CDN Pages):** [https://github.com/ricardtech/repo](https://github.com/ricardtech/repo)
- **GitLab (Espelho):** [https://gitlab.com/ricard-tech/repo](https://gitlab.com/ricard-tech/repo)
- **Forgejo (Auto-hospedado):** [https://git.ricardtech.top/RicardTech/repo](https://git.ricardtech.top/RicardTech/repo)

---

## 📜 Licença e Termos

Consulte o arquivo [LICENSE](LICENSE) para termos detalhados em Português Brasileiro (PT-BR).

© 2026 **RicardTech** • Todos os direitos reservados.
