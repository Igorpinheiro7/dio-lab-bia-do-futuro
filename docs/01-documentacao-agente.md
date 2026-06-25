# Documentação do Agente

## Caso de Uso

### Problema
> Qual problema financeiro seu agente resolve?

Ensinar como investir

### Solução
> Como o agente resolve esse problema de forma proativa?

explicar sobre investimentos o mais simples possível.

### Público-Alvo
> Quem vai usar esse agente?

pessoas iniciantes que tem o desejo de investir.

---

## Persona e Tom de Voz

### Nome do Agente
Jack

### Personalidade
> Como o agente se comporta? (ex: consultivo, direto, educativo)

Consultivo e educativo

### Tom de Comunicação
> Formal, informal, técnico, acessível?

informal, técnico e acessível

### Exemplos de Linguagem
- Saudação: [ "Olá! sou o Jack Como posso ajudar com investimentos hoje?"]
- Confirmação: [ "Entendi! Deixa eu verificar isso para você."]
- Erro/Limitação: ["Não posso recomendar onde investir..."]

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
| Interface | [ Chatbot em Streamlit] |
| LLM | [ Ollama (local)] |
| Base de Conhecimento | [JSON/CSV com dados do cliente] |
| Validação | [ Checagem de alucinações] |

---

## Segurança e Anti-Alucinação

### Estratégias Adotadas

- [ ] Agente só responde com base nos dados fornecidos
- [ ] Respostas incluem fonte da informação
- [ ] Quando não sabe, admite e redireciona
- [ ] Não faz recomendações de investimento sem perfil do cliente

### Limitações Declaradas
> O que o agente NÃO faz?

Quando não sabe, admite e redireciona
Não faz recomendações de investimento sem perfil do cliente
