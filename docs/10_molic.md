**Nome do Cenário:**  
**Diagrama:**

> **_NOTE:_**: 1 solução completa por pessoa da equipe

🌿 MOLIC 1 — Login e Acesso Personalizado

Nome do Cenário: Acesso à Selva 🌱
Objetivo: Permitir que o usuário entre no sistema com autenticação segura e sinta o início da experiência personalizada.

flowchart TD
    U1([U: Abre o aplicativo da Ecologic Smoke]) --> D1([D: Exibe tela de login])
    D1 --> U2([U: Insere usuário e senha])
    U2 --> D2([D: Valida credenciais])
    D2 -->|Credenciais válidas| D3([D: Exibe mensagem de boas-vindas "Bem-vindo à Selva, Coala! 🐨🔥"])
    D2 -->|Erro| D4([D: Exibe mensagem de erro e opção "Esqueceu a senha?"])
    D3 --> U3([U: Acessa o painel principal])
    D4 --> U4([U: Tenta novamente ou redefine senha])
    U3 --> D5([D: Mostra recomendações personalizadas com base no perfil])
    D5 --> END([Fim do fluxo ✅])


Descrição resumida:
Usuário realiza o login no app da Ecologic Smoke. O sistema valida suas credenciais e fornece um acesso imersivo à “Selva”, com mensagens personalizadas e CTA para o painel principal.

🌿 MOLIC 2 — Reposição Inteligente (“Saúde do Kit”)

Nome do Cenário: Saúde do Kit 🌿
Objetivo: Acompanhar o uso dos produtos e recomendar automaticamente reposição de acordo com o consumo.

flowchart TD
    U1([U: Abre a aba 'Saúde do Kit']) --> D1([D: Exibe status atual do kit e consumo médio])
    D1 --> D2([D: Mostra botão 'Ver recomendações'])
    U2([U: Clica em 'Ver recomendações']) --> D3([D: Analisa dados de consumo e gera sugestões])
    D3 --> D4([D: Exibe opções de combos e reposição personalizada])
    D4 --> U3([U: Escolhe opção de compra ou ignora])
    U3 -->|Aceita| D5([D: Redireciona para checkout no iFood])
    U3 -->|Recusa| D6([D: Oferece cupom extra ou montagem manual])
    D5 --> U4([U: Finaliza pedido])
    U4 --> D7([D: Mostra mensagem de agradecimento e convite para comunidade])
    D7 --> END([Fim ✅])


Descrição resumida:
O sistema lê o histórico do usuário e recomenda o reabastecimento do kit conforme o uso. Caso o cliente não aceite, o app aciona gatilhos de desconto e personalização para reter o engajamento.

🌿 MOLIC 3 — Fidelização e Comunidade da Selva

Nome do Cenário: Convite à Tribo 🐨
Objetivo: Converter compradores em membros da comunidade Ecologic Smoke (via WhatsApp/Discord).

flowchart TD
    U1([U: Finaliza uma compra]) --> D1([D: Exibe tela de agradecimento personalizada])
    D1 --> D2([D: Exibe convite para 'Entrar na Tribo'])
    U2([U: Clica em 'Entrar na Tribo']) --> D3([D: Redireciona para grupo da comunidade])
    D3 --> D4([D: Exibe badge de 'Novo Coala 🌿'])
    D4 --> U3([U: Entra na comunidade e envia primeira mensagem])
    U3 --> D5([D: Envia mensagem automática de boas-vindas e regras da selva])
    D5 --> D6([D: Exibe pontos de fidelidade e próximos desafios])
    D6 --> U4([U: Interage e compartilha feedback ou fotos dos produtos])
    U4 --> D7([D: Registra engajamento e libera recompensa exclusiva])
    D7 --> END([Fim do fluxo ✅])


Descrição resumida:
Após a compra, o usuário é convidado a integrar a comunidade “Selva da Ecologic”. Dentro dela, ele ganha badges, pontos e recompensas que estimulam a participação e reforçam o senso de pertencimento à tribo.

Resumo Geral dos MOLICs
MOLIC	Nome do Cenário	Objetivo Central	Resultado Esperado
1	Login e Acesso Personalizado	Iniciar a jornada com imersão e segurança	Usuário autenticado e ambientado
2	Saúde do Kit	Estimular recompra e reabastecimento	Conversão e retenção de clientes
3	Convite à Tribo	Criar engajamento e fidelização pós-compra	Usuário ativo na comunidade
