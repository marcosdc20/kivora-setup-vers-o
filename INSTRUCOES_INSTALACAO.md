# KIVORA SOFT — Guia Oficial de Instalação, Distribuição e Resolução de Problemas
> Certificado AGT n.º FE/387/AGT/2026 | Decreto Presidencial n.º 71/25 & CIVA (Angola)

Este pacote contém os ficheiros para instalação do **KIVORA SOFT v1.0.0** preparado para máxima estabilidade nos 4 cenários de implantação e imunidade contra falhas de WebView2.

---

## 🛡️ Escolha do Instalador Adequado

| Ficheiro | Tamanho | Cenário de Uso Recomendado |
| :--- | :---: | :--- |
| **`KIVORA SOFT_1.0.0_x64-setup.exe`** | ~16 MB | **Padrão / Online:** Para computadores com acesso à internet ou Windows 10/11 atualizados onde o WebView2 já se encontra pré-instalado. |
| **`KIVORA SOFT_1.0.0_Offline_x64-setup.exe`** | ~230 MB | **100% Offline / Standalone:** Para computadores antigos (Windows 7/8/10), computadores sem internet ou onde haja bloqueios de firewall. Inclui o Microsoft Edge WebView2 completo embutido. |
| **`KIVORA SOFT.exe` / `KIVORA.exe`** | ~34 MB | **Portátil (Pen Drive):** Execução direta sem necessidade de instalação em qualquer computador Windows com WebView2. |

---

## Cenário 1: Instalação em PC Novo (Windows 10 ou Windows 11)
1. Dê um duplo clique no instalador oficial: `KIVORA SOFT_1.0.0_x64-setup.exe` ou `KIVORA SOFT_1.0.0_Offline_x64-setup.exe`.
2. O assistente permite escolher:
   - **Instalar apenas para mim:** Não requer privilégios de Administrador. Instala no perfil do utilizador.
   - **Instalar para todos os utilizadores:** Recomendado para empresas e postos de caixa partilhados.
3. Conclua o assistente. Os atalhos **KIVORA SOFT** serão criados na Área de Trabalho e no Menu Iniciar.

---

## Cenário 2: Instalação em PC Antigo (Windows 7 SP1, Windows 8, Windows 8.1 ou Sem Internet)
O KIVORA SOFT v1.0.0 foi especialmente otimizado para máxima performance e compatibilidade:
- **Resoluções e Monitores:** Otimizado com janela adaptativa para 1366x768 (ou 1280x720) sem cortar botões, barras de ferramentas ou menus.
- **Computadores Sem Internet (Totalmente Offline):**
  - Utilize o instalador **`KIVORA SOFT_1.0.0_Offline_x64-setup.exe`**.
  - O instalador deteta automaticamente se a máquina tem ou não o WebView2 e realiza a instalação autónoma sem necessidade de ligação à internet.
- **Hardware Modesto:**
  - Compilação nativa em Rust com `opt-level = 3` e `lto = "thin"` para menor consumo de memória RAM e CPU.
  - Base de dados SQLite local com índices compostos de alta performance (`t074`).

---

## Cenário 3: PC Novo sem o Kivora (Instalação Virgem / Primeiro Uso)
1. Instale e abra o **KIVORA SOFT**.
2. O sistema deteta automaticamente que é a primeira execução:
   - Inicializa a base de dados SQLite local (`global.db`).
   - Carrega o **Plano de Contas PGC-AO Oficial** (Decreto n.º 82/01 com 220 contas integradas).
   - Configura as séries fiscais para os 21 tipos de documentos certificados pela AGT.
   - Aplica as taxas de imposto angolanas (IVA 14%, 7%, 5%, 0% e Retenção 6,5%).
3. O ecrã de boas-vindas apresentará a escolha entre:
   - **Servidor Principal / Posto Único:** Base de dados SQLite local independente.
   - **Posto Satélite / Terminal de Rede:** Ligação rápida ao IP do servidor central da loja.
4. Conclua o registo inicial da empresa e crie o utilizador Administrador com e-mail de recuperação seguro.

---

## Cenário 4: Atualização por cima de Versão Antiga do Kivora (In-Place Upgrade)
1. Feche o KIVORA SOFT (caso esteja aberto). Mesmo se esquecer aberto, o instalador encerra automaticamente os processos residuais e os processos filhos WebView2 sem erro de ficheiro em uso.
2. Execute o instalador `KIVORA SOFT_1.0.0_x64-setup.exe` ou `KIVORA SOFT_1.0.0_Offline_x64-setup.exe` apontando para a mesma pasta.
3. **Garantia de Segurança de Dados Fiscais:**
   - A base de dados SQLite, as faturas emitidas, os certificados digitais RSA e as configurações de terminal em `%APPDATA%\com.kivora.erp` **NUNCA são eliminados nem sobrescritos**.
   - Ao iniciar, o sistema executa automaticamente as migrações incrementais de esquema e índices de alta performance (`t074`) de forma 100% idempotente.
   - Caso existam dados em pastas legadas (`visualpro-erp`, `KIVORA`), o sistema auto-migra os ficheiros transparentemente.

---

## 🛠️ Resolução do Erro: "Falta de Microsoft Edge WebView2" ou Ecrã em Branco

Em computadores antigos ou com edições do Windows sem o componente Edge WebView2, o aplicativo pode não abrir ou apresentar a mensagem de runtime ausente. Para resolver em definitivo:

1. **Solução Automática (Recomendada):**
   - Execute o instalador **`KIVORA SOFT_1.0.0_Offline_x64-setup.exe`**. Ele instala o runtime Evergreen automaticamente sem internet.
2. **Solução Manual / Técnico de TI:**
   - Na pasta de distribuição, execute diretamente o ficheiro:
     **`MicrosoftEdgeWebView2RuntimeInstallerX64.exe`**
   - Aguarde 30 a 60 segundos até a instalação do runtime concluir.
   - Abra o **KIVORA SOFT**. O sistema arrancará imediatamente com 100% de estabilidade.
3. **Em Windows 7 SP1:**
   - Certifique-se de que o Windows 7 possui a atualização de suporte a assinaturas SHA-2 da Microsoft (KB4474419) aplicada.

---

## Modo Portátil / Execução Direta (Pen Drive / Standalone)
- Copie o ficheiro executável standalone `KIVORA.exe` ou `KIVORA SOFT.exe` diretamente para uma Pen Drive.
- Pode executá-lo diretamente em qualquer computador Windows que possua o WebView2 instalado.

---

*Suporte Técnico Oficial — KIVORA SOFT 2026 (Angola)*
