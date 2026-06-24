# 💰 Consumo da Vida

**Plataforma de Inteligência Financeira** — três ferramentas integradas para educação financeira consciente.

🌐 **Live:** [consumodavida.com.br](https://consumodavida.com.br)

---

## Ferramentas

| Ferramenta | O que faz |
|---|---|
| 🕐 **Calculadora de Vida** | Converte preço em horas/dias de trabalho real. Método QDP. |
| 📊 **Planejador de Compras** | Avalia peso da compra na renda, plano de economia, projeção de desconto. |
| 📈 **Simulador de Rendimentos** | Juros compostos com Selic ao vivo (Banco Central). Linha do tempo arrastável. |

## Stack

- HTML + CSS + Vanilla JS (single-file SPA, zero build step)
- Chart.js 4.4.1 via CDN
- Tipografia: DM Sans · DM Serif Display · DM Mono (Google Fonts)
- Dados em tempo real: [api.bcb.gov.br](https://api.bcb.gov.br) (Selic)
- Deploy: GitHub Pages + domínio personalizado

## Deploy

```bash
git add .
git commit -m "deploy: Consumo da Vida vX.X"
git push origin main
```

GitHub Pages publica automaticamente. DNS já configurado para `consumodavida.com.br`.

## Design System

- Paleta v4.0 auditada WCAG AA/AAA
- Modo claro e escuro (`prefers-color-scheme` + toggle manual)
- Acessibilidade: skip link, ARIA roles, focus-visible, aria-live, prefers-reduced-motion

---

Desenvolvido por [Anderson Schultz Ribeiro](https://www.linkedin.com/in/anderson-schultz-ribeiro0001/)
