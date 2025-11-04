1) **Cenários de Interação**
> **_NOTE:_**: destacar em negrito o texto alterado entre Cenário Problema e Cenário de Interação

2) **Design Centrado na Comunicação**

**Nome do Cenário: XXXXXX**

| tópico \> subtópico (diálogo) | falas e signos |
| :---- | :---- |
|  | U: Preciso … |
| \>  | U: Quero … D: Aqui está o mapa |
|  | U:  |
|  | U:  |
|  | D: Aqui está a informação filtrada |

3) **Mapa de Objetivos**
> **_NOTE:_**: cada um coloca seu mapa de objetivos e deverá ter um diagrama de consolidação

4) **Esquema Conceitual de Signos**

> **_NOTE:_**: fazer a junção das 3 tabelas abaixo em uma única

| Credenciais (C) \- credenciais para acesso ao sistema |  |  |
| :---- | :---- | :---- |
| **signo** | **origem** | **observações** |
| usuário | domínio |  |
| senha | domínio |  |

| Credenciais (C) \- credenciais para acesso ao sistema |  |  |  |
| :---- | :---- | :---- | :---- |
| **signo** | **Tipo de conteúdo** | **restrição sobre conteúdo** | **valor default** |
| usuário | texto | não pode ser nulo | — |
| senha | texto | não pode ser nulo | — |

| Credenciais (C) \- credenciais para acesso ao sistema |  |  |
| :---- | :---- | :---- |
| **signo** | **prevenção** | **recuperação** |
| usuário | PP: campo obrigatório | RA |
| senha | PP campo obrigatório  | RA |


---

---

## 🧩 1) Cenários de Interação

> **NOTE:** O texto alterado entre o *Cenário Problema* e o *Cenário de Interação* está em **negrito**.

### **Cenário Problema**
Usuários da Ecologic Smoke têm dificuldade em acompanhar o estado dos seus produtos e saber quando repor seus itens essenciais (sedas, tabacos e acessórios).  
A experiência atual, feita por redes sociais e mensagens manuais, causa **ruídos comunicativos**, falta de clareza nas promoções e perda de oportunidades de recompra.

### **Cenário de Interação**
No app **SelvaCheck**, o usuário realiza o “check-up” do seu kit.  
O sistema interpreta as interações, **reconhece o nível de estoque pessoal** e comunica de forma simbólica, através de ícones e cores (verde → saudável, amarelo → médio, vermelho → zerado).  
Quando o kit está baixo, o app emite **alertas visuais e verbais**, convidando o usuário a repor no iFood com um toque.  
Esse novo modelo de interação elimina as **rupturas comunicativas**, pois **traduz o status do usuário em signos visuais intuitivos**, mantendo o diálogo contínuo entre sistema e consumidor.

---

## 💬 2) Design Centrado na Comunicação

**Nome do Cenário:** *Check-up do Kit — Comunicação entre Usuário e Sistema SelvaCheck*

| tópico > subtópico (diálogo) | falas e signos |
| :---- | :---- |
| U: Abre o app SelvaCheck | D: Exibe a tela inicial com o status do kit (barras de energia 🌿🟢🟡🔴) |
| > | U: “Quero saber o estado do meu kit”  D: “Aqui está o mapa do seu estoque atual — sedas, tabacos e piteiras” |
|  | U: “E se tiver baixo?” |
|  | D: Exibe alerta visual **(ícone vermelho e frase: “Seu kit tá zerando!”)** |
|  | U: “Quero repor agora” |
|  | D: **Abre CTA direto pro iFood (‘Repor Agora na Selva 🚀’) e registra o comportamento de compra.** |

**Interpretação Semiótica:**  
Cada ícone e cor representa um signo que media a comunicação.  
A cor, o tom e o texto trabalham como camadas simbólicas, evitando rupturas — o usuário **entende sem precisar ler instruções**.

---

## 🎯 3) Mapa de Objetivos

### **Objetivo Central**
Facilitar a interação do usuário com seu estoque pessoal de produtos Ecologic, reduzindo ruídos comunicativos e incentivando a recompra.

### **Objetivos do Usuário**
- Visualizar facilmente o estado do kit  
- Receber sugestões automáticas de reposição  
- Comprar com praticidade (1 clique)  
- Ganhar recompensas e promoções personalizadas  

### **Objetivos do Sistema**
- Interpretar as ações do usuário  
- Comunicar o status do kit por signos visuais (cores, ícones, animações)  
- Enviar alertas e sugestões no momento certo  
- Manter um canal de compra ativo com o iFood  

**Fluxo Resumido:**  
Usuário → Interage com Dashboard → Sistema interpreta → Exibe signos (cores, mensagens, ícones) → Usuário reage → Sistema gera CTA → Retorno (recompra).  

---

## 🌀 4) Esquema Conceitual de Signos

> **NOTE:** Junção das três tabelas solicitadas no documento acadêmico.

| **Signo** | **Origem** | **Tipo de Conteúdo** | **Restrição** | **Valor Default** | **Prevenção** | **Recuperação** | **Observações** |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| usuário | domínio | texto | não pode ser nulo | — | PP: campo obrigatório | RA: solicitação de novo login | Credencial primária de acesso |
| senha | domínio | texto | não pode ser nulo | — | PP: campo obrigatório | RA: redefinir senha via e-mail | Credencial de segurança |
| status do kit | sistema | icônico (barras coloridas) | sempre ativo | 🟢 | PA: mudança automática por leitura de estoque | RA: atualização manual | Signo visual que representa a saúde do kit |
| alerta de estoque | sistema | texto + ícone | ativa quando estoque < 30% | — | AL: mensagem “Kit quase zerando!” | RA: botão “Atualizar agora” | Prevenção apoiada, reforça engajamento |
| botão iFood CTA | sistema | interativo | não pode estar inativo | “Repor Agora no iFood” | PP: sempre visível | RA: recarregar interface | Ação principal de conversão |
| ícone tribal | visual | simbólico | — | 🐨 | PA: reforço de identidade da selva | — | Signo cultural da marca |

---

## ⚙️ 5) Aplicação dos Conceitos de Prevenção e Recuperação

| Tipo | Descrição | Aplicação no App |
| :---- | :---- | :---- |
| **PP (Prevenção Passiva)** | O sistema evita erros por estrutura. | Campos obrigatórios no login e bloqueio de ações sem dados. |
| **PA (Prevenção Ativa)** | O sistema interpreta e corrige comportamentos antes do erro. | Atualização automática do status do kit. |
| **AL (Prevenção Apoiadora)** | Alertas comunicam estados de risco. | Mensagens de “kit quase zerando” e ícones vermelhos. |
| **RA (Recuperação Apoiadora)** | Permite corrigir uma ação com ajuda. | Botão “Atualizar agora” ou “Repor no iFood”. |
| **CE (Captura de Erro)** | O sistema reconhece e registra erros. | Logs de tentativa de compra falha e falha de login. |

---

## 📚 6) Resumo do Modelo Conceitual

O app **SelvaCheck** cria um ecossistema simbólico entre **usuário (U)** e **dispositivo (D)**, onde signos visuais e verbais mediam a comunicação.  
Cada elemento da interface (ícone, cor, alerta, texto) é um **signo de interação**, permitindo **interpretação imediata e resposta emocional**.  

Esse modelo garante:
- **Fluidez comunicativa**  
- **Redução de ruídos**  
- **Maior sensação de pertencimento à tribo Ecologic**


