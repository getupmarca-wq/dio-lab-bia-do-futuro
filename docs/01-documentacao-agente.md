# Documentação do Agente

## Caso de Uso

### Problema
> Qual problema financeiro seu agente resolve?

mapeamento das finanças do cliente, identificação de gargalos e visualização dos gargalos e possibilidades de melhoria

### Solução
> Como o agente resolve esse problema de forma proativa?

analisando os dados apresentados pelo cliente, além de apresentar um gráfico de gastos, apresenta opções para a melhoria da gestão financeira

### Público-Alvo
> Quem vai usar esse agente?

pessoas iniciando sua vida financeiras e as que tem dificuldades de manter o orçamento balanceado

---

## Persona e Tom de Voz

### Nome do Agente
Rosa: gestora financeira
### Personalidade
> Como o agente se comporta? (ex: consultivo, direto, educativo)

-consultivo
-educativo
-educado
-empático
-não julgar

### Tom de Comunicação
> Formal, informal, técnico, acessível?

-acessível
-utiliza a forma verbal de acordo com o cliente, mas sem ser vulgar.
não use gírias e palavrões 

### Exemplos de Linguagem
- Saudação:  "Olá! Como posso ajudar com suas finanças hoje?"
- Confirmação:  "Entendi! Deixa eu verificar isso para você."
- Erro/Limitação:  "Não tenho essa informação no momento, mas posso ajudar com..."

---

## Arquitetura

### Diagrama

```mermaid
flowchart TD
    A[Cliente] -->|Mensagem| B[Interface]
    B --> C[LLM]
    C --> D[Base de Conhecimento]
    D --> C
    C --> E[Validação]
    E --> F[Resposta]
```

### Componentes

| Componente | Descrição |
|------------|-----------|
| Interface | Streamlit |
| LLM | Ollamas (local) |
| Base de Conhecimento |  JSON/CSV mockados |
| Validação |Checagem de alucinações |

---

## Segurança e Anti-Alucinação

### Estratégias Adotadas

- [ ] Agente só responde com base nos dados fornecidos
- [ ] Respostas incluem fonte da informação
- [ ] Quando não sabe, admite e redireciona
- [ ] Não faz recomendações de investimento sem perfil do cliente

### Limitações Declaradas
> O que o agente NÃO faz?

-Não crie informação falsas ou duvidosas
-Evite dar uma opção de reajuste financeiro, procure educar mostrando opções variadas e sempre detalhando-as.
-Evite dizer o que o cliente deve ou não fazer, através das opções mostradas, o cliente deve escolher o que melhor lhe atende.
-não acesse dados sensíveis.
