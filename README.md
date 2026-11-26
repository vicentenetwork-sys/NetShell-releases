<p align="center">
  <img src="imagens/banner.png" alt="NetShell: terminal e gerenciador de conexões para engenheiros de rede, no Windows" width="100%">
</p>

<p align="center">
  <a href="../../releases/latest"><img src="https://img.shields.io/github/v/release/vicentenetwork-sys/NetShell-releases?label=vers%C3%A3o&color=0078d4&labelColor=202020" alt="Versão"></a>
  <img src="https://img.shields.io/badge/Windows-10%20%7C%2011%20(x64)-202020?labelColor=1c1c1c" alt="Windows 10 e 11 (x64)">
  <img src="https://img.shields.io/badge/SSH%20%C2%B7%20Telnet%20%C2%B7%20Serial%20%C2%B7%20RDP-202020?labelColor=1c1c1c" alt="SSH, Telnet, serial e RDP">
  <img src="https://img.shields.io/badge/senhas-protegidas%20(DPAPI)-0078d4?labelColor=1c1c1c" alt="Senhas protegidas pelo Windows">
  <img src="https://img.shields.io/badge/interface-ingl%C3%AAs-202020?labelColor=1c1c1c" alt="Interface em inglês">
</p>

<p align="center">
  <a href="../../releases/latest"><b>⬇️ Baixar a versão mais nova</b></a> ·
  <a href="#funcionalidades">Funcionalidades</a> ·
  <a href="#instalar">Instalar</a> ·
  <a href="#segurança-e-atualizações">Segurança</a>
</p>

O **NetShell** é um terminal e gerenciador de conexões para **engenheiros de rede** no Windows. Num só lugar você organiza
centenas de equipamentos em pastas e cofres, abre sessões SSH, Telnet, serial e RDP em abas, transfere arquivos e roda
comandos em muitos equipamentos de uma vez, com relatórios prontos. O layout e os termos seguem o Devolutions RDM e o
VanDyke SecureCRT, então quem vem deles se sente em casa.

<table>
  <tr>
    <td width="33%" valign="top">
      <h3>🗂️ Organizado</h3>
      Equipamentos em pastas e cofres, com herança de credenciais, proxies e opções de terminal. Importa do SecureCRT, PuTTY, RDM e planilhas CSV.
    </td>
    <td width="33%" valign="top">
      <h3>⚡ Automatizado</h3>
      Execução em massa (Bulk Execution), macros, templates de configuração com Jinja2 e relatórios em Markdown que viram PDF, sem abrir uma sessão por vez.
    </td>
    <td width="33%" valign="top">
      <h3>🔒 Seu</h3>
      Roda no seu PC, sem nuvem e sem conta. Os dados ficam num arquivo local, as senhas protegidas pelo Windows, e há versão portable para pendrive.
    </td>
  </tr>
</table>

## Funcionalidades

| Recurso | O que faz |
|---|---|
| 🖥️ **Sessões em abas** | SSH, Telnet, serial (COM), TCP bruto, shell local (cmd/PowerShell) e SSH externo (plink) para algoritmos antigos. Abas soltas, divididas, em janelas separadas e em **grupos de abas** coloridos. |
| 🧭 **Cofres e pastas** | Vários cofres (por cliente) e um cofre compartilhado; pastas com herança de credenciais, proxies, opções de terminal e variáveis; regras de sessão por nome, endereço ou tipo de equipamento. |
| 🔀 **Proxies e jump hosts** | SOCKS4/5, HTTP CONNECT e saltos SSH em qualquer ordem, também para RDP, sites e transferências, com relay local só no loopback. |
| 🪟 **RDP e sites embutidos** | Área de trabalho remota dentro de uma aba, com ajuste automático de tamanho; páginas web de equipamentos numa aba (WebView2), pelo proxy do equipamento. |
| 📁 **Transferência de arquivos** | SFTP, SCP, FTP/FTPS e TFTP com fila, retomada e conflitos; envio e download em lote para muitos equipamentos. |
| 🚀 **Execução em massa** | Os mesmos comandos em dezenas de equipamentos em paralelo, saída limpa por equipamento, histórico, exportação e coleta de fatos (modelo, versão). |
| ⌨️ **Macros e broadcast** | Macros com entradas `[[Nome]]` e atalhos, comandos após o login, digitação sincronizada em várias abas e repetidor de comandos que destaca o que mudou. |
| 📊 **Relatórios e templates** | Relatórios em Markdown com blocos de comandos por equipamento (tabelas, filtros, campos) e exportação em PDF; templates de configuração Jinja2 com variáveis YAML/JSON. |
| 🔎 **Terminal completo** | Emulação xterm, histórico de 50.000 linhas, busca, destaque de palavras-chave (listas do SecureCRT), links para equipamentos citados na saída e colagem segura. |
| 📜 **Logs e histórico** | Logs de sessão com senhas apagadas, histórico pesquisável, comparação de logs lado a lado e a atividade de cada equipamento no Dashboard. |
| 🧰 **Ferramentas de rede** | Calculadora de IP, kit SSL (certificados e cadeias), varredura de rede para cadastrar vários equipamentos de uma vez. |
| 🎨 **Aparência** | Tema escuro nos cinzas do Windows, claro e alto contraste; oito cores de destaque; escala da interface. |

## Instalar

### 💻 Com instalador (Windows 10 ou 11, 64 bits)

1. Abra a [versão mais nova](../../releases/latest) e baixe `NetShell-Setup-<versão>.exe`.
2. Execute. O NetShell é instalado só para o seu usuário (sem pedir administrador) e aparece no menu Iniciar.

### 🎒 Portable (sem instalar)

1. Baixe `NetShell-<versão>-win-x64-portable.zip`, abra as **Propriedades** do arquivo e marque **Desbloquear**.
2. Extraia numa pasta sua (Documentos, outra unidade ou pendrive) e abra `NetShell.exe` dentro de `NetShell-win-x64-self-contained`.
3. Os dados ficam na pasta `Data` ao lado do programa: apagar a pasta remove tudo.

> O executável ainda não tem assinatura de código. Se o Windows mostrar "O Windows protegeu o computador", clique em **Mais informações › Executar assim mesmo**.

## Segurança e atualizações

- **Senhas protegidas:** senhas, chaves privadas e frases-senha são cifradas com o DPAPI do Windows, presas ao seu usuário. Os logs de sessão apagam o que você digita como senha, e o export pode ser cifrado com senha. Opcionalmente, o Windows Hello é pedido antes de mostrar, copiar ou exportar uma senha.
- **Atualização com um clique:** em **Help › About › Check for Updates** o NetShell avisa quando há versão nova, baixa, confere o **SHA-256** (do GitHub e do `SHA256SUMS.txt`) e reinicia sozinho. Isso vale também para a **versão portable**: os arquivos do programa são trocados e, se a versão nova não subir, a pasta volta sozinha para a anterior. As pastas `Data` e `Logs` nunca são tocadas.
- **Backups:** backup diário automático do arquivo de dados, e um backup antes de cada importação e de cada atualização do arquivo.
- **Conferência manual:** cada versão traz `SHA256SUMS.txt` com o SHA-256 de todos os arquivos. Veja [todas as versões](../../releases).

---

<sub>Este repositório tem só as versões publicadas; o código-fonte não é público. © vicentenetwork-sys. Todos os direitos reservados.</sub>
