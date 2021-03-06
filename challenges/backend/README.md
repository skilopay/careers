# Desafio: GraphBanking

Este é um desafio para testar seus conhecimentos em Elixir e GraphQL.

# Obrigatório

O projeto deve ser desenvolvido em Elixir usando o Phoenix Framework.

# GraphBanking

Seu objetivo é criar um API GraphQL que permita a abertura de uma conta bancária e a transferência de ativos entre elas.

A API deve permitir:

- Abrir uma conta bancária com saldo inicial;
- Transferir ativos da "conta A" para "conta B";
- Obter as informações de uma conta, incluindo suas movimentações;

Critérios de aceitação:

- Durante a abertura da conta o saldo inicial deve ser informado;
- Não pode aceitar saldo negativo;
- Deve exibir um erro se a conta A não possuir saldo para transferência;
- Todos os campos devem ser obrigatórios;
- Não pode transferir dinheiro pra conta de origem;

Chamadas GraphQL

Query

```
account(uuid: <account_uuid>) {
  uuid
  currentBalance
  transactions {
    uuid
    address
    amount
    when
  }
}
```

Mutations

Abertura da conta

```
openAccount(balance: 100) {
  uuid
  currentBalance
}
```

Transferência entre contas

```
transferMoney(sender: <account_uuid>, address: <account_uuid>, amount: 45.5) {
  uuid
  address
  amount
  when
}
```

# Diferenciais

- Arquitetura baseada em eventos
- Utilizar alguma ferramenta de CI
- Seguir algum Elixir Style Guide
- Documentação no código
- Testes Unitários

---

Este desafio foi inspirado em: [Jusbrasil:Challenge](https://github.com/jusbrasil/careers/blob/master/challenges/02-carrinho-de-compras.md)
