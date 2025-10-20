README - Cadastro de Jurados (Capivari de Baixo)
=============================================

Conteúdo do pacote:
- index.html: Aplicação web completa (HTML + CSS + JS integrados). Usa Bootstrap, jsPDF e SheetJS via CDN.
- manifest.webmanifest: Manifesto PWA para instalação e uso offline.
- service-worker.js: Service Worker para cache offline.
- icons/: Ícones do aplicativo (192 e 512 px).

Como usar:
1) Abra o arquivo index.html no navegador (Chrome/Edge/Firefox). Para pleno uso PWA, hospede em um servidor (por exemplo, usando extensão Live Server no VS Code) e acesse via http://localhost.
2) Tela de Login: informe usuário e senha. Padrão inicial (não exibido na tela):
   - Usuário: escrivao
   - Senha: tjsc2025
   Após entrar, você pode trocar em "Trocar Usuário/Senha".
3) Cadastre jurados no formulário à esquerda. Os campos em maiúsculas são convertidos automaticamente e salvos em maiúsculas.
4) Validações: CPF com máscara e verificação de dígitos; bloqueio de CPF e NOME duplicados; telefone com máscara (XX) XXXXX-XXXX.
5) Último Conselho: ao preencher, a regra automática marca INATIVO/Motivo "12 meses" quando o ano do conselho for o ano anterior (salvo se já houver motivo fixo diferente de "12 meses"). Motivo "Temporário" ativa automaticamente na data informada.
6) Impressão: Selecione o filtro (Ativos/Inativos/Todos) e clique em "Imprimir Lista para Sorteio". A página imprime cartões em A4 (3 colunas x 4 linhas), margens 1cm e espaçamento 1mm, no padrão exigido.
7) Exportações: botões "Exportar PDF" e "Exportar Excel" exportam a lista atual.
8) Backup/Restore: "Backup" baixa um arquivo JSON com os dados. "Restaurar" importa um arquivo de backup.
9) Relatórios: veja Resumo, Por Bairro e Por Profissão na guia de relatórios.

PWA/Offline:
- Com o site servido via HTTP(s), clique no ícone de instalar (do navegador) para adicionar ao dispositivo. O Service Worker faz cache e permite uso offline.

Observações:
- Os cartões de impressão exibem campos em formatação específica (cores/tamanhos/capitalização). Na base de dados os textos ficam em MAIÚSCULAS, conforme exigido.
- Impressão limpa: somente os cartões são mostrados na impressão (outros elementos são ocultados com @media print).
