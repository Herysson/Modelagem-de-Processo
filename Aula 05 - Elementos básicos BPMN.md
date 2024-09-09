## Elementos Básicos do BPMN

Com base no guia de referência rápida do BPMN, vamos explorar os elementos principais da notação BPMN (Business Process Model and Notation). 
Esses elementos são a base para modelagem de processos de negócios e fornecem uma representação visual clara dos fluxos de trabalho dentro de uma organização.

---

### **Atividades (Tarefas / Task)**

As atividades representam o trabalho realizado por uma organização; são um passo dentro do processo. As atividades podem ser atômicas ou compostas.


#### **Tarefa**: Representa uma única unidade de trabalho. Pode ser manual ou automatizada. Exemplo: preencher um formulário.
  - Representação: Um retângulo com bordas arredondadas.
    
![image](https://github.com/user-attachments/assets/267a9d87-b160-4ef8-be36-b142996f257c)


#### **Subprocesso**: É uma atividade composta cujo detalhe é definido como um fluxo de outras atividades, ou agrupamento de tarefas menores dentro de um processo maior, o que permite que o processo seja dividido em partes gerenciáveis.
  - Representação: Um retângulo com um símbolo de mais '+' no centro.

![image](https://github.com/user-attachments/assets/be554e44-beb5-4564-8fde-b4f33462d3df)

---


### **Eventos [círculos]**
Os eventos representam algo que acontece ou pode acontecer durante o curso de um processo. Esses eventos afetam o fluxo do processo e geralmente têm uma causa ou um impacto. Existem três tipos de eventos baseados em como o fluxo do processo é afetado:

#### Eventos de Início

Representa o ponto onde o processo começa. Um processo só pode ter um evento de início. 

![image](https://github.com/user-attachments/assets/389b0e6d-7ad9-4e44-9ef2-0c99a45317be)

- Indicam a instância ou iniciação de um processo.
- Não possuem fluxos de sequência de entrada.

#### Eventos Intermediários

Representa uma ação que ocorre entre o início e o término do processo, como uma espera ou uma interrupção temporária.

![image](https://github.com/user-attachments/assets/5c915afa-2144-4677-bceb-16e33cd304f0)

- Indicam algo que ocorre ou pode ocorrer durante o curso do processo, entre o início e o fim.
- Podem ser usados dentro do fluxo de sequência ou anexados à fronteira de uma atividade.
- Os eventos intermediários podem ser usados para capturar ou lançar um gatilho de evento.
- Quando o evento é usado para capturar, o marcador do evento será não preenchido, e quando o evento é usado para lançar, o marcador do evento será preenchido.

#### Eventos de Término

Indica o fim de um processo ou sub-processo. 

![image](https://github.com/user-attachments/assets/ca566617-43d0-4e62-ac5d-898314e5b6b1)

- Indicam onde um processo terminará.
- Um processo pode ter mais de um término.
- Não possuem fluxos de sequência de saída.

---


### **Gateways [diamantes]**

Os gateways representam pontos de decisão ou junções no processo. Eles controlam o fluxo, permitindo bifurcações, junções e combinações de caminhos.

#### Gateway Exclusivo Baseado em Dados(XOR)

Apenas uma rota do processo pode ser seguida.

![image](https://github.com/user-attachments/assets/7b10d42a-3592-439b-853f-b0626320cb88)

- **Representação**: Losango. 
- **Divergência**: A Decisão Exclusiva tem duas ou mais saídas de Fluxo de Sequência, mas apenas uma delas pode ser tomada e a decisão será tomada após avaliar uma condição de negócios.
- **Convergência**: é usado para mesclar caminhos alternativos.

#### Gateway Paralelo(AND)

Todos os caminhos são executados simultaneamente.

![image](https://github.com/user-attachments/assets/104cce2e-9eee-4245-9c9e-9c63e2978598)

- **Representação**: Losango com um "+". 
- **Divergência**: é usado para criar fluxo paralelo.
- **Convergência**: é usado para sincronizar múltiplos caminhos paralelos em um. O fluxo continua quando todos os fluxos de sequência de entrada alcançaram o gateway.

#### Gateway Inclusivo (OR)

Um ou mais caminhos podem ser seguidos dependendo das condições.

![image](https://github.com/user-attachments/assets/248858a7-318e-477e-82c3-49b0bfe623ea)

- **Representação**: Losango com um círculo.
- **Divergência**: indica que uma ou mais rotas podem ser ativadas de várias disponíveis, e a decisão é baseada em dados do processo.
- **Convergência**: indica que muitas rotas de saída de um Gateway Inclusivo, usado como um elemento de divergência, podem ser sincronizadas em apenas uma.

---


### Objetos de Conexão

Os conectores indicam a direção e o fluxo entre as atividades do processo:

#### Fluxo de Sequência

![image](https://github.com/user-attachments/assets/aada9fc5-4249-4a43-9234-752db64cd178)

- É usado para mostrar a ordem em que as atividades serão executadas em um processo.
- É usado para representar a sequência dos objetos de fluxo, onde encontramos atividades, gateways e eventos.

#### Associação

![image](https://github.com/user-attachments/assets/8e7fa98f-ac41-4143-95db-701c6be017dd)

- Uma Associação é usada para associar informações e Artefatos com Objetos de Fluxo.

---

### Swimlanes 

As piscinas e raias ajudam a organizar o processo e a definir as fronteiras entre as diferentes responsabilidades:

#### Piscinas (Pools)

Representam entidades ou participantes no processo. Exemplo: diferentes empresas ou departamentos.

![image](https://github.com/user-attachments/assets/005a2662-493b-449e-b349-7989d78aa2cc)

- Um pool é um recipiente de um único processo.
- O nome do pool pode ser considerado como o nome do processo.
- Sempre existe pelo menos um Pool.

#### Raias (Lanes)

Dividem uma piscina em diferentes papéis ou departamentos dentro da mesma organização, ajudando a visualizar responsabilidades específicas.

![image](https://github.com/user-attachments/assets/e331a406-de8e-4cd1-9a76-a3289c476317)

- Uma lane é uma subdivisão de um pool.
- Representa um papel ou uma área organizacional.

---


### Artefatos
Permitem ou fornecem informações adicionais sobre um processo.

#### Anotação

![image](https://github.com/user-attachments/assets/03647ef3-a13b-41b2-b29f-d60f6552d3c3)

- Fornece informações adicionais sobre o processo para o leitor.

#### Grupo

![image](https://github.com/user-attachments/assets/2f9949a7-0c80-4285-be18-56d578d51e93)

- É um mecanismo visual que permite o agrupamento de atividades para fins de documentação ou análise.

#### Objeto de Dados

![image](https://github.com/user-attachments/assets/f39f1fd7-a6de-4597-96d9-0cfc944a977c)

- Fornece informações sobre a entrada e saída de uma atividade.

---

### Exercício 1: Mapeamento de Processo de Aprovação de Crédito

**Descrição:**  
Crie um diagrama BPMN para um processo de aprovação de crédito em uma instituição financeira. O processo deve começar com o recebimento de uma solicitação de crédito e terminar com a aprovação ou rejeição do pedido. Utilize eventos, tarefas, gateways e fluxos de sequência conforme necessário.

**Passos a serem mapeados:**
1. Recebimento da solicitação de crédito.
2. Análise preliminar da solicitação .
3. Decisão se mais informações são necessárias .
   - Se sim, solicitar mais informações e receber as mesmas .
   - Se não, prosseguir para análise de crédito .
4. Avaliação final.
   - Se aprovado, emitir crédito.
   - Se rejeitado, notificar rejeição.
5. Conclusão do processo.


### Exercício 2: Diagrama de Solicitação de Férias

**Descrição:**  
Desenvolva um diagrama BPMN que modele o processo de solicitação de férias de um funcionário em uma empresa. O processo deve incluir a solicitação das férias, a aprovação pelo supervisor e a notificação ao funcionário.

**Passos a serem mapeados:**
1. Início do pedido de férias pelo funcionário (Evento de Início).
2. Envio do pedido para o supervisor (Tarefa).
3. Avaliação do pedido pelo supervisor (Gateway Exclusivo).
   - Se aprovado, confirmar as férias (Tarefa).
   - Se rejeitado, solicitar alteração da data (Tarefa).
4. Notificação ao funcionário sobre o resultado (Tarefa).
5. Fim do processo (Evento de Término).

### Exercício 3: Diagrama de Reserva de Vaga no Programa de Pós-graduação

O processo de reserva de vaga no programa de pós-graduação da UFN começa quando o candidato recebe instruções detalhadas sobre como preencher sua aplicação. Este procedimento envolve várias fases, iniciando com a inserção de informações pessoais em um formulário específico. Uma vez preenchidas as informações pessoais, o candidato se depara com uma decisão importante: se deve ou não fornecer detalhes sobre sua formação em ensino médio. Dependendo da escolha, o candidato ou adiciona esses dados ou prossegue diretamente para o próximo passo, que é fornecer informações de contato necessárias para futuras comunicações.

Após essas etapas, o candidato deve registrar e anexar todos os documentos que são exigidos para a análise de sua candidatura. O processo avança para a conclusão quando todos os documentos necessários são anexados. O candidato finaliza a submissão da aplicação e, se necessário, anexa arquivos adicionais. O objetivo desse processo é assegurar que todos os dados e documentos requeridos sejam coletados de forma organizada e sistemática para facilitar a avaliação da candidatura pelo programa de pós-graduação.

---

### Referências

1. Bizagi. (n.d.). *Modeler Video List*. Recuperado de [https://www.bizagi.com/pt/home/modeler-video-list.html](https://www.bizagi.com/pt/home/modeler-video-list.html)
2. Bizagi. (n.d.). *My First Model Tutorial*. Recuperado de [https://help.bizagi.com/platform/en/index.html?my_first_model.htm](https://help.bizagi.com/platform/en/index.html?my_first_model.htm)
3. Bizagi. (n.d.). *BPMN Quick Reference Guide*. Recuperado de [https://resources.bizagi.com/docs/BPMN_Quick_Reference_Guide_ENG.pdf](https://resources.bizagi.com/docs/BPMN_Quick_Reference_Guide_ENG.pdf)

