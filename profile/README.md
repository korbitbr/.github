<div align="center">

# korbitbr

**Infraestrutura de pagamentos para negócios digitais no Brasil — em código aberto.**

PIX e cartão com 3DS · assinaturas · checkout hospedado · payouts via PIX · antecipações

[Documentação](https://docs.korbit.com.br) · [API Reference](https://docs.korbit.com.br/api-reference) · [SDK Node.js](https://docs.korbit.com.br/sdk/visao-geral) · [reportar vulnerabilidade](https://github.com/korbitbr/.github/blob/main/SECURITY.md)

</div>

---

## O que é a Korbit

A Korbit é a plataforma que conecta negócios digitais e SaaS ao dinheiro: o comerciante expõe o produto, o cliente paga por **PIX** ou **cartão**, e o valor chega ao saldo para **saque direto via PIX** — com assinaturas, antecipações, reconciliação financeira e ambiente sandbox completo.

Esta organização guarda a parte pública dessa operação: o que nossos usuários e integradores usam para construir em cima da plataforma.

## O ecossistema aberto

| Repositório | O que é |
| --- | --- |
| [`korbit-docs`](https://github.com/korbitbr/korbit-docs) | Documentação pública da API (Mintlify) — guias, referência OpenAPI, webhooks e sandbox |
| [`korbit-sdk`](https://github.com/korbitbr/korbit-sdk) | SDK oficial Node.js — idempotência automática, retries, erros tipados, webhooks verificados |
| [`korbit-mcp`](https://github.com/korbitbr/korbit-mcp) | Servidor MCP para agentes de IA operarem a Korbit — com movimentação financeira desligada por padrão |
| [`korbit-skills`](https://github.com/korbitbr/korbit-skills) | Skills `SKILL.md` que ensinam assistentes de código a integrar a Korbit do jeito certo |

## Comece por aqui

```bash
# Node.js
npm install @korbitbr/sdk
```

```ts
import { Korbit } from '@korbitbr/sdk';

const korbit = new Korbit({ apiKey: 'kbt_test_...' }); // sandbox
const payment = await korbit.payments.create({
  amount: 14990, // R$ 149,90 em centavos
  paymentMethod: 'PIX',
});
```

Primeira venda ponta a ponta em menos de 10 minutos: [quickstart](https://docs.korbit.com.br/guias/quickstart).

## Como trabalhamos

- **APIs com contrato versionado** — toda a superfície pública é descrita em OpenAPI e testada contra ela mesma (SDK, docs e playground gerados da mesma fonte).
- **Segurança por padrão** — menor privilégio por escopo, ambientes isolados, segredos nunca em código, e ferramentas financeiras desligadas até você ligá-las explicitamente.
- **Issues e PRs são bem-vindos** — bugs de documentação, melhorias de DX e discussões de design do SDK seguem o fluxo padrão de cada repositório. Vulnerabilidades **não**: siga [SECURITY.md](https://github.com/korbitbr/.github/blob/main/SECURITY.md).

<div align="center">

[docs.korbit.com.br](https://docs.korbit.com.br) · [korbit.com.br](https://korbit.com.br)

</div>
