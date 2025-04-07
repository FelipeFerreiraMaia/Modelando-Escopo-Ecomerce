# 📚 Projeto de Modelagem Conceitual — Modelando Escopo E-commerce

Este projeto foi desenvolvido como parte dos estudos em modelagem de banco de dados no contexto da linguagem SQL. O objetivo é aplicar os principais conceitos de modelagem conceitual, incluindo **entidades**, **relacionamentos**, **especializações**, **heranças** e **cardinalidades**, simulando as necessidades de um sistema real de e-commerce.

---

## 🎯 Objetivo do Modelo

Representar a estrutura de dados de um sistema de e-commerce capaz de:

- Cadastrar clientes (Pessoa Física e Pessoa Jurídica)
- Gerenciar contas de acesso
- Registrar e processar pedidos
- Suportar múltiplas formas de pagamento
- Controlar entregas e cancelamentos

---

## 👥 Modelagem de Tipos de Conta

O modelo diferencia dois perfis de clientes a partir da entidade `Conta`, que possui um atributo `tipoCliente` com os valores `'PF'` (Pessoa Física) e `'PJ'` (Pessoa Jurídica).

### Especializações:
- **Pessoa Física**: inclui `nome`, `cpf`, `dataNascimento`
- **Pessoa Jurídica**: inclui `razaoSocial`, `cnpj`, `inscricaoEstadual`

Essa abordagem permite aplicar os conceitos de especialização na modelagem, otimizando a estrutura do banco e evitando duplicidade de dados.

---

## 💰 Forma de Pagamento com Herança

A entidade `Forma de Pagamento` representa os métodos disponíveis para finalização dos pedidos e se ramifica em três especializações:

- **Cartão de Crédito**: `numeroCartao`, `nomeTitular`, `validade`
- **Boleto**: `codigoBarras`, `vencimento`
- **Pix**: `chavePix`

Foi utilizada **herança com especialização** para refletir os atributos específicos de cada forma de pagamento, reforçando a prática de normalização e reaproveitamento de estrutura.

---

## 📦 Entrega dos Pedidos

A entidade `Entrega` foi adicionada ao modelo para representar a etapa logística do processo de compra. Ela contém:

- `statusEntrega` (ex: em trânsito, entregue, etc.)
- `codigoRastreio`
- `dataEnvio` e `dataEntrega`

Essa entidade está diretamente relacionada à entidade `Pedido` com cardinalidade 1:1, permitindo rastreabilidade individualizada de cada entrega.

---

## ❌ Cancelamento de Pedidos

O modelo contempla também o cenário de pedidos cancelados por meio da entidade `Cancelamento`, que registra:

- `motivo` do cancelamento
- `dataCancelamento`
- Referência ao pedido correspondente

Dessa forma, mantém-se o histórico e os motivos das interrupções de pedidos, o que pode ser útil em análises futuras e controle de qualidade.

---

## 📌 Considerações Finais

O modelo desenvolvido visa consolidar o conhecimento teórico da disciplina, simulando um cenário prático de e-commerce. Conceitos como:

- Entidades fortes e fracas
- Especializações e generalizações
- Relacionamentos binários e n-ários
- Regras de integridade e cardinalidade

foram aplicados com o objetivo de preparar a base para uma futura implementação lógica em bancos de dados relacionais com SQL.

---

## 🖼️ Arquivos Entregues

- `Modelando Escopo E-commerce_Felipe Ferreira Maia.png`: Diagrama conceitual completo (modelo ER)
- `README.md`: Documento explicativo da modelagem

---

📘 *Projeto realizado como parte da formação em SQL e modelagem de dados no programa Bootcamp Heineken -Inteligência Artificial Aplicada a Dados com Copilot.*
