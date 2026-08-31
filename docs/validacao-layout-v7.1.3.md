# Consumo da Vida — validação v7.1.3

## Objetivo
Revisar o layout da versão v7.1.2, reduzir espaços ociosos, compactar menu e rodapé e garantir comportamento consistente em desktop, tablet e smartphones sem alterar regras de negócio.

## Ajustes visuais
- Menu superior reduzido de aproximadamente 80 px para 66 px no desktop e 60 px em smartphones.
- Lockup da marca reorganizado para não forçar altura extra no cabeçalho.
- Menu continua no fluxo da página (`position: relative`) e não sobrepõe conteúdo durante rolagem.
- Menu mobile abre dentro do fluxo e empurra o conteúdo para baixo.
- Hero, blocos da home e cartões receberam ritmo vertical mais compacto.
- Painel ilustrativo do hero é ocultado abaixo de 1100 px para evitar uma composição alta e desproporcional em tablets/notebooks compactos.
- Espaçamento interno da área do Método QDP reduzido.
- Cabeçalhos da Calculadora, Planejador e Simulador ficaram mais compactos.
- Padding inferior dos containers de ferramentas caiu de ~110 px para 56 px no desktop e de ~70 px para 34 px no smartphone.
- Margem superior do rodapé caiu de 100 px para 0, preservando respiro pelo padding da seção anterior.
- Rodapé ficou mais compacto e mantém os logos do Consumo da Vida e Instituto Schultz em paridade visual.
- Corrigido um overflow residual de 2 px em 768 px causado pelo halo decorativo do hero.

## Viewports validadas
320, 360, 390, 430, 768, 900, 1024, 1366, 1440, 1920 e 2560 px.

Em todas elas:
- `scrollWidth == clientWidth`;
- tentativa de rolagem horizontal permaneceu em `scrollX = 0`;
- cabeçalho permaneceu `position: relative`;
- menu mobile empurrou o conteúdo em vez de sobrepô-lo;
- não houve quebra horizontal do layout.

## Validação funcional automatizada
13/13 verificações aprovadas:
- navegação Home / Calculadora / Planejador / Simulador;
- cálculo da Calculadora de Vida;
- geração do Planejador;
- cenários do Planejador;
- IR regressivo no Simulador;
- IR habilitado por padrão;
- ranking do Simulador;
- troca de tema;
- cadastro de instituição personalizada;
- ausência de erros JavaScript não tratados no fluxo testado.

### Caso de controle — Calculadora
R$ 5.000 / 200 h e compra de R$ 1.000:
- valor/hora: R$ 25,00;
- horas necessárias: 40,0;
- dias de trabalho: 5,0;
- impacto na renda: 20,0%.

### Caso de controle — Simulador
R$ 1.000 iniciais + R$ 200/mês por 10 anos a 14,4% a.a.:
- bruto: R$ 54.209,71;
- líquido com IR regressivo: R$ 49.804,00.

## Validações estruturais
- todos os arquivos JavaScript passaram por `node --check`;
- `banks.json` válido;
- nenhum ID HTML duplicado;
- nenhum asset local referenciado ausente;
- nova folha `layout-refine-v7.1.3.css` carregada por último para consolidar o layout sem alterar lógica financeira.
