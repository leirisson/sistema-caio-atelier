# 🧵 Sistema de Gestão de Vendas para Confecção Infantil

> Um sistema simples e eficiente para gestão de clientes, vendas, entregas e relatórios para confecções infantis (fantasias, batizados, casamentos, apresentações escolares).

---

## 📌 Visão Geral

Este sistema foi desenvolvido para automatizar e organizar o fluxo de trabalho de uma confecção especializada em roupas infantis. Ele permite o cadastro de clientes com múltiplas crianças, controle de vendas, status de entrega, gerenciamento de pagamentos (incluindo parcelamento), registro de despesas e geração de relatórios estratégicos.

Ideal para pequenos negócios que desejam ter maior controle financeiro, melhor atendimento ao cliente e crescimento sustentável.

---

## ✨ Funcionalidades

- ✅ Cadastro de clientes com múltiplas crianças
- ✅ Registro detalhado de vendas (tipo de produto, tamanho, descrição, valor, etc.)
- ✅ Controle de status de entrega: Aguardando prova, Tirar medida, Atrasada, Entregue
- ✅ Gestão de pagamentos parciais (ex: 50% na entrada via PIX)
- ✅ Validação automática de pagamento restante ao entregar o produto
- ✅ Registro de despesas operacionais
- ✅ Geração de relatórios mensais:
  - Faturamento do mês
  - Cliente destaque (maior número de compras)
  - Aniversariantes do mês
  - Crescimento anual
  - Programa de indicação

---

## 🗄️ Modelo de Banco de Dados

O sistema utiliza um modelo relacional com normalização até a 3ª forma normal (3NF). As principais entidades são:

| Entidade | Descrição |
|--------|-----------|
| `CLIENTE` | Dados do responsável (nome, telefone, endereço, Instagram) |
| `CRIANÇA` | Informações das crianças associadas ao cliente (nome, sexo, aniversário) |
| `VENDA` | Detalhes de cada venda realizada |
| `PRODUTO` | Tipos de produtos oferecidos (fantasia, batizado, etc.) |
| `STATUS_ENTREGA` | Status do pedido |
| `PAGAMENTO` | Registros de pagamentos (entrada e restante) |
| `DESPESA` | Despesas operacionais |
| `RELATORIO` | Métricas mensais e indicadores de negócio |

> 📂 Veja o diagrama completo em [`docs/diagrama-er.txt`](docs/diagrama-er.txt)

---

## 🔄 Fluxo de Trabalho

```text
[Cliente] → [Cadastro] → [Venda] → [Status de Entrega]
     ↓                          ↓
[Aniversário]             [Pagamento Parcial?]
                                 ↓
                    [Entrega? → Validar Restante]
                                 ↓
                   [Gerar Relatório Mensal]
