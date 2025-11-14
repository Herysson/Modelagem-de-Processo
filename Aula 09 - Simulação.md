## 1. Cenário: Atendimento em uma Cafeteria (genérica)

### Contexto

Uma cafeteria de médio porte recebe muitos clientes em um curto intervalo de tempo nos horários de pico (por exemplo, entre 8h e 9h da manhã). A gerência quer entender:

* quanto tempo o cliente passa dentro do processo,
* onde surgem filas e gargalos,
* que mudanças de recursos ou de processo podem melhorar o atendimento.

### Visão geral do processo

Fluxo típico de um cliente:

1. Chega à cafeteria
2. Entra na fila do atendimento
3. Faz o pedido
4. Realiza o pagamento
5. Aguarda preparo do pedido
6. Retira o pedido
7. Sai da cafeteria

### Atividades (para BPMN)

* **Chegada do cliente** (evento de início)
* **Entrar na fila**
* **Atender cliente (pedido + pagamento)**
* **Preparar pedido**
* **Entregar pedido**
* **Fim do atendimento** (evento de fim)

Opcional: você pode separar “Pedido” e “Pagamento” em duas tarefas diferentes se quiser explorar otimizações depois.

### Lanes (piscinas/faixas)

* **Cliente**
* **Atendente de balcão/caixa**
* **Barista/Cozinha** (quem prepara cafés e lanches)

---

## 2. Dados para simulação no Bizagi

Use valores simples, que os alunos entendem fácil (e depois podem alterar):

### Chegadas

* Período de simulação de interesse: **pico de 60 minutos** (por exemplo, 8h–9h).
* Aproximadamente **80 clientes em 1 hora** → ~1,33 cliente/minuto.

  * No Bizagi: taxa de chegada ou distribuição de chegadas ao longo de 60 minutos.

### Tipos de pedido (com probabilidades)

* 40% – **Café simples** (apenas bebida)
* 35% – **Café + lanche**
* 25% – **Lanche + bebida especial** (por exemplo, cappuccino, frappé)

### Tempos médios (atividade)

Pode usar tempos médios ou distribuições, mas como primeira aula, média fixa já serve:

* **Atender cliente (pedido + pagamento)**: 2 minutos por cliente
* **Preparo:**

  * Café simples: 1,5 minuto
  * Café + lanche: 3 minutos
  * Lanche + bebida especial: 4 minutos
* **Entregar pedido ao cliente**: 0,5 minuto

### Recursos

* **Atendentes de balcão (caixa)**: 1 (cenário base)
* **Baristas / Cozinha**: 2 (cenário base)

Depois, na parte de otimização, os alunos podem testar:

* 2 caixas
* 3 baristas
* Redistribuição de atividades, etc.

---

## 3. Métricas interessantes para análise

Quando rodar a simulação no Bizagi focarem em:

* Tempo médio total do processo (chegada → pedido pronto)
* Tempo médio de espera na fila de atendimento
* Tempo médio de espera pelo preparo
* Utilização dos recursos:

  * % de ocupação do atendente de balcão
  * % de ocupação dos baristas
* Tamanho médio e máximo das filas
