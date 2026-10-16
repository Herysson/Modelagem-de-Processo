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

## Exercícios

Aqui estão cinco exercícios envolvendo a utilização dos elementos BPMN que foram apresentados, ideais para ajudar os alunos a aplicar e entender melhor esses conceitos em cenários práticos:

### Exercício 1: Mapeamento de Processo de Compra
**Descrição**: Desenhe um diagrama BPMN para um processo de compra simples em uma empresa. O processo deve começar com uma "Tarefa de Usuário" para a solicitação de compra, seguida por uma "Tarefa de Serviço" para a verificação automática de fundos, uma "Tarefa de Envio" para enviar o pedido ao fornecedor, e uma "Tarefa de Recebimento" para confirmar o recebimento do pedido.

**Objetivos**:
- Identificar e utilizar diferentes tipos de tarefas.
- Entender o fluxo de mensagens entre atividades.

### Exercício 2: Processo de Onboarding de Funcionários
**Descrição**: Modele um processo de onboarding para novos funcionários utilizando BPMN. O processo deve incluir uma "Tarefa de Usuário" para o preenchimento de documentos pelo novo funcionário, uma "Tarefa Manual" para a revisão física desses documentos por um RH, e um "Sub-processo Incorporado" que agrupa as atividades de treinamento.

**OBS**: Onboarding é o processo de integrar novos funcionários em uma organização e ajudá-los a se adaptar aos aspectos sociais e de desempenho de seus novos empregos de forma rápida e suave. Ele vai além da simples orientação e inclui todo o processo durante o qual o novo colaborador aprende as competências necessárias para se tornar um membro efetivo da equipe.

**Objetivos**:
- Aplicar tarefas manuais e de usuário em um contexto prático.
- Utilizar sub-processos para organizar o diagrama.

### Exercício 3: Automação de Relatório de Vendas
**Descrição**: Crie um diagrama BPMN para o processo de geração e distribuição de um relatório de vendas mensal. O processo deve iniciar com uma "Tarefa de Script" para coletar dados de vendas, seguida por uma "Tarefa de Serviço" para gerar o relatório, e uma "Tarefa de Envio" para distribuir o relatório por e-mail aos stakeholders.

**Objetivos**:
- Utilizar tarefas de script para processamento de dados.
- Demonstrar o uso de tarefas de serviço e de envio em processos automatizados.

### Exercício 4: Agendamento de Consultas Médicas
**Descrição**: Desenvolva um diagrama BPMN para o processo de agendamento de consultas em um hospital. Este processo deve incluir uma "Tarefa de Usuário" para que os pacientes possam solicitar uma consulta, uma "Tarefa de Referência" para verificar a disponibilidade do médico, e um "Sub-processo Reutilizável" para o processo de confirmação da consulta.

**Objetivos**:
- Incorporar tarefas de referência para reutilização de processos.
- Desenvolver a habilidade de modelar sub-processos reutilizáveis.

### Exercício 5: Revisão de Código em Desenvolvimento de Software
**Descrição**: Elabore um diagrama BPMN que modele o processo de revisão de código em um projeto de software. O processo deve começar com uma "Tarefa de Usuário" para submissão de código, seguido por um "Sub-processo Incorporado" para revisão de código que inclui tarefas de usuário e tarefas de script para análises automatizadas, e termina com uma "Tarefa de Usuário" para aprovação ou rejeição do código revisado.

**Objetivos**:
- Aplicar sub-processos incorporados em um fluxo de trabalho complexo.
- Integrar diferentes tipos de tarefas para simular um ambiente de trabalho real.

### Desafio 1: Geladeira Solidária: Resgate de Alimentos
Uma universidade desenvolveu um projeto chamado Geladeira Solidária, cujo objetivo é reduzir o desperdício de alimentos. Por meio de uma plataforma digital, as cantinas podem disponibilizar refeições e lanches que não foram comercializados, mas que ainda estão próprios para consumo.
Esses alimentos são encaminhados para organizações sociais parceiras, responsáveis por sua distribuição.
O processo começa quando um funcionário da cantina acessa o sistema e cadastra os alimentos disponíveis para doação, informando a quantidade, o tipo de alimento e o horário limite para consumo.
Após o cadastro, o sistema executa automaticamente um script que calcula o tempo restante para o vencimento dos alimentos e classifica a urgência da doação.
Em seguida, um serviço automatizado consulta o cadastro de organizações parceiras e verifica se existe alguma organização habilitada para receber os alimentos naquela região.
Caso nenhuma organização seja encontrada, o sistema registra a impossibilidade da doação e encerra o processo.
Caso exista uma organização disponível, o sistema envia uma mensagem contendo as informações dos alimentos oferecidos e aguarda uma resposta da organização.
A organização poderá aceitar ou recusar a doação.
Se a oferta for recusada, o sistema registra a recusa e encerra a solicitação.
Se for aceita, o funcionário da cantina deverá preparar a doação. Essa etapa compreende a separação dos alimentos, a conferência das embalagens e o acondicionamento dos produtos para transporte.
Após a preparação, o funcionário acessa a plataforma e confirma que os alimentos estão prontos para retirada.
O sistema gera automaticamente um código de identificação da doação e envia uma notificação à organização parceira, informando que os alimentos podem ser retirados.
Quando o representante da organização chega à cantina, o funcionário realiza a entrega física dos alimentos e registra a retirada no sistema.
O processo é encerrado quando a entrega é confirmada.

**Atividade proposta**
Elabore um diagrama BPMN que represente todo o processo de doação de alimentos descrito.
Na modelagem, procure utilizar corretamente os diferentes tipos de tarefas estudados nesta aula, distinguindo as atividades humanas executadas com auxílio do sistema daquelas realizadas manualmente e das operações automatizadas.
A etapa de preparação da doação deverá ser representada por um subprocesso incorporado (Embedded Sub-process), contendo as atividades de separação, conferência e acondicionamento dos alimentos.
Utilize pools e lanes para representar os participantes do processo e os respectivos responsáveis.

### Desafio 2: Produção de Protótipos em Impressoras 3D
Uma universidade possui um laboratório de fabricação digital chamado Fábrica de Ideias, no qual estudantes e professores podem solicitar a produção de protótipos utilizando impressoras 3D.
Para organizar a utilização dos equipamentos, o laboratório desenvolveu um sistema que gerencia solicitações, analisa arquivos digitais e acompanha o processo de fabricação.
O processo começa quando um estudante acessa a plataforma, preenche uma solicitação e envia um arquivo digital contendo o modelo 3D que deseja fabricar.
Após receber a solicitação, o sistema utiliza um serviço automatizado para verificar se o arquivo enviado possui um formato válido e se suas dimensões são compatíveis com as impressoras disponíveis.
Caso o arquivo apresente problemas, o sistema informa ao estudante que a solicitação não pode ser processada, permitindo que ele envie uma nova versão do arquivo.
Quando o arquivo está correto, o sistema executa um script para calcular a quantidade estimada de material necessário, o tempo de impressão e o custo aproximado da fabricação.
Em seguida, o sistema envia ao estudante uma mensagem contendo o orçamento e aguarda sua confirmação.
Se o orçamento for recusado, a solicitação é cancelada.
Caso o estudante aprove o orçamento, o sistema registra a autorização para fabricação e encaminha a solicitação para a equipe do laboratório.
Antes de iniciar a fabricação, um técnico deverá realizar o procedimento de Inspeção de Segurança dos Equipamentos. Esse procedimento é padronizado e também utilizado em outros processos do laboratório, como manutenção preventiva e treinamento de novos operadores.
Após a inspeção, inicia-se a produção do protótipo, composta pelas seguintes atividades:
- O técnico prepara manualmente a impressora, verificando o material e as condições da mesa de impressão.
- O sistema envia automaticamente o arquivo de fabricação para a impressora 3D.
- A impressora executa a fabricação da peça.
- Após a impressão, o técnico remove manualmente a peça e realiza sua inspeção visual.
- O técnico registra no sistema se o protótipo foi produzido corretamente.
Se a peça apresentar defeitos, o técnico verifica se existe material e tempo disponíveis para realizar uma nova tentativa. Caso seja possível, a peça retorna à etapa de fabricação. Se não for possível, a solicitação é encerrada como não concluída, e o estudante é notificado.
Se a peça estiver correta, o sistema registra a fabricação como concluída e envia uma notificação ao estudante informando que o protótipo está disponível para retirada.
Quando o estudante comparece ao laboratório, o técnico entrega a peça e registra a retirada no sistema, encerrando o processo.

**Atividade proposta**
Elabore um diagrama BPMN para representar o processo de fabricação de protótipos da Fábrica de Ideias.
O diagrama deverá empregar os tipos de tarefas apropriados para cada atividade, considerando operações humanas e automatizadas, trocas de mensagens, decisões e retornos no fluxo.
Represente o procedimento Inspeção de Segurança dos Equipamentos como uma atividade de chamada (Call Activity), que permita reutilizar um processo previamente definido.
Já a etapa de produção do protótipo deverá ser representada por um subprocesso incorporado (Embedded Sub-process), detalhando internamente as atividades de preparação da impressora, fabricação, remoção e inspeção da peça.
Organize os participantes em pools e lanes e represente os diferentes resultados possíveis da solicitação.


## Referências

1. Bizagi. (n.d.). *Modeler Video List*. Recuperado de [https://www.bizagi.com/pt/home/modeler-video-list.html](https://www.bizagi.com/pt/home/modeler-video-list.html)
2. Bizagi. (n.d.). *My First Model Tutorial*. Recuperado de [https://help.bizagi.com/platform/en/index.html?my_first_model.htm](https://help.bizagi.com/platform/en/index.html?my_first_model.htm)
3. Bizagi. (n.d.). *BPMN Quick Reference Guide*. Recuperado de [https://resources.bizagi.com/docs/BPMN_Quick_Reference_Guide_ENG.pdf](https://resources.bizagi.com/docs/BPMN_Quick_Reference_Guide_ENG.pdf)


