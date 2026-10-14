# KIVORA SOFT — Guia de Compilação e Distribuição para macOS (Apple Mac)
> Certificado AGT n.º FE/387/AGT/2026 | Tauri v2 Multiplataforma

O **KIVORA SOFT** possui compatibilidade nativa completa com o ecossistema Apple macOS (chips **Apple Silicon M1/M2/M3/M4** e computadores **Intel Mac**).

---

## 🍏 Características da Versão macOS:
1. **Tamanho Super Reduzido (~18 MB a 22 MB):** O macOS já inclui o motor **WebKit (WKWebView)** de fábrica, eliminando a necessidade de instaladores pesados com runtimes embutidos.
2. **Formato Padrão Apple:** Produz o ficheiro `.dmg` (imagem de disco oficial com arrastar e soltar para a pasta *Aplicações*) e o pacote `.app`.
3. **Hardware ID Imutável:** A ativação de licença no Mac utiliza o identificador de placa-mãe `IOPlatformUUID` via `ioreg`.
4. **Base de Dados Offline-First:** Persistência idêntica em `~/Library/Application Support/com.kivora.erp/`.

---

## 🚀 Método 1: Geração Automática na Nuvem via GitHub Actions (Recomendado)
*Não precisa de ter um computador Mac! O GitHub compila num servidor Mac real da Apple na nuvem gratuitamente.*

1. Faça push das alterações para o repositório GitHub:
   ```bash
   git add .
   git commit -m "feat(macos): suporte a build nativo macOS e workflow CI/CD"
   git push origin main
   ```
2. Abra o repositório no GitHub pelo navegador.
3. Clique na aba **"Actions"** no menu superior.
4. No menu lateral esquerdo, clique no workflow: **`Build KIVORA SOFT macOS (.dmg)`**.
5. Clique no botão **"Run workflow"** à direita.
6. Escolha a arquitetura desejada:
   - **universal** (Recomendado: funciona em todos os Macs M1/M2/M3/M4 e Intel).
   - **aarch64** (Específico para Apple Silicon).
   - **x86_64** (Específico para Intel).
7. Aguarde ~4 minutos.
8. Ao concluir, faça o download do artefacto gerado: **`KIVORA-SOFT-macOS-Installer.zip`** que contém o ficheiro `.dmg` pronto para instalar e usar em qualquer Mac!

---

## 💻 Método 2: Compilação Direta num Computador Mac Físico

Se você ou alguém da sua equipa tiver um Mac (MacBook, Mac Mini ou iMac):

1. **Pré-requisitos no Mac (caso ainda não tenha):**
   - **Homebrew e Node.js 20+:**
     ```bash
     brew install node
     ```
   - **Rust & Cargo:**
     ```bash
     curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
     source $HOME/.cargo/env
     ```
2. **Clonar e Executar a Compilação:**
   ```bash
   git clone <URL_DO_REPOSITORIO>
   cd angola-agt-cloud-erp-main
   npm install
   npm run build:macos
   ```
3. O ficheiro instalador `.dmg` será gerado automaticamente em:
   - `src-tauri/target/release/bundle/dmg/KIVORA SOFT_1.0.0_aarch64.dmg` (ou `_universal.dmg`)
   - E copiado para a pasta `release-distribution/`.

---

*KIVORA SOFT 2026 — Gestão Empresarial e Faturação Certificada AGT*
