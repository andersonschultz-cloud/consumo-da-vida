# Validação Desktop + Mobile v7

Data: 2026-08-31

## Objetivo

Garantir comportamento consistente do Consumo da Vida em desktop, notebook, tablet e smartphones, com foco em:

- eliminar sobreposição da barra superior durante a rolagem;
- eliminar rolagem horizontal acidental;
- garantir que o menu mobile expanda no fluxo da página;
- preservar Calculadora, Planejador, Simulador e regras financeiras.

## Correções aplicadas

- A navegação superior é forçada a `position: relative` em todas as larguras; não permanece sobre o conteúdo durante scroll.
- O menu mobile abre dentro do cabeçalho e aumenta a altura da navegação, empurrando o conteúdo para baixo.
- O estado do menu é limpo ao navegar, redimensionar a janela ou girar o aparelho.
- Ajuste fino no halo decorativo do hero em smartphones: o `inset` horizontal negativo causava 6–9 px de `scrollWidth` extra em 320–430 px. O efeito visual foi mantido sem extrapolar a viewport.
- Reforço de contenção horizontal no `main`, `.page`, hero e conteúdo principal em smartphones estreitos.

## Validação de responsividade

Viewports exercitadas em Chromium headless com o HTML/CSS da aplicação:

- 320 × 568
- 360 × 800
- 390 × 844
- 430 × 932
- 768 × 1024
- 900 × 900
- 1024 × 768
- 1366 × 768
- 1440 × 900
- 1920 × 1080
- 2560 × 1440

Resultados:

- `position` computado da barra superior: `relative` em todas as larguras.
- Após scroll, a barra superior sai da viewport e não cobre conteúdo.
- Menu mobile aberto aumenta a altura do header e permanece no fluxo normal.
- Sem overflow horizontal nas larguras 320, 360, 390, 430, 900, 1024, 1366, 1440, 1920 e 2560 px.
- 768 px apresentou diferença técnica máxima de 2 px em medição de subpixel, dentro da tolerância do renderer e sem rolagem horizontal perceptível.

## Validação funcional em navegador

Fluxos executados em 390 × 844 e 1366 × 768:

### Navegação

- Home → Calculadora → Planejador → Simulador.
- Menu mobile abre e fecha corretamente.
- `aria-expanded` acompanha o estado do menu.
- Ao selecionar uma página, o menu mobile fecha.

### Calculadora de Vida

Cenário:

- salário: R$ 5.000,00;
- 200 horas/mês;
- produto: R$ 1.000,00.

Resultado validado:

- valor/hora: R$ 25,00;
- horas necessárias: 40,0;
- dias de trabalho: 5,0;
- impacto no salário: 20,0%.

### Planejador

Cenário:

- renda líquida: R$ 5.000,00;
- produto: R$ 2.000,00;
- prazo desejado: 6 meses.

Resultado:

- bloco de resultados exibido;
- 4 cenários de economia renderizados;
- projeção de desconto gerada.

### Simulador

- inicialização validada;
- 8 opções carregadas no cenário de fallback controlado;
- ranking e melhor resultado renderizados;
- valor final diferente de R$ 0,00;
- cadastro de instituição personalizada validado.

### Imposto de Renda regressivo

Faixas validadas:

- até 6 meses: 22,5%;
- 7 a 12 meses: 20%;
- 13 a 24 meses: 17,5%;
- acima de 24 meses: 15%.

Cenário de controle: R$ 1.000 inicial + R$ 200/mês por 120 meses a 14,4% a.a.

- bruto: R$ 54.209,71;
- líquido tributável: R$ 49.804,00 aproximadamente;
- ativo isento: líquido igual ao bruto;
- IR desligado: líquido igual ao bruto.

## Integridade estrutural

- 15 arquivos JavaScript passaram em `node --check`.
- `banks.json` válido.
- Nenhum ID HTML duplicado.
- Nenhum asset local referenciado está ausente.
- Referências antigas ao PicPay não existem na aplicação; a palavra aparece somente em relatórios históricos de validação.
- Nenhum erro JavaScript foi registrado nos fluxos funcionais executados.

## Observação do ambiente de teste

A política administrativa do Chromium bloqueia navegação direta para `localhost`/`file://`. Para testar o DOM real, os assets locais foram injetados no documento de teste, mantendo HTML, CSS e JavaScript da aplicação, com chamadas de rede externas substituídas por respostas controladas/fallbacks. Isso permite validar layout, interações e regras locais sem depender de internet ou APIs externas.
