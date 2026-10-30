# CLOCK

PWA de controle de horas e registro de atividades — 100% local, sem servidor e sem nuvem.

**🔗 Acessar a aplicação: https://hebertwng.github.io/clock/**

## O que é

CLOCK é um aplicativo web (PWA) para cronometrar atividades do dia a dia, organizar por data, acompanhar totais num dashboard com gráficos e exportar relatórios. Todo o processamento acontece no seu navegador; não há backend, não há chamadas de rede e nenhum dado é enviado a lugar nenhum.

## Principais recursos

- **Cronômetro por atividade** — inicia/pausa com um clique, atalho de teclado (barra de espaço) ou pelo botão de play/pause fixo na tela.
- **Calendário e navegação por dia**, com virada automática de atividades não concluídas para o dia seguinte.
- **Conclusão em cadeia** — marcar uma atividade como concluída propaga o status para os cards anteriores que a originaram.
- **Dashboard** com gráficos de horas/atividades por período, detalhamento por atividade, exportação em CSV e impressão.
- **Armazenamento local em camadas**:
  - **IndexedDB** como fonte da verdade (transacional, resistente a quedas de energia/desligamentos abruptos).
  - **Arquivo JSON vinculado** (via File System Access API) como espelho/backup legível e portátil, com um segundo arquivo de backup automático.
  - Recuperação assistida caso o arquivo principal seja corrompido.
- **Idiomas** — Português (Brasil) e Inglês, com seletor no canto superior direito.
- **Instalável como PWA** (funciona offline, ícone na tela inicial).

## Como usar

### Direto pelo GitHub Pages
Acesse a página publicada (veja a seção abaixo) — nenhuma instalação necessária.

### Localmente
Basta abrir `index.html` no Chrome ou Edge (navegadores com suporte à File System Access API). Em navegadores sem esse suporte, o app funciona em modo de exportação/importação manual de JSON.

## Privacidade dos dados

Nenhuma informação de atividades ou horas trabalhadas sai do seu dispositivo. Os dados ficam:
1. No **IndexedDB** do navegador (por origem/domínio).
2. Opcionalmente, num **arquivo `.json`** que você escolhe e vincula no seu próprio computador.

O código-fonte deste repositório não contém nem transmite nenhum dado de uso.

## Compatibilidade

- **Vincular arquivo / backup automático**: requer um navegador com File System Access API (Chrome, Edge e derivados Chromium). Veja [caniuse](https://caniuse.com/native-filesystem-api).
- **Demais recursos** (cronômetro, dashboard, IndexedDB, exportar/importar JSON manualmente): funcionam em qualquer navegador moderno.

## Atalhos de teclado

| Tecla | Ação |
|---|---|
| `Espaço` | Pausa a atividade em andamento, ou retoma a última pausada |
| `+` | Abre o modal de nova atividade |
| `←` / `→` | Navega entre os dias |
| `Esc` | Fecha modais abertos |
