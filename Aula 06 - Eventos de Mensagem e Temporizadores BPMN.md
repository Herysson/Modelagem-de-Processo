### Aula sobre Elementos de Eventos de Mensagem e Timer em BPMN

Nesta aula, vamos explorar os elementos de eventos relacionados a mensagens e timers na notação BPMN (Business Process Model and Notation). Esses eventos são cruciais para representar as interações baseadas em tempo e comunicação em processos de negócios.

#### 1. Eventos de Mensagem (Message Events)

**Message Start Event**

![image](https://github.com/user-attachments/assets/f344afeb-c1d7-42af-b35a-fc1b34baab61)


- **Descrição**: Este evento é utilizado para iniciar um processo com base no recebimento de uma mensagem. Ele é representado por um círculo com um envelope no meio.
- **Exemplo**: Imagine um processo de solicitação de serviço de TI que começa quando um ticket é recebido. O "Message Start Event" seria ativado ao receber esse ticket, iniciando o processo de atendimento.

**Message Intermediate Event (Sent/Received)**

![image](https://github.com/user-attachments/assets/340fc075-b07d-4d5e-b58f-c55ccfad0517)  ![image](https://github.com/user-attachments/assets/0b3dc6a7-0869-4323-9dc9-b46d24140cf8)



- **Descrição**: Os eventos intermediários de mensagem podem ser de dois tipos: envio (sent) ou recebimento (received). São utilizados para modelar o ponto em um processo onde uma mensagem é enviada ou recebida, afetando o fluxo do processo.
- **Exemplo**:
 
![image](https://github.com/user-attachments/assets/340fc075-b07d-4d5e-b58f-c55ccfad0517)  **Sent**: Durante um processo de pedido de compra, um evento de mensagem intermediário de envio pode ocorrer após a aprovação do pedido, onde uma ordem de compra é enviada ao fornecedor.
    
![image](https://github.com/user-attachments/assets/0b3dc6a7-0869-4323-9dc9-b46d24140cf8) **Received**: No mesmo processo, um evento de mensagem intermediário de recebimento pode modelar a chegada da confirmação do fornecedor, que então leva à próxima etapa do processo.

**Message End Event**

![image](https://github.com/user-attachments/assets/cef6a9fb-75e7-4f1a-8242-82361c32e2a1)

- **Descrição**: Este evento é utilizado para indicar o fim de um processo devido ao envio de uma mensagem. É representado por um círculo com uma borda grossa e um envelope no centro.
- **Exemplo**: Em um processo de reclamação de cliente, o processo pode terminar com o envio de uma mensagem de confirmação de resolução para o cliente.

#### 2. Eventos de Timer (Timer Events)

**Timer Start Event**

![image](https://github.com/user-attachments/assets/0f3b99e3-ec49-435e-b74b-c218856cc553)


- **Descrição**: Um evento de início com timer é usado para iniciar um processo em um momento específico ou após um período de tempo definido. É representado por um círculo com um relógio no meio.
- **Exemplo**: Um processo de geração de relatório financeiro mensal pode ser iniciado automaticamente no primeiro dia de cada mês através de um "Timer Start Event".

**Timer Intermediate Event**

![image](https://github.com/user-attachments/assets/7f82cb90-72cb-4380-9469-4813190ce501)

- **Descrição**: Este evento é utilizado para modelar uma espera ou atraso dentro de um processo até que ocorra um determinado momento ou período de tempo. É representado por um círculo com borda dupla e um relógio no centro.
- **Exemplo**: Em um processo de aprovação de empréstimo, um evento intermediário com timer pode ser configurado para pausar o processo por dois dias úteis, dando tempo para a realização de verificações de crédito antes de prosseguir com a aprovação ou rejeição.

Na imagem, você observa um exemplo de um **Evento de Mensagem Anexado** a uma atividade em um diagrama BPMN. Esse evento é representado pelo círculo com um ícone de envelope, colocado na borda da tarefa chamada "Tarefa 1".

## Evento Anexado?

![image](https://github.com/user-attachments/assets/0d01b037-9eb0-4bab-8755-5ac7b08ada9f)

Um evento anexado, também conhecido como **evento de fronteira**, é um evento que está diretamente conectado à fronteira de uma atividade (tarefa ou subprocesso) em um diagrama BPMN. Este evento não interrompe o fluxo principal do processo; em vez disso, ele monitora condições ou circunstâncias que podem ocorrer enquanto a atividade está sendo executada.

### Funcionamento e Tipos
- **Eventos de Mensagem Anexados**: Especificamente, o evento de mensagem anexado pode ser configurado para agir quando uma mensagem específica é recebida. Ele pode interromper a tarefa à qual está anexado ou prosseguir em paralelo, dependendo se é um evento de interrupção ou não interrupção.
  - **Interrupção**: Quando o evento de mensagem ocorre, a atividade principal é interrompida e o controle do processo é transferido para o caminho definido pelo evento.
  - **Não Interrupção**: A atividade principal continua, mas um novo caminho de fluxo é iniciado em paralelo com a atividade original.

### Exemplo Prático 1 
Considerando a "Tarefa 1" como uma atividade onde um usuário precisa preencher um formulário e, durante essa tarefa, uma mensagem de atualização de dados pode ser necessária:
- **Cenário com Interrupção**: Se a mensagem de atualização de dados é considerada crítica e requer interrupção imediata para processamento, então o evento de mensagem anexado interromperia a "Tarefa 1" e redirecionaria o fluxo para um caminho alternativo para tratar essa atualização.
- **Cenário sem Interrupção**: Se a mensagem pode ser tratada em paralelo sem interromper a atividade principal, então a tarefa continua e a mensagem é processada simultaneamente em um fluxo paralelo.

### Exemplo Prático 2
Considere a "Tarefa 2" como uma atividade em que um funcionário deve completar um relatório. Se houver um prazo definido para essa tarefa, um evento de timer anexado pode ser usado para lembrar o funcionário de que o prazo está se aproximando ou para automaticamente encaminhar o relatório para revisão após um certo tempo, garantindo que os prazos sejam respeitados.

### Importância
Eventos anexados são essenciais para modelar exceções e ações paralelas que precisam ser consideradas sem necessariamente interromper o fluxo principal de atividades em um processo. Eles oferecem flexibilidade ao modelar processos que exigem resposta a eventos externos ou mensagens durante a execução de tarefas específicas, permitindo assim uma modelagem mais precisa e dinâmica do comportamento do processo.

## Referências

1. Bizagi. (n.d.). *Modeler Video List*. Recuperado de [https://www.bizagi.com/pt/home/modeler-video-list.html](https://www.bizagi.com/pt/home/modeler-video-list.html)
2. Bizagi. (n.d.). *My First Model Tutorial*. Recuperado de [https://help.bizagi.com/platform/en/index.html?my_first_model.htm](https://help.bizagi.com/platform/en/index.html?my_first_model.htm)
3. Bizagi. (n.d.). *BPMN Quick Reference Guide*. Recuperado de [https://resources.bizagi.com/docs/BPMN_Quick_Reference_Guide_ENG.pdf](https://resources.bizagi.com/docs/BPMN_Quick_Reference_Guide_ENG.pdf)







