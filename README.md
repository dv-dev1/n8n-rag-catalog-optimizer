# Otimização de Chatbot n8n com RAG e Pinecone

Um repositório de portfólio demonstrando um caso de estudo real de otimização de IA. Como uma arquitetura RAG no n8n reduziu o custo de consulta de API em **99,33%**.

## O Caso de Estudo: Viabilizando um Agente de Vendas de IA

Na engenharia de IA, é fácil criar algo que "funciona". O verdadeiro desafio é criar algo que seja **financeiramente viável**.

Durante meu estágio, me deparei com um desafio prático: um agente de IA para uma loja (+2.000 produtos) que era um caos financeiro. A solução inicial "funcionava", mas queimava **$20 por dia** em API (GPT-4), mesmo com tráfego baixíssimo.

---

### O Problema: 600.000+ Tokens por Consulta

A arquitetura inicial enviava o catálogo inteiro (600.000 tokens) para o GPT-4 a cada pergunta. Isso gerava um custo de **~$6,00 por consulta**.

Com um orçamento de $20, o bot só conseguia atender 3-4 clientes por dia antes de "morrer". Isso não é uma solução, é um "protótipo de luxo" que não se paga.

**IMAGEM "ANTES":**
*A linha grifada mostra o custo de 661.407 tokens para uma única consulta.*
<img width="1550" height="800" alt="image" src="https://github.com/user-attachments/assets/5b6b1c8a-5216-489f-8b22-5646b0232a3c" />


---

### A Solução: RAG + Pinecone

Meu trabalho não era só fazer funcionar, mas fazer ser **rentável**. A solução foi re-implementar o fluxo com RAG (Retrieval-Augmented Generation) e um banco de dados vetorial (Pinecone).

Em vez de enviar o catálogo todo, o agente agora busca de forma inteligente apenas os 3-5 produtos mais relevantes e envia *apenas isso* para a IA.

**IMAGEM "DEPOIS":**
*A linha grifada mostra o novo custo: 1.913 tokens.*
<img width="1550" height="800" alt="image" src="https://github.com/user-attachments/assets/5ee5de95-e2aa-4bbe-8ae3-86da2862d5ea" />



---

## O Impacto Real (Os Números)

* **Tokens por consulta:** 600.000 ➔ 1.913
* **Custo por consulta:** $6,00 ➔ $0,04
* **Resultado:** Uma otimização de custo de **99,33%** por interação.

O impacto real está no que isso fez com o orçamento diário de $20:

* **ANTES:** O bot atendia **3 clientes** por dia.
* **AGORA:** O bot atende **500 clientes** por dia.

Isso é engenharia de IA na prática: transformar um protótipo caro em um produto escalável e lucrativo.

## Sobre este Repositório

Este repositório serve como um **caso de estudo** para o meu portfólio.

Por razões éticas e de confidencialidade, os fluxos de trabalho (.json) e os prompts são propriedade da empresa e não estão incluídos. As imagens foram devidamente ofuscadas para proteger a propriedade intelectual.

**Para mais detalhes sobre esta conquista, veja meu post no LinkedIn:**
[https://www.linkedin.com/posts/dv-dev_ia-otimizaaexaeto-n8n-activity-7394121491581227009-x53o?utm_source=share&utm_medium=member_desktop&rcm=ACoAAFc_DlQBWo5kg2ycBaxMo2glIyn1uMv7brI]
