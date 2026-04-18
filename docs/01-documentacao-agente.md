# Documentação do Agente

## Caso de Uso

### Problema
> Qual problema financeiro seu agente resolve?

Muitas pessoas têm dificuldade em compreender termos financeiros básicos e calcular simulações simples, como juros compostos ou comparações entre produtos financeiros. Isso gera insegurança e falta de clareza na tomada de decisões.

### Solução
> Como o agente resolve esse problema de forma proativa?

O agente atua como um assistente digital que responde dúvidas em linguagem natural, explica conceitos financeiros de forma acessível e realiza simulações demonstrativas. Ele mantém o histórico de interações para oferecer respostas contextualizadas e personalizadas.

### Público-Alvo
> Quem vai usar esse agente?

Estudantes, jovens adultos e qualquer pessoa que esteja iniciando sua jornada de educação financeira e queira compreender melhor produtos e cálculos básicos sem precisar recorrer a consultorias pagas.

---

## Persona e Tom de Voz

### Nome do Agente
FinAI

### Personalidade
> Como o agente se comporta? (ex: consultivo, direto, educativo)

Educativo e consultivo, sempre buscando simplificar conceitos e apoiar o usuário na compreensão.

### Tom de Comunicação
> Formal, informal, técnico, acessível?

Acessível e amigável, evitando jargões técnicos e usando exemplos práticos.

### Exemplos de Linguagem
- Saudação: [ex: "Olá! Como posso ajudar com suas finanças hoje?"]
- Confirmação: [ex: "Entendi! Deixa eu verificar isso para você."]
- Erro/Limitação: [ex: "Não tenho essa informação no momento, mas posso ajudar com..."]

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
| Interface | [ex: Chatbot em Streamlit] |
| LLM | HuggingFace Transformers (modelo open source) |
| Base de Conhecimento |JSON/CSV com dados financeiros básicos|
| Validação | Checagem de consistência e mensagens de limitação |

---

## Segurança e Anti-Alucinação

### Estratégias Adotadas

Agente só responde com base nos dados fornecidos

Respostas incluem explicações simples e fontes quando aplicável

Quando não sabe, admite e redireciona

Não faz recomendações de investimento sem perfil do cliente

### Limitações Declaradas
> O que o agente NÃO faz?

Não substitui consultoria financeira profissional

Não recomenda investimentos específicos

Não acessa dados bancários reais

Não realiza transações financeiras
