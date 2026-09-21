# 🚀 Repositório Oficial Linux — RP Play Max (RicardTech)

Repositório de pacotes e instaladores para o player de streaming **RP - Play Max** no Linux (Desktop & Notebook).

🌐 **Acesse a página oficial do repositório:** [https://repo.rictv.top](https://repo.rictv.top)

---

## 📦 1. Instalação no Arch Linux, Manjaro, BigLinux & Derivados

### Forma Rápida (Terminal)
Adicione o repositório e instale com um único comando no terminal:

```bash
echo -e "\n[playmax]\nSigLevel = Optional TrustAll\nServer = https://repo.rictv.top/\$arch" | sudo tee -a /etc/pacman.conf && sudo pacman -Sy rp-play-max-linux
```

### Forma Manual (Passo a Passo)
1. Abra o arquivo `/etc/pacman.conf` com privilégios de administrador:
   ```bash
   sudo nano /etc/pacman.conf
   ```
2. Adicione as seguintes linhas ao final do arquivo:
   ```ini
   [playmax]
   SigLevel = Optional TrustAll
   Server = https://repo.rictv.top/$arch
   ```
3. Atualize a base de dados do Pacman e instale o pacote:
   ```bash
   sudo pacman -Sy rp-play-max-linux
   ```

---

## 🛍️ 2. Instalação via Interface Gráfica (Pamac / Big Store / Octopi)

Após adicionar o repositório ao `/etc/pacman.conf`:
1. Abra sua central de aplicativos (**Pamac**, **Big Store** ou **Octopi**).
2. Pesquise por **`Play Max`** ou **`rp-play-max-linux`**.
3. Clique em **Instalar**.
4. O sistema cuidará das atualizações automáticas sempre que uma nova versão for lançada.

---

## 📥 3. Downloads Diretos (Versão v2.2.0)

Você também pode baixar os arquivos binários diretamente:

| Formato | Distribuições Compatíveis | Link de Download |
| :--- | :--- | :--- |
| **`.pkg.tar.xz`** | Arch Linux, Manjaro, BigLinux, EndeavourOS | [Baixar .pkg.tar.xz](https://repo.rictv.top/x86_64/rp-play-max-linux-2.2.0.pkg.tar.xz) |
| **`.AppImage`** | Todas as distribuições Linux (Universal Portátil) | [Baixar .AppImage](https://repo.rictv.top/x86_64/RP%20-%20Play%20Max-2.2.0.AppImage) |
| **`.deb`** | Ubuntu, Debian, Linux Mint, Pop!_OS, Zorin OS | [Baixar .deb](https://repo.rictv.top/x86_64/rp-play-max-linux_2.2.0_amd64.deb) |

---

## 🛠️ Manutenção do Repositório (Administração)

Para administradores atualizarem a base de dados do repositório ALPM/Pacman:

```bash
cd x86_64
repo-add -n -R playmax.db.tar.gz rp-play-max-linux-2.2.0.pkg.tar.xz
```

---

© 2026 **RicardTech** • Todos os direitos reservados.
