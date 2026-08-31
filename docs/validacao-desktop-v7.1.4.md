# Consumo da Vida — validação desktop v7.1.4

## Objetivo
Refinar exclusivamente a experiência em notebook e desktop, preservando o comportamento mobile aprovado na v7.1.3.

## Ajustes realizados
- Header reequilibrado em uma malha central de até 1480 px.
- Marca do Consumo da Vida reorganizada no desktop para leitura mais clara.
- Navegação centralizada e dimensionada com melhor proporção.
- Hero alinhado à esquerda, com hierarquia editorial e escala tipográfica mais corporativa.
- Painel visual do hero redimensionado para equilibrar texto e conteúdo.
- Conteúdo desktop passou a responder de forma fluida entre notebooks, Full HD e telas ultrawide.
- Cards de ferramentas, parceria, dashboard e Método QDP receberam ritmo e espaçamento consistentes.
- Seção da parceria recebeu melhor distribuição de logo, texto e CTA em desktop.
- Páginas Calculadora, Planejador e Simulador receberam largura e escala próprias para desktop.
- Footer alinhado à mesma malha do conteúdo e marca "Consumo da Vida" exibida integralmente.
- Nenhuma regra nova desta versão é aplicada abaixo de 901 px.

## Larguras verificadas
901, 1024, 1180, 1366, 1440, 1600, 1920 e 2560 px.

Em todas as larguras acima:
- scrollWidth == clientWidth;
- nenhum overflow horizontal detectado;
- barra superior com `position: relative`;
- conteúdo centralizado e limitado a uma malha responsiva;
- footer ocupa a largura da viewport com conteúdo interno alinhado à malha principal.

Controle mobile também verificado em 390 px, sem overflow e sem alteração das regras de layout mobile.

## Integridade funcional
A v7.1.4 não modifica nenhum arquivo JavaScript.

Comparação com a v7.1.3:
- Arquivo alterado: `index.html` (apenas inclusão da nova folha de estilo).
- Arquivo adicionado: `assets/css/desktop-polish-v7.1.4.css`.
- Arquivos JavaScript alterados: 0.
- 15 arquivos JavaScript validados com `node --check`.
- IDs HTML duplicados: 0.
- Assets locais ausentes referenciados no HTML: 0.

Como a lógica de negócio não foi modificada, Calculadora, Planejador, Simulador, IR regressivo, navegação e demais funções permanecem idênticos à versão funcionalmente validada v7.1.3.
