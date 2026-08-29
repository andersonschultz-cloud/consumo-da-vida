# Consumo da Vida — Corporate v4

## Ajustes visuais
- Logo da navegação restaurado para uma presença maior e proporcional, sem dominar o header.
- Marca reorganizada para destacar "Consumo da Vida" e deixar "Schultz" como assinatura secundária.
- Logo do painel executivo e do rodapé redimensionados para manter consistência.
- Hero reduzido para uma escala mais corporativa e melhor leitura em notebook e desktop.
- Títulos de Calculadora, Planejador e Simulador redimensionados e mantidos centralizados.
- Ícones das ferramentas, métricas, botões e badges padronizados em uma escala menor e consistente.
- Cards, controles e botões receberam proporções mais compactas e executivas.
- Mobile recebeu ajustes próprios de logo, título, ícones, menu e espaçamento.

## Validação estrutural
- Todos os JavaScripts foram validados com `node --check`.
- Não foram encontrados IDs HTML duplicados.
- Assets locais referenciados no HTML foram verificados.
- A alteração é uma camada CSS adicional e não modifica regras de negócio.

## Observação
O ambiente de execução bloqueia navegação do Chromium para localhost por política administrativa, portanto o teste E2E visual automatizado no navegador não pôde ser concluído nesta sessão. A validação estrutural e de sintaxe foi concluída.
