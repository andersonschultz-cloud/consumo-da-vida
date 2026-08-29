# Validação — Portfolio Vibe v3

Data: 2026-08-29

## Escopo visual
- Home reestruturada para uma linguagem mais próxima do portfólio Anderson Schultz: hero editorial, navegação compacta, bordas finas, superfícies sóbrias e acento ciano com uso contido.
- Logo principal reduzido e removido do papel de elemento dominante do hero.
- Novo painel lateral de apresentação da plataforma, substituindo o emblema/orbita de grandes dimensões.
- Calculadora, Planejador e Simulador mantêm títulos centralizados e passam a seguir a mesma linguagem visual.
- Fundo animado preservado com intensidade reduzida para não competir com o conteúdo.

## Validação estrutural
- Todos os arquivos JavaScript passaram por `node --check`.
- `assets/data/banks.json` validado como JSON.
- Nenhum ID HTML duplicado.
- Nenhum asset local referenciado no HTML está ausente.

## Smoke test funcional em Chromium
Como a execução direta por localhost é bloqueada administrativamente no ambiente, foi construído um harness de teste somente em memória, com CSS/JS locais inline e mock apenas para requisições de rede. O código de produção não foi alterado pelo harness.

Testes aprovados:
- Home carrega e exibe a nova composição visual.
- Navegação SPA entre Início, Calculadora, Planejador e Simulador.
- Calculadora gera horas e dias corretamente a partir dos dados informados.
- Planejador gera resumo e cenários.
- Simulador inicializa instituições e resultados.
- IR regressivo: para ativo tributável, valor líquido fica menor que o bruto.
- Inclusão de instituição personalizada.
- Alternância entre tema escuro e claro.
- Menu mobile abre e permite selecionar páginas.
- Nenhum erro JavaScript de página ou console no harness de smoke test.
