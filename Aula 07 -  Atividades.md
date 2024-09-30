# Aula Sobre Atividades BPMN

No BPMN (Business Process Model and Notation), atividades são elementos fundamentais que representam o trabalho que precisa ser feito em um processo de negócio. 
Elas são usadas para descrever tanto tarefas individuais quanto sub-processos dentro de um diagrama de processo. Cada atividade no BPMN é representada por um 
retângulo arredondado e pode ser categorizada em vários tipos específicos, dependendo da natureza do trabalho a ser realizado e da interação necessária. 

**Aqui estão os principais tipos de atividades no BPMN:**

## User Task

![image](https://github.com/user-attachments/assets/57d5575c-fa8b-4405-b77b-eb8f67e36e9c)

É uma atividade que necessita de interação direta do usuário com o sistema. Esse tipo de tarefa é frequentemente utilizado quando uma decisão manual é necessária.

**Exemplos**:
1. **Entrevistar Candidato**: Durante um processo de contratação, um recrutador realiza uma entrevista para avaliar as qualificações do candidato.
2. **Registrar Reclamação**: Um atendente registra os detalhes de uma reclamação do cliente para futura análise e resolução.

## Manual Task

![image](https://github.com/user-attachments/assets/c2e4ba25-22ae-4f89-a09c-0dab3e8f44d7)

Refere-se a uma tarefa que é executada manualmente, sem o auxílio de qualquer ferramenta ou sistema automatizado. Este tipo de tarefa é útil para representar atividades que dependem exclusivamente do esforço humano.

**Exemplos**:
1. **Preparar o Prato**: Um chef prepara uma refeição seguindo uma receita sem a ajuda de dispositivos automatizados.
2. **Analisar Amostras**: Um técnico de laboratório realiza testes em amostras biológicas, observando e registrando os resultados manualmente.

## Service Task

![image](https://github.com/user-attachments/assets/883c1e9c-c93c-434c-b19f-a1bd8b7a08ec)

Automatiza uma tarefa por meio de um serviço de software ou aplicação. Este tipo de tarefa é essencial em processos que requerem integração com sistemas de TI para realizar operações sem intervenção humana.

**Exemplos**:
1. **Verificação de Documentos**: Um sistema automatizado compara os documentos submetidos com dados em um banco de dados para validar a autenticidade.
2. **Validação de Pagamento**: Um sistema de e-commerce processa pagamentos verificando informações de cartão de crédito com o banco emissor.

## Send Task

![image](https://github.com/user-attachments/assets/4dcf7218-2c6d-4ce1-8b96-af2e86e5096c)

Uma tarefa que envia uma mensagem para outro processo ou participante. É geralmente usada para iniciar uma comunicação ou notificar outros sistemas ou participantes sobre um evento ou mudança de estado.

**Exemplos**:
1. **Enviar Ordem de Compra**: Automaticamente, o sistema envia uma ordem de compra ao fornecedor assim que a aprovação interna é concluída.
2. **Notificar Stakeholders**: Um sistema de gestão de projetos envia atualizações sobre o progresso do projeto para os investidores e partes interessadas.

## Receive Task

![image](https://github.com/user-attachments/assets/5949c45a-6c24-4b2a-94e2-5597d223b20b)


Espera por uma mensagem de outro processo ou participante externo. Esta tarefa é usada para sincronizar processos ou para ações que dependem de eventos externos.

**Exemplos**:
1. **Recepção da Confirmação do Pedido**: O sistema aguarda a confirmação de que o pedido foi recebido pelo fornecedor.
2. **Recepção de Sinistro**: A empresa de seguros espera receber um formulário de sinistro preenchido após um incidente reportado.

## Script Task

![image](https://github.com/user-attachments/assets/a763e468-b336-4d50-8d5c-10b09c78b963)


Executa um script ou código definido, automático e sem interação do usuário. É útil para processamento de dados, cálculos complexos ou operações de transformação.

**Exemplos**:
1. **Calcular Estatísticas**: Um script é executado para calcular estatísticas de vendas mensais.
2. **Reordenar Estoque**: Um script verifica os níveis de estoque e faz pedidos automaticamente quando os níveis estão abaixo de um limite predeterminado.

## Reference Task

![image](https://github.com/user-attachments/assets/1deec28c-e012-472a-9530-2c90ff4e562d)

Refere-se a uma tarefa que é definida uma vez e referenciada em vários lugares. Isso evita a duplicação de esforços e garante consistência em processos onde a mesma atividade é realizada em vários contextos.

**Exemplos**:
1. **Aprovação de Segurança**: Em diferentes processos de uma organização, a mesma tarefa de aprovação de segurança é realizada.
2. **Agendar Consulta**: Usada em diversos departamentos de um hospital para agendar consultas de forma padronizada.

## Sub-processos

![image](https://github.com/user-attachments/assets/0666f408-5338-466c-904d-93d5ff85dcaa)


Representam um conjunto de atividades que são agrupadas dentro de um processo maior, facilitando a organização e a modularidade dos processos.

### Embedded Sub-process

![image](https://github.com/user-attachments/assets/8dafe6d5-bec5-46d9-acc1-76922fba21f3)


Um sub-processo que é definido dentro de um processo maior e não pode existir independentemente. Ele é executado dentro do contexto do processo principal.

**Exemplos**:
1. **Revisão de Código**: Inclui várias tarefas menores, como revisar código, compilar e testar, todas agrupadas em um sub-processo.
2. **Organização do Evento**: Consiste em escolher o local, confirmar palestrantes e distribuir ingressos, todos agrupados como um sub-processo do processo de planejamento do evento.

### Reusable Sub-process

![image](https://github.com/user-attachments/assets/e3f1885a-b980-4c7d-b328-6a9a4a9ff898)


Um sub-processo que pode ser invocado em diferentes processos. Ele é definido uma vez e pode ser utilizado por vários processos diferentes, promovendo reusabilidade.

**Exemplos**:
1. **Onboarding de Funcionários**: Utilizado por diferentes departamentos para integrar novos funcionários.
2. **Processo de Compras**: Comum tanto para o departamento de TI quanto para recursos humanos para realizar compras de equipamentos e serviços.


### Exemplo

![image](https://github.com/user-attachments/assets/cacf162a-f3a8-436d-9fa3-5df4b975ff05)


![image](https://github.com/user-attachments/assets/32a5ee4b-76ca-4b23-b9be-e303e1cea9fe)

