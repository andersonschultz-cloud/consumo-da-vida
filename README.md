# Consumo da Vida — v6.0 Premium

**Hub de Inteligência Financeira do Instituto Schultz — finanças, tecnologia e consciência.**

🌐 **[consumodavida.com.br](https://consumodavida.com.br)**

## Ferramentas

| | Ferramenta | O que faz |
|---|---|---|
| 🕐 | **Calculadora de Vida** | Converte preço em horas/dias de trabalho. Método QDP. |
| 📊 | **Planejador de Compras** | Avalia peso da compra, plano de economia, desconto à vista. |
| 📈 | **Simulador de Rendimentos** | Juros compostos com Selic ao vivo + 8 instituições + comparison cards. |

## Estrutura do projeto

```
assets/css/        → Design System modular (5 arquivos, incluindo o tema premium)
assets/js/         → Módulos JavaScript (9 arquivos)
assets/data/       → banks.json (fonte de dados dos bancos)
assets/img/logo/   → Logo, favicon e ícones da plataforma
assets/img/background/ → Fundo tecnológico em SVG
docs/              → Arquitetura e changelog
```

## Adicionar um banco

Edite apenas `assets/data/banks.json` — nenhum código precisa ser alterado.

## Deploy

```bash
git add -A && git commit -m "descrição" && git push origin main
```

---
Desenvolvido por [Anderson Schultz Ribeiro](https://linkedin.com/in/anderson-schultz-ribeiro0001)


## v6.0 — identidade premium

Nova identidade Instituto Schultz, hero com raposa abstrata, dashboard premium, Método QDP, refinamento completo para desktop e iPhone e fallbacks de robustez. Veja `docs/testes-v6.md`.
