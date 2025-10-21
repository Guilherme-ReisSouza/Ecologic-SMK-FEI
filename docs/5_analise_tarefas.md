# Análise de Tarefas

> **_NOTE:_**: A equipe deve descrever as funcionalidades mais importantes da interface/produto. A equipe deve modelar pelo menos 1 HTA, 1 GOMS e 1 CTT (de pelo menos 4 funcionalidades diferentes). Cada diagrama deve ter um texto explicando a funcionalidade.

1. HTA
2. GOMS
3. CTT

---

# ⚙️ Análise de Tarefas — Ecologic Smoke  
*(Baseado em Barbosa & Silva, 2010 – Disciplina CC8122 / FEI)*

---

## 🧭 Introdução

A **Análise de Tarefas** tem como objetivo compreender **como os usuários executam suas atividades dentro da interface** e **por que as realizam dessa maneira**, identificando possíveis falhas de usabilidade e oportunidades de melhoria.

Os modelos utilizados — **HTA (Hierarchical Task Analysis)**, **GOMS** e **CTT (ConcurTaskTrees)** — foram aplicados para mapear as principais funcionalidades da plataforma **Ecologic Smoke**, um ecossistema digital que une **marketplace, comunidade e sistema de recompensas**.

---

## 🔹 HTA — Hierarchical Task Analysis  
### Funcionalidade: Efetuar Compra com Sistema de Pontos

A Análise Hierárquica de Tarefas (HTA) descreve as etapas necessárias para o usuário realizar uma compra de produto utilizando pontos de fidelidade.  
O objetivo é identificar gargalos de interação e oportunidades de otimização da experiência de compra.

---

### 🧩 Diagrama HTA

```mermaid
graph TD
    A0["0. Efetuar compra com pontos (1>2>3)"]
    A1["1. Selecionar produto e adicionar ao carrinho (1+2)"]
    A2["2. Escolher forma de pagamento"]
    A3["3. Confirmar e finalizar a compra"]

    A1 --> A1_1["1.1. Explorar catálogo e aplicar filtros"]
    A1 --> A1_2["1.2. Visualizar detalhes e clicar em 'Adicionar ao carrinho'"]

    A2 --> A2_1["2.1. Selecionar PIX / Cartão / Pontos"]
    A2 --> A2_2["2.2. Confirmar uso de pontos de fidelidade"]

    A3 --> A3_1["3.1. Revisar resumo da compra"]
    A3 --> A3_2["3.2. Confirmar pagamento"]
    A3 --> A3_3["3.3. Receber feedback de confirmação e saldo atualizado"]
````

---

### 📋 Tabela Explicativa

| Nível   | Objetivo / Operação         | Problemas Identificados           | Recomendações IHC                           |
| ------- | --------------------------- | --------------------------------- | ------------------------------------------- |
| **0**   | Efetuar compra com pontos   | Processo dividido em várias telas | Unificar checkout em uma única página       |
| **1**   | Selecionar produto          | Filtros lentos e confusos         | Implementar filtros dinâmicos e responsivos |
| **1.1** | Explorar catálogo           | Carregamento lento de imagens     | Otimizar cache e imagens                    |
| **2**   | Escolher forma de pagamento | Dúvida sobre saldo de pontos      | Exibir saldo de pontos durante o checkout   |
| **3**   | Finalizar compra            | Falta de mensagem de confirmação  | Incluir feedback visual e sonoro            |

**Plano:**
Para concluir a tarefa principal **(0)**, o usuário deve seguir a sequência:
1️⃣ Selecionar produto (**1**) → 2️⃣ Escolher forma de pagamento (**2**) → 3️⃣ Confirmar e finalizar a compra (**3**).

**Input:** Usuário autenticado e produto disponível no catálogo.
**Feedback:** Mensagem de sucesso e saldo de pontos atualizado.

---

### 💬 Interpretação

A HTA mostra que o processo atual exige múltiplas interações e telas separadas.
A recomendação é consolidar o fluxo de pagamento em **uma única tela**, com **feedback imediato** a cada ação, reduzindo o esforço cognitivo do usuário.

---

## 🔹 GOMS — Goals, Operators, Methods and Selection Rules

### Funcionalidade: Montar Box Personalizado

O modelo GOMS identifica **os objetivos, operadores, métodos e regras de seleção** necessários para que o usuário crie um box mensal de produtos personalizados.
Este processo reflete a funcionalidade de personalização e fidelização do sistema Ecologic Smoke.

---

### 🧠 Estrutura GOMS

**GOAL 0:** Criar um box mensal personalizado.

* **GOAL 1:** Selecionar categorias de produtos

  * **METHOD 1.A:** Escolher categorias fixas (papel, ervas, acessórios)
    *(SEL. RULE: o usuário já sabe o tipo de produto que deseja)*
  * **METHOD 1.B:** Utilizar sugestões automáticas do sistema
    *(SEL. RULE: o usuário não possui preferências definidas)*

* **GOAL 2:** Personalizar quantidade e tipo de itens

  * **OP. 2.1:** Ajustar quantidade via controle “+ / –”
  * **OP. 2.2:** Visualizar valor total e pontos em tempo real

* **GOAL 3:** Confirmar e salvar box

  * **OP. 3.1:** Clicar em “Salvar Box”
  * **OP. 3.2:** Receber feedback visual de confirmação

---

### 💡 Interpretação

O modelo GOMS evidencia que o processo de montagem do box exige **decisões repetitivas e cognitivamente custosas**.
A solução proposta é implementar **sugestões automáticas de produtos** com base em compras anteriores e **feedbacks em tempo real**, otimizando o tempo e reduzindo a carga mental do usuário.

---

## 🔹 CTT — Concur Task Trees

### Funcionalidades:

(A) Compra de Produto
(B) Participar de Evento
(C) Interagir na Comunidade
(D) Gerenciar Pedidos de Parceiros

O modelo **CTT** descreve as tarefas concorrentes e dependentes que ocorrem simultaneamente entre o usuário, o sistema e os parceiros comerciais.

---

### 🌐 Diagrama Textual CTT

**Relações de Tarefas:**

* T1 >> T2 → T2 inicia após T1 terminar.
* T1 [ ] >> T2 → T1 passa informações a T2.
* T1 ||| T2 → tarefas podem ocorrer em paralelo.
* T1 |> T2 → T1 pode ser pausada por T2.

---

```mermaid
graph TD
    T0["T0 — Interagir com o Ecossistema Ecologic Smoke"]

    T1["T1 — Explorar catálogo de produtos"]
    T2["T2 — Realizar compra [ ] >>"]
    T3["T3 — Gerar pontos de fidelidade"]
    T4["T4 — Participar de eventos"]
    T5["T5 — Interagir na comunidade"]
    T6["T6 — Parceiro gerenciar estoque consignado"]
    T7["T7 — Emitir relatório de vendas"]

    T0 --> T1
    T1 --> T2
    T2 --> T3
    T0 --> T4
    T0 --> T5
    T6 --> T7

    T4 -. concorrente .-> T5
```





