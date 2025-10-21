# Análise de Tarefas

> **_NOTE:_**: A equipe deve descrever as funcionalidades mais importantes da interface/produto. A equipe deve modelar pelo menos 1 HTA, 1 GOMS e 1 CTT (de pelo menos 4 funcionalidades diferentes). Cada diagrama deve ter um texto explicando a funcionalidade.

1. HTA
2. GOMS
3. CTT

---

# ⚙️ Análise de Tarefas — Ecologic Smoke  
*(Conforme Barbosa & Silva 2010 / Disciplina CC8122 – FEI)*

A análise de tarefas permite compreender **como os usuários realizam o trabalho** dentro da interface proposta e **por que** o fazem dessa forma.  
O objetivo é mapear **tarefas, sub-tarefas e ações** para melhorar a eficiência, reduzir erros e garantir que a interface responda adequadamente às necessidades do usuário final e dos parceiros comerciais.

---

## 🔹 HTA — Hierarchical Task Analysis  
### **Funcionalidade: Realizar Compra de Produto com Sistema de Pontos**

| Nível | Objetivos / Operações | Problemas Identificados | Recomendações IHC |
|-------|-----------------------|-------------------------|-------------------|
| **0** | **Efetuar compra com resgate de pontos**  <br> *Input:* usuário logado e produto selecionado    *Feedback:* confirmação de pedido e saldo atualizado    *Plano:* 1 > 2 > 3 | Processo de checkout fragmentado entre páginas | Unificar em uma única página de pagamento |
| **1** | Selecionar produto e adicionar ao carrinho | Filtros pouco visíveis e demora na resposta | Implementar filtros dinâmicos e feedback visual |
| **2** | Escolher forma de pagamento (PIX, cartão ou pontos) | Dúvida sobre saldo de pontos | Mostrar saldo em tempo real |
| **3** | Confirmar dados e finalizar compra | Falta de mensagem de confirmação | Inserir mensagem de feedback positivo |

**Plano HTA:** Para finalizar a compra (0), o usuário deve selecionar o produto (1), escolher a forma de pagamento (2) e confirmar a transação (3).  

**Interpretação:** A HTA mostra que o processo de compra precisa de maior integração e feedback imediato.  
**Recomendação:** Simplificar a sequência de ações com feedback em cada etapa e design consistente com a identidade visual da marca.

---

## 🔹 GOMS — Goals, Operators, Methods and Selection Rules  
### **Funcionalidade: Montar Box Personalizado**

**GOAL 0:** Criar um box mensal personalizado de produtos.  

- **GOAL 1:** Selecionar categoria de produtos  
  - **METHOD 1A:** Escolher a partir de categorias fixas (papel, ervas, acessórios)  
     *(SEL. RULE:* usuário já sabe o tipo de produto desejado )*  
  - **METHOD 1B:** Usar sugestões automáticas do sistema  
     *(SEL. RULE:* usuário não tem preferência definida )*  

- **GOAL 2:** Personalizar quantidade e tipo de itens  
    **OP. 2.1:** Ajustar quantidade via controle (“+ / –”)  
    **OP. 2.2:** Visualizar valor e pontos em tempo real  

- **GOAL 3:** Confirmar e salvar box  
    **OP. 3.1:** Clicar em “Salvar Box”  
    **OP. 3.2:** Receber feedback visual de confirmação  

**Selection Rule:** Se o usuário não souber o que incluir, o sistema sugere kits pré-montados; caso contrário, segue para customização manual.  

**Interpretação:** O modelo GOMS identifica a carga cognitiva na criação do box e permite reduzi-la com sugestões contextuais e automação parcial.  

---

## 🔹 CTT — Concur Task Trees  
### **Funcionalidades: (A) Compra de Produto   (B) Participar de Evento   (C) Interagir na Comunidade   (D) Gerenciar Pedidos Parceiro**

**Legenda de relações:**  
- T1 >> T2 → T2 só inicia após T1 concluir.  
- T1 [ ] >> T2 → T1 passa informação a T2.  
- T1 ||| T2 → tarefas concorrentes.  
- T1 [> T2 → T1 é interrompida por T2.  

---

### 🧭 Diagrama Textual CTT — Fluxo Principal

**T0 — Interagir com a Plataforma Ecologic Smoke**  
- T1: Explorar catálogo de produtos  
- T2: Comprar produto [ ] >> T3: Gerar pontos de fidelidade  
- T4: Participar de eventos || | | T5: Interagir na comunidade  
- T6: Parceiro gerenciar estoque consignado >> T7: Emitir relatório de vendas  

**Relações:**  
- T1 [ ] >> T2 (passa dados do produto para compra).  
- T2 [ ] >> T3 (gera pontos automáticos).  
- T4 ||| T5 (tarefas concorrentes de engajamento).  
- T6 >> T7 (sequência de gestão operacional).  

---

**Interpretação:** O modelo CTT demonstra como as tarefas principais (usuário final e parceiro) acontecem de forma concorrente, mas com dependências claras de informação.  
Ele evidencia a necessidade de um **núcleo de dados integrado** que permita transitar de compra para evento e para a comunidade sem perder contexto.

---

## 🧩 Síntese Geral

| Modelo | Foco | Insight Principal | Recomendações de IHC |
|---------|------|------------------|-----------------------|
| **HTA** | Estrutura sequencial da compra | Processo de checkout precisa de feedback contínuo e menos telas | Unificar pagamento e confirmação em um único fluxo |
| **GOMS** | Interação cognitiva na montagem do box | Reduzir decisões repetitivas e fornecer sugestões contextuais | Oferecer kits pré-montados e autocompletar preferências |
| **CTT** | Concorrência entre tarefas do usuário e do sistema | Integrar compra, evento e comunidade no mesmo ecossistema | Implementar núcleo central de dados e identidade única do usuário |


