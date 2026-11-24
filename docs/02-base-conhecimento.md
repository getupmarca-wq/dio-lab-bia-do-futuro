# Base de Conhecimento

## Dados Utilizados

Descreva se usou os arquivos da pasta `data`, por exemplo:

| Arquivo | Formato | Utilização no Agente |
|---------|---------|---------------------|
| `historico_atendimento.csv` | CSV | Contextualizar interações anteriores para ser mais eficiente no atendimento, referência. |
| `perfil_investidor.json` | JSON | Personalizar recomendações, atribuindo as melhores opções de solução financeira. Explique o uso explicativo no perfil  |
| `transacoes.csv` | CSV | Analisar padrão de gastos do cliente, identificar gargalos e gerar opções de melhoria para ele busque resolver, arquivos lidos |
|`exemplo-de-gastos.SQL`| SQL | Utilize como exemplos de gastos, para possíveis análises, não há execução automática de SQL |


---

## Adaptações nos Dados

> Você modificou ou expandiu os dados mockados? Descreva aqui.

Sim, utilizando dados de despesas e receitas para uma melhor análise por parte da ia.

---

## Estratégia de Integração

### Como os dados são carregados?
> Descreva como seu agente acessa a base de conhecimento.

Os JSON/CSV/SQL são carregados no início da sessão e incluídos no contexto do prompt

### Como os dados são usados no prompt?
> Os dados vão no system prompt? São consultados dinamicamente?

sim, a título de exemplo. Os dados, a princípio, são retirado de um banco de dados público, a nível de exemplo. são separados e retirados só o que o cliente deseja.

---

## Exemplo de Contexto Montado

> Mostre um exemplo de como os dados são formatados para o agente. Os dados a seguir são fictícios, utilize apenas a título educacional.

```
Dados do Cliente:
- Nome: João Silva
- Perfil: Moderado
- Saldo disponível: R$ 5.000

Últimas transações:
- 01/11: Supermercado - R$ 450
- 03/11: Streaming - R$ 55
...
```
