# Validação responsiva v6

Objetivo desta revisão: garantir comportamento consistente do Consumo da Vida em desktop, notebook, tablet e smartphones, eliminando sobreposição da barra superior durante a rolagem.

## Correções principais

- Navegação superior passa a permanecer no fluxo normal da página em todas as larguras; não usa `sticky`/`fixed` no desktop nem no mobile.
- Menu mobile abre dentro da própria navegação e empurra o conteúdo para baixo.
- Nova camada final `assets/css/responsive-unified-v6.css` neutraliza regras antigas conflitantes de responsividade.
- Larguras máximas e gutters passam a ser fluidos em telas de 320 px até monitores ultrawide.
- Hero, parceria Instituto Schultz, cards, grids, formulários, gráficos, modais, rodapé e páginas das três ferramentas recebem breakpoints consistentes.
- Reforço de `min-width: 0`, quebra de texto e contenção de mídia para evitar rolagem horizontal acidental.
- Resize/orientation do menu foi reforçado em `assets/js/ui.js`.

## Funcionalidades preservadas

- Calculadora de Vida.
- Planejador de Compras.
- Simulador de Patrimônio.
- IR regressivo do simulador.
- Navegação SPA.
- Tema claro/escuro.
- Histórico local.
- Cadastro de instituição personalizada.
- Integração/parceria Instituto Schultz.

## Debug executado

### Viewports validados

A camada foi exercitada em navegador Chromium com emulação de 320, 360, 390, 430, 768, 900, 1024, 1280, 1366, 1440, 1920 e 2560 px.

Em Home, Calculadora, Planejador e Simulador, o `documentElement.scrollWidth` permaneceu dentro da largura útil em 320, 360, 390, 430, 768, 1024 e 1366 px, inclusive depois de gerar resultados.

### Navegação

- Cabeçalho calculado como `position: relative`, portanto sai da viewport com a rolagem e não cobre o conteúdo.
- Menu mobile abre no fluxo da página e aumenta a altura do cabeçalho; o `main` começa abaixo do menu aberto.
- Toque nos atalhos fecha o menu e ativa a página correta.
- `aria-expanded` alterna entre `true` e `false`.

### Funcionalidades

- Navegação SPA: Home, Calculadora, Planejador e Simulador.
- Calculadora: cenário R$ 5.000 / 200 h / produto R$ 1.000 retornou R$ 25/h, 40 h, 5 dias e 20% da renda.
- Planejador: cenário R$ 5.000 de renda / R$ 2.000 de produto gerou impacto de 40% e quatro cenários de economia.
- Simulador: inicialização, ranking, opções de investimento e IR regressivo validados.
- IR: investimento tributável retorna líquido inferior ao bruto; opção isenta mantém líquido igual ao bruto.
- Tema claro/escuro validado.
- Inclusão de instituição personalizada validada.
- Sintaxe dos 15 JavaScripts validada com Node.js.
- `banks.json` validado.
- Sem IDs HTML duplicados.
- Sem assets locais ausentes.
- Sem referências ao PicPay.

Durante o teste automatizado, as APIs externas foram deliberadamente simuladas como indisponíveis para validar também o fallback interno de bancos/Tesouro sem depender da rede. Não foram observadas exceções JavaScript de runtime no fluxo testado.
