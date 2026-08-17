# 💰 Agente de Gestão Financeira Pessoal

## Projeto de conclusão — Bootcamp Bradesco | DIO

Este projeto apresenta um **agente educativo de gestão financeira pessoal**, desenvolvido em Python, que utiliza uma base de dados local para analisar informações financeiras e apresentar alternativas de organização.

A proposta não é substituir um profissional financeiro. O objetivo é **transformar dados financeiros em informações simples para ajudar o usuário a compreender sua própria situação e tomar decisões conscientes**.

---

# 1. 🎯 Objetivo do projeto

O agente foi criado para responder perguntas relacionadas à organização financeira pessoal.

Ele pode ajudar a:

- visualizar receitas e despesas;
- calcular o saldo financeiro;
- identificar se o período apresenta superávit ou déficit;
- analisar despesas por categoria;
- acompanhar a reserva de emergência;
- comparar modelos de gestão financeira;
- apresentar pontos fortes e fracos de cada alternativa;
- explicar conceitos financeiros de forma simples;
- utilizar os dados existentes na base para gerar uma análise.

### Princípio principal

> O agente não decide pelo usuário. Ele apresenta informações e alternativas para fins educativos.

---

# 2. 🧠 Como funciona

O funcionamento pode ser entendido em cinco etapas:

```text
                BASE DE DADOS
                     │
                     ▼
        ┌─────────────────────────┐
        │ Validação dos arquivos  │
        └────────────┬────────────┘
                     │
                     ▼
        ┌─────────────────────────┐
        │ Leitura dos dados       │
        │ JSON / CSV / SQL        │
        └────────────┬────────────┘
                     │
                     ▼
        ┌─────────────────────────┐
        │ Análise financeira      │
        │ receitas / despesas     │
        │ saldo / reserva         │
        └────────────┬────────────┘
                     │
                     ▼
        ┌─────────────────────────┐
        │ Agente educativo        │
        │ perguntas / alternativas│
        └────────────┬────────────┘
                     │
                     ▼
              RESPOSTA AO USUÁRIO
```

O usuário faz uma pergunta.

O programa verifica se o assunto está relacionado a finanças. Em seguida, utiliza a base de dados e os cálculos realizados pelo Python para apresentar uma resposta.

---

# 3. 📁 Estrutura do projeto

```text
agente-gestao-financeira-dio/
│
├── main.py
│
├── README.md
├── requirements.txt
├── LICENSE
├── .gitignore
│
└── data/
    ├── perfil_investidor.json
    ├── produtos_financeiros.json
    ├── transacoes.csv
    ├── historico_atendimento.csv
    └── exemplos-de-gastos.sql
```

## `main.py`

É o arquivo principal da aplicação.

Nele estão:

- carregamento da base;
- validação dos dados;
- cálculos financeiros;
- regras do agente;
- modelos de gestão financeira;
- processamento das perguntas;
- execução do programa.

## `data/`

É a pasta que contém a base usada pelo projeto.

### `perfil_investidor.json`

Contém informações do perfil utilizado na demonstração, como:

- nome;
- idade;
- perfil;
- objetivo;
- renda;
- patrimônio;
- reserva;
- metas.

### `transacoes.csv`

Contém as movimentações utilizadas nos cálculos.

O programa utiliza essas informações para calcular receitas, despesas e saldo.

### `historico_atendimento.csv`

Contém registros de atendimentos anteriores utilizados como parte da base do projeto.

### `produtos_financeiros.json`

Contém produtos financeiros usados para comparação educativa.

O projeto não transforma automaticamente esses produtos em recomendação de investimento.

### `exemplos-de-gastos.sql`

Arquivo SQL mantido como material de referência da base.

Por segurança, o programa não executa comandos SQL automaticamente.

---

# 4. 🔐 Segurança e confiabilidade

Uma das principais preocupações do projeto é evitar respostas financeiras inventadas ou apresentadas como fatos quando não estão confirmadas.

O código possui algumas regras para isso.

## 4.1 Não inventar informações

Quando o dado necessário não está disponível na base, o programa deve informar que não possui dados suficientes.

Exemplo:

```text
Não há dados suficientes para calcular a meta da reserva.
```

Isso é preferível a criar um número que não existe na base.

---

## 4.2 Cálculos feitos pelo programa

Informações quantitativas importantes são calculadas pelo Python.

Por exemplo:

```text
saldo = receitas - despesas
```

Assim, o agente não precisa "imaginar" qual é o saldo.

---

## 4.3 Não prometer ganhos

O agente não promete:

- lucro;
- rentabilidade;
- retorno garantido;
- enriquecimento;
- resultado financeiro futuro.

---

## 4.4 Investimentos

Quando o usuário pergunta sobre investimentos, o projeto apresenta informações educativas.

O agente não deve dizer:

```text
"Este é o melhor investimento para você."
```

Em vez disso, deve explicar características e permitir que o usuário compare alternativas.

---

# 5. 📊 Modelos de gestão financeira

O projeto apresenta diferentes modelos de organização financeira.

Eles não são classificados como "melhor" ou "pior".

Cada alternativa possui:

- descrição;
- pontos fortes;
- pontos fracos.

Atualmente são apresentados exemplos como:

### Orçamento por percentuais

Distribui a renda entre categorias usando limites ou percentuais.

**Pontos fortes:**

- simples de entender;
- facilita o acompanhamento;
- ajuda a estabelecer limites.

**Pontos fracos:**

- os percentuais podem não funcionar para todas as pessoas;
- despesas extraordinárias podem dificultar o planejamento.

---

### Orçamento Base Zero

A renda recebe uma finalidade dentro do planejamento.

**Pontos fortes:**

- permite acompanhar melhor o destino do dinheiro;
- pode revelar despesas não planejadas.

**Pontos fracos:**

- exige mais acompanhamento;
- pode consumir mais tempo.

---

### Método dos Envelopes

O orçamento é dividido por categorias com limites definidos.

**Pontos fortes:**

- deixa os limites mais claros;
- pode ajudar no controle dos gastos.

**Pontos fracos:**

- exige disciplina;
- pode ser menos conveniente para gastos muito variáveis.

---

### Pague-se Primeiro

Uma parcela da renda é separada para objetivos financeiros antes da distribuição do restante.

**Pontos fortes:**

- pode facilitar a criação de uma reserva;
- coloca os objetivos financeiros no planejamento.

**Pontos fracos:**

- pode pressionar o orçamento quando a renda já está comprometida;
- não substitui o controle das despesas.

---

# 6. 📈 Indicadores calculados

O sistema calcula alguns indicadores básicos.

## Receitas

Representa a soma das entradas encontradas na base de transações.

## Despesas

Representa a soma das saídas encontradas na base.

## Saldo

Calculado por:

```text
Saldo = Receitas - Despesas
```

## Situação financeira do período

O resultado é classificado como:

```text
Saldo > 0  → SUPERÁVIT
Saldo < 0  → DÉFICIT
Saldo = 0  → EQUILÍBRIO
```

Essa classificação representa **somente o período existente na base de transações**.

---

# 7. 🧮 Exemplo de análise

Com os dados de demonstração do projeto, o programa pode apresentar informações como:

```text
Renda mensal:       R$ 5.000,00
Receitas:           R$ 5.000,00
Despesas:           R$ 2.488,90
Saldo:              R$ 2.511,10

Situação:           SUPERÁVIT
Taxa de poupança:   50,22%

Reserva atual:      R$ 10.000,00
Meta:               R$ 15.000,00
Diferença:          R$ 5.000,00
Progresso:          66,67%
```

### Interpretação educativa

O cálculo indica que, no período analisado, as receitas foram superiores às despesas.

Isso **não significa automaticamente que a situação financeira esteja perfeita**.

Ainda é necessário observar:

- composição das despesas;
- dívidas;
- objetivos;
- estabilidade da renda;
- necessidade de liquidez;
- capacidade de manter o comportamento financeiro.

Essa diferença entre **dado calculado** e **interpretação** é importante para evitar conclusões exageradas.

---

# 8. 💬 Exemplos de perguntas

Depois de executar o programa, o usuário pode testar:

```text
Qual é minha situação financeira?
```

```text
Como está minha reserva?
```

```text
Quais modelos de gestão financeira existem?
```

```text
Quero organizar minhas finanças.
```

```text
Quero investir meu dinheiro.
```

---

# 9. ▶️ Como executar

## Pré-requisito

Python 3.10 ou superior.

## Instalar dependências

No terminal:

```bash
pip install -r requirements.txt
```

## Executar

```bash
python main.py
```

O programa deverá apresentar:

```text
AGENTE DE GESTÃO FINANCEIRA PESSOAL
Projeto de conclusão — Bootcamp DIO / Bradesco
```

Depois disso, basta digitar uma pergunta.

Para encerrar:

```text
sair
```

---

# 10. 🗂️ Por que não usar o caminho `C:\Users\...`?

O projeto originalmente utilizava um caminho específico do computador do desenvolvedor.

Isso cria um problema:

```text
C:\Users\edileaceia\Desktop\alan\chat bot\data
```

Esse caminho só existe naquele computador.

Por isso, o projeto foi estruturado para utilizar:

```text
data/
```

relativo ao próprio projeto.

O `main.py` identifica automaticamente a pasta em que está localizado e procura os arquivos dentro de:

```text
projeto/data/
```

Dessa forma, o projeto pode ser clonado do GitHub em outro computador sem precisar alterar o caminho manualmente.

---

# 11. 🛡️ Boas práticas para publicar no GitHub

Os arquivos disponibilizados neste projeto devem ser considerados **dados de demonstração**.

Não publique:

- senhas;
- tokens;
- chaves de API;
- dados bancários;
- CPF;
- informações reais de clientes;
- documentos pessoais;
- dados financeiros identificáveis.

Se os dados utilizados no projeto representarem pessoas reais, substitua-os por dados fictícios ou anonimizados antes de tornar o repositório público.

---

# 12. 🚧 Limitações atuais

Este projeto é um **protótipo educacional**.

Ele ainda não possui:

- interface gráfica;
- autenticação;
- banco de dados relacional integrado;
- API;
- modelo de linguagem conectado;
- testes automatizados completos;
- sistema de auditoria;
- integração automática com instituições financeiras.

Portanto, ele não deve ser utilizado como sistema financeiro de produção.

---

# 13. 🔮 Próximas melhorias

Uma evolução natural do projeto seria adicionar:

### Etapa 1 — Interface

Criar uma interface web para facilitar a utilização.

### Etapa 2 — Gráficos

Apresentar:

- receitas;
- despesas;
- categorias;
- evolução da reserva.

### Etapa 3 — Banco de dados

Substituir arquivos estáticos por uma estrutura de banco de dados.

### Etapa 4 — IA generativa

Integrar um modelo de linguagem ao agente.

Nesse cenário, seria importante manter uma camada de validação para impedir que a IA apresente como fato algo que não esteja confirmado na base.

### Etapa 5 — Testes

Criar testes automatizados para:

- cálculos;
- carregamento dos arquivos;
- respostas fora do escopo;
- regras de segurança;
- tratamento de dados ausentes.

---

# 14. 🎓 Relação com o Bootcamp

Este projeto demonstra a aplicação prática de conceitos de programação e inteligência artificial em um problema do cotidiano.

A solução combina:

```text
Python
+
Pandas
+
JSON
+
CSV
+
SQL como base de referência
+
Regras de negócio
+
Educação financeira
```

O principal objetivo não é criar um sistema que "decide pelo usuário", mas demonstrar como uma aplicação pode utilizar dados estruturados para gerar uma análise compreensível e apresentar alternativas de maneira responsável.

---

# 15. ⚠️ Aviso

Este projeto possui finalidade **educacional**.

As análises apresentadas são baseadas nos dados disponíveis na aplicação e não constituem aconselhamento financeiro profissional, recomendação de investimento ou promessa de resultado.

O usuário deve analisar sua própria situação e, quando necessário, procurar um profissional habilitado.

---

## Autor

Projeto desenvolvido para apresentação no **Bootcamp Bradesco — DIO**.

---

## Licença

MIT.
