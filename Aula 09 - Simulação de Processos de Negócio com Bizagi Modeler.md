# Aula prática — Simulação de Processos de Negócio com Bizagi Modeler

**Disciplina:** Modelagem de Processos  
**Curso:** Sistemas de Informação  
**Tema:** Simulação de processos BPMN, análise de desempenho e comparação de cenários  
**Duração sugerida:** 120 minutos  
**Ferramenta:** Bizagi Modeler (aplicação desktop)  
**Modalidade:** atividade guiada, com investigação e discussão dos resultados

> **Objetivo da aula:** aprender a transformar um diagrama BPMN em um modelo de simulação, configurar demanda, probabilidades, tempos e recursos, identificar gargalos e avaliar alternativas de melhoria sem alterar o processo real.

**Importante:** todos os valores de chegada, duração e probabilidade deste tutorial são **hipotéticos e exclusivos para fins didáticos**. Eles não foram obtidos de um sistema real. A nomenclatura e a localização de alguns comandos podem variar conforme o idioma e a versão instalada do Bizagi Modeler. O tutorial foi organizado a partir da [documentação oficial de simulação do Bizagi](https://help.bizagi.com/platform/en/simulation_in_bizagi.htm).

---

## 1. Resultados de aprendizagem

Ao final da aula, o estudante deverá ser capaz de:

1. Diferenciar **modelar** um processo de **simular** seu funcionamento.
2. Configurar os dados necessários à simulação de um diagrama BPMN.
3. Executar os níveis de **validação**, **análise de tempos** e **análise de recursos** no Bizagi Modeler.
4. Interpretar indicadores de desempenho, como tempo médio, espera, instâncias concluídas e utilização de recursos.
5. Criar e comparar cenários do tipo *what-if* para apoiar decisões de melhoria.

### 1.1. Pré-requisitos

- Conhecimentos básicos de BPMN: eventos, tarefas, fluxos de sequência, raias e gateway exclusivo (XOR).
- Bizagi Modeler instalado no computador.
- Possibilidade de salvar o modelo localmente.

A versão gratuita do **Bizagi Modeler desktop** oferece modelagem, simulação e análise de cenários *what-if*. Para obtê-la, consulte [Bizagi Modeler — página oficial](https://www.bizagi.com/pt/plataforma/try-modeler). Não confundir o **Bizagi Modeler**, utilizado nesta aula, com o **Bizagi Studio**, voltado a outras atividades de automação de processos.

---

## 2. O que é simulação de processos?

Um modelo BPMN descreve **como** o trabalho deve percorrer o processo. A simulação permite investigar **como o processo pode se comportar** em determinadas condições de operação.

Na simulação, cada solicitação é representada por uma **instância** (ou *token*) que percorre as atividades do processo. O comportamento depende dos dados fornecidos, como:

- **Demanda:** quantas solicitações chegam e com qual frequência.
- **Roteamento:** qual a probabilidade de seguir cada saída de um gateway.
- **Tempo de processamento:** quanto cada atividade demora para ser executada.
- **Recursos:** quantas pessoas ou equipamentos estão disponíveis e quais tarefas exigem esses recursos.
- **Calendários:** em que períodos os recursos estão disponíveis (extensão opcional desta aula).

A simulação **não prova** que o processo real terá aqueles resultados: ela gera estimativas condicionadas ao modelo e às premissas adotadas.

### 2.1. Níveis de simulação no Bizagi

| Nível | Nome na documentação | Pergunta central | Dados adicionados |
|---|---|---|---|
| 1 | **Process Validation** | O fluxo funciona corretamente? | Quantidade de instâncias e probabilidades das saídas |
| 2 | **Time Analysis** | Quanto tempo o processo leva, sem restrição de capacidade? | Intervalo entre chegadas e duração das atividades |
| 3 | **Resource Analysis** | O que acontece quando pessoas/equipamentos são limitados? | Recursos, quantidades, vinculação às tarefas e, opcionalmente, custos |
| 4 | **Calendar Analysis** | O que muda quando há turnos e horários de trabalho? | Calendários e disponibilidade dos recursos por período |

**Nesta aula**, os níveis 1, 2 e 3 são obrigatórios. O nível 4 fica como atividade de aprofundamento.

---

## 3. Estudo de caso: atendimento de chamados de TI

### 3.1. Contexto

O setor de tecnologia de uma universidade atende solicitações de estudantes e professores relacionadas a computadores, laboratórios e sistemas institucionais.

Quando um chamado chega, um atendente o registra e o classifica. Algumas solicitações podem ser resolvidas com uma orientação simples. As demais precisam ser encaminhadas ao suporte técnico para diagnóstico e correção. Em ambos os casos, o chamado deve ser encerrado ao final.

A coordenação percebeu que alguns usuários aguardam muito tempo por atendimento técnico e deseja responder:

> **Contratar ou disponibilizar mais um técnico de suporte reduz o tempo de atendimento dos chamados?**

### 3.2. Regras do processo

1. Todo chamado deve ser **registrado** e **classificado**.
2. Após a classificação, há duas possibilidades:
   - **40%** dos chamados são simples e seguem para **Orientar usuário**.
   - **60%** exigem **Diagnosticar problema** e **Executar correção**.
3. Independentemente do caminho percorrido, todo chamado passa por **Encerrar chamado**.
4. Inicialmente, estão disponíveis **1 atendente** e **1 técnico de suporte**.

### 3.3. Fluxo lógico simplificado

O esquema abaixo serve como guia. **O diagrama oficial da atividade deverá ser construído em BPMN dentro do Bizagi.**

<img width="1920" height="640" alt="image" src="https://github.com/user-attachments/assets/3f160a94-1ab8-4868-a724-efc5d2bb681e" />


### 3.4. Dados para a simulação

**Demanda e roteamento**

| Parâmetro | Valor |
|---|---:|
| Quantidade máxima de chamados gerados (*Max. arrival count*) | 120 |
| Intervalo entre chegadas | 12 minutos (constante) |
| Chamados simples: saída “Sim” | 40% |
| Chamados técnicos: saída “Não” | 60% |
| Duração do cenário | 48 horas |
| Unidade básica de tempo | Minutos |

**Atividades e recursos necessários**

| Atividade | Tempo de processamento | Recurso exigido | Quantidade exigida |
|---|---:|---|---:|
| Registrar chamado | 3 min | Atendente | 1 |
| Classificar chamado | 4 min | Atendente | 1 |
| Orientar usuário | 5 min | Atendente | 1 |
| Diagnosticar problema | 12 min | Técnico de suporte | 1 |
| Executar correção | 15 min | Técnico de suporte | 1 |
| Encerrar chamado | 2 min | Atendente | 1 |

**Disponibilidade inicial dos recursos**

| Recurso | Quantidade disponível no cenário inicial |
|---|---:|
| Atendente | 1 |
| Técnico de suporte | 1 |

> **Atenção:** o tempo de uma tarefa é o seu **tempo de execução**, não um tempo de espera já somado. No nível 3, o Bizagi calculará as esperas causadas pela indisponibilidade dos recursos.

---

## 4. Parte I — Construção do BPMN (20 min)

1. Abra o **Bizagi Modeler** e crie um novo modelo.
2. Crie um processo com o nome **Atendimento de Chamados de TI**.
3. Insira um **pool** com duas **raias (lanes)**:
   - **Central de Atendimento**;
   - **Suporte Técnico**.
4. Na raia **Central de Atendimento**, adicione:
   - Evento de início: `Chamado recebido`;
   - Tarefa: `Registrar chamado`;
   - Tarefa: `Classificar chamado`;
   - Gateway exclusivo (XOR): `Pode ser atendido com orientação?`;
   - Tarefa: `Orientar usuário`;
   - Tarefa: `Encerrar chamado`;
   - Evento de fim: `Chamado encerrado`.
5. Na raia **Suporte Técnico**, adicione:
   - Tarefa: `Diagnosticar problema`;
   - Tarefa: `Executar correção`.
6. Conecte as tarefas com **fluxos de sequência**. Nomeie as saídas do gateway como `Sim` e `Não`.
7. Una os dois caminhos antes de `Encerrar chamado`, utilizando um gateway exclusivo de **convergência**.
8. Salve o arquivo do modelo (por exemplo, `Atendimento_Chamados_TI.bpm`).

**Conferência antes de simular:** há exatamente um início e um fim? Todas as tarefas estão conectadas? Os dois caminhos chegam ao encerramento? O fluxo usa **sequências dentro de um único pool**, e não fluxos de mensagem entre raias?

> **Nota técnica:** para este primeiro exercício, evite tarefas multi-instância, gateways complexos e outros elementos avançados. Nem todos os elementos BPMN são aceitos pelo mecanismo de simulação do Bizagi.

---

## 5. Parte II — Nível 1: validação do processo (15 min)

### Objetivo

Verificar se os chamados percorrem os caminhos previstos e conseguem chegar ao evento de fim.

### Passo a passo

1. Com o diagrama aberto, selecione **Simulation View** (ou a opção equivalente de visualização de simulação) na faixa de opções do Bizagi.
2. Certifique-se de estar no nível **1 — Process Validation**. Elementos que precisam de parâmetros deverão ficar disponíveis para configuração.
3. Clique no **evento de início** e abra a configuração pelo ícone de **engrenagem** que aparece no menu contextual do elemento.
4. Em **Max. arrival count**, digite **120**.
5. Selecione o gateway de decisão `Pode ser atendido com orientação?` e configure as probabilidades dos fluxos de saída:
   - `Sim` = **40%**;
   - `Não` = **60%**.
6. Na faixa de opções da simulação, abra **Properties** (propriedades do cenário) e configure:
   - **Name:** `Cenário A — Situação atual`;
   - **Description:** `Um atendente e um técnico de suporte`;
   - **Base Time unit:** `Minutes`;
   - **Duration:** `48 hours` (ou duração equivalente, conforme a interface).
7. Clique em **Run** e, na janela de execução, clique em **Start**.
8. Observe os tokens percorrendo os dois caminhos. Ao finalizar, selecione **Results**.

### O que observar?

- Quantas instâncias foram iniciadas e concluídas?
- Quantos chamados percorreram o caminho simples?
- Quantos chamados passaram pelo suporte técnico?
- Algum token ficou sem atingir o evento de fim?

**Resultado esperado conceitualmente:** aproximadamente **48 chamados simples** e **72 chamados técnicos**, pois as proporções são 40% e 60% de 120. A contagem exata pode variar conforme o sorteio das rotas realizado pelo simulador. Se o tempo de simulação for suficiente, espera-se que os chamados cheguem ao fim.

**Registro do estudante:** anote as contagens efetivamente obtidas. Não substitua os resultados do Bizagi pelos valores esperados.

---

## 6. Parte III — Nível 2: análise de tempos (20 min)

### Objetivo

Estimar o tempo necessário para processar os chamados, **sem impor limite de recursos**.

### Passo a passo

1. Na visualização de simulação, altere o nível para **2 — Time Analysis**.
2. Selecione o **evento de início** e, na configuração de tempo, informe **12 minutos** como intervalo **constante** entre chegadas (*Arrival interval time*).
3. Para cada tarefa, clique no elemento e utilize o ícone de **relógio** no menu contextual.
4. Preencha o tempo **constante** de processamento, conforme a tabela da seção **3.4**:
   - Registrar chamado: **3 min**;
   - Classificar chamado: **4 min**;
   - Orientar usuário: **5 min**;
   - Diagnosticar problema: **12 min**;
   - Executar correção: **15 min**;
   - Encerrar chamado: **2 min**.
5. Confirme que a unidade de tempo do cenário é **minutos**.
6. Execute novamente com **Run → Start** e abra **Results**.
7. Registre o tempo médio do processo e, quando disponível, os tempos por atividade.


### Exercício de interpretação

Um chamado simples percorre `Registrar → Classificar → Resolver → Encerrar`:

```math
T_{\text{simples}} = 3 + 4 + 5 + 2 = 14\ \text{minutos}
```

Um chamado que precisa de suporte percorre `Registrar → Classificar → Diagnosticar → Executar correção → Encerrar`:

```math
T_{\text{técnico}} = 3 + 4 + 12 + 15 + 2 = 36\ \text{minutos}
```

O tempo médio teórico **de processamento, sem espera**, é:

```math
E[T] = 0{,}40(14) + 0{,}60(36) = \boxed{27{,}2\ \text{minutos}}
```


**Pergunta:** o tempo médio apresentado pelo Bizagi ficou próximo de **27,2 minutos**? Explique eventuais diferenças considerando que a quantidade de chamados em cada caminho não precisa ser exatamente 40% ou 60%.

> **Conceito-chave:** neste nível, o Bizagi assume capacidade de recursos ilimitada. Por isso, os tempos obtidos **não refletem as filas** que surgem quando uma pessoa precisa atender a vários chamados.

---

## 7. Parte IV — Nível 3: análise de recursos (25 min)

### Objetivo

Analisar como a disponibilidade de atendentes e técnicos modifica o desempenho do processo.

### Passo a passo

1. Altere o nível para **3 — Resource Analysis**.
2. Na faixa de opções, clique em **Resources**.
3. Cadastre os recursos **Atendente** e **Técnico de suporte**, caso ainda não existam. Dependendo da versão, o cadastro poderá aparecer em **Resources → Add performer**.
4. Na opção de **Availability** (disponibilidade), configure:
   - Atendente: **1**;
   - Técnico de suporte: **1**.
5. Para cada atividade, clique no respectivo elemento e abra a opção **Resources** no menu contextual (ícone associado à atribuição de recursos).
6. Associe **1 Atendente** às tarefas `Registrar chamado`, `Classificar chamado`, `Orientar usuário` e `Encerrar chamado`.
7. Associe **1 Técnico de suporte** às tarefas `Diagnosticar problema` e `Executar correção`.
8. Mantenha os tempos, probabilidades, intervalos de chegada e quantidade máxima de chamados previamente informados.
9. Execute a simulação e abra **Results**.
10. Consulte as informações de **tempo médio**, **espera por recurso**, **instâncias concluídas** e **utilização dos recursos**, quando disponibilizadas pelo relatório.

**Importante:** o fato de uma tarefa estar desenhada em determinada raia **não substitui** a atribuição dos recursos exigidos pela tarefa na simulação.


### Antes de olhar os resultados: existe capacidade suficiente?

A taxa média de chegada configurada é:

```math
\lambda = \frac{60}{12} = 5\ \text{chamados por hora}
```

O atendente trabalha, em média, por chamado:

```math
3 + 4 + 0{,}40(5) + 2 = 11\ \text{minutos}
```

Assim, a demanda estimada de trabalho do atendente é:

```math
5(11) = 55\ \text{minutos de trabalho por hora}
```

O técnico só participa de 60% dos chamados, com 27 minutos de serviço em cada um:

```math
5(0{,}60)(12+15) = 81\ \text{minutos de trabalho técnico por hora}
```


**Interpretação:** durante o período de chegadas, a demanda média de **81 minutos de trabalho técnico por hora** excede os **60 minutos de capacidade por hora** de um único técnico. Isso sugere formação de fila no suporte. O atendente também tem carga elevada (55 minutos por hora), mas inferior à sua capacidade teórica.

Esses cálculos são uma **verificação analítica das premissas**, não uma antecipação dos resultados exatos que o Bizagi deve apresentar.

### Questões para registrar

1. Em quais tarefas apareceram as maiores esperas por recurso?
2. O tempo médio total ficou maior que no nível 2? Por quê?
3. A disponibilidade de um técnico parece suficiente para absorver a demanda configurada?
4. Qual recurso tende a se tornar o gargalo quando a quantidade de técnicos aumenta?

---

## 8. Parte V — Comparação de cenários *what-if* (20 min)

### Objetivo

Avaliar a consequência de uma alteração na capacidade do suporte **sem modificar a estrutura do BPMN**.

### 8.1. Criar o cenário alternativo

1. Ainda na **Simulation View**, acesse **What if → Manage scenarios**.
2. Clique em **New**.
3. Escolha **Duplicate selected scenario** para copiar todas as configurações do cenário atual.
4. Renomeie a cópia para **Cenário B — Dois técnicos**.
5. Na descrição, informe: `Mesmo processo, mesma demanda e mesmos tempos; dois técnicos de suporte disponíveis`.
6. Mantenha todos os valores anteriores e altere **apenas** a disponibilidade de **Técnico de suporte** de **1 para 2**, em **Resources → Availability**.
7. Confira que cada tarefa técnica continua exigindo **1 técnico por execução**; a mudança é na **quantidade total de profissionais disponíveis**, não na quantidade necessária para fazer uma mesma tarefa.
8. Execute o cenário B e registre os resultados.

### 8.2. Comparar os cenários

Selecione **What if**, marque os cenários **A** e **B** e execute a comparação. O Bizagi apresenta um relatório comparativo. Caso a sua instalação apresente uma interface diferente, consulte a opção correspondente na documentação de [What-if analysis](https://help.bizagi.com/platform/en/what_if_analysis.htm).

Preencha a tabela **com os valores observados no Bizagi**:

| Indicador | Cenário A: 1 técnico | Cenário B: 2 técnicos | Diferença / comentário |
|---|---|---|---|
| Chamados concluídos | | | |
| Tempo médio do processo | | | |
| Tempo médio de espera por técnico | | | |
| Tempo médio de espera por atendente | | | |
| Utilização dos técnicos | | | |
| Utilização do atendente | | | |

### 8.3. Discussão em grupo

- Adicionar o segundo técnico reduziu o **tempo de espera**?
- A redução no tempo total do processo foi proporcional ao aumento de técnicos?
- O **atendente** passou a ter maior relevância como gargalo?
- A contratação seria necessariamente a melhor decisão, ou seria interessante testar mudanças nas atividades e na taxa de chegada?
- Quais dados reais seriam necessários para tornar essa análise mais confiável?

> **Cuidados na comparação:** preserve a demanda, as probabilidades, os tempos e a duração entre os cenários. Como o roteamento envolve aleatoriedade, resultados de uma única execução podem apresentar oscilações. Para análises mais robustas, repita as simulações e avalie a variabilidade. A documentação do Bizagi recomenda **30 replicações** em análises estatísticas; para executá-las, utilize *What-if* com **um cenário selecionado de cada vez**, configurando a opção de replicações nas propriedades do cenário.

> **Atenção à utilização:** como as 120 chegadas ocorrem aproximadamente nas primeiras 24 horas de um cenário de 48 horas, poderá haver um período final sem novas solicitações. Esse período ocioso afeta indicadores agregados de utilização. Interprete-os em conjunto com os tempos de espera e com a carga de trabalho calculada durante o período de chegadas; **não use apenas o percentual de utilização para concluir que não existe gargalo**.

---

## 9. Desafio complementar — Cenário C: automatizar uma atividade

A coordenação está avaliando automatizar parte da classificação inicial dos chamados.

**Tarefa:** crie um terceiro cenário, duplicando o cenário A e modificando **somente** o tempo da tarefa `Classificar chamado`, de **4 minutos para 1 minuto**. Mantenha **1 atendente** e **1 técnico**.

Investigue:

1. O tempo médio total do processo diminuiu?
2. A espera pelo atendente diminuiu?
3. A automação da classificação resolve o problema da fila de suporte técnico?
4. Comparando A, B e C, qual intervenção ataca diretamente o gargalo identificado?

**Não há um único número obrigatório para a resposta:** a conclusão deve ser baseada nas configurações e nos resultados efetivamente registrados.

---

## 10. Aprofundamento opcional — Nível 4: calendários

Na análise de recursos, a disponibilidade padrão considera recursos acessíveis continuamente. Para aproximar a simulação da rotina institucional, é possível utilizar o nível **4 — Calendar Analysis**.

**Exemplo de extensão:** configurar atendimento de segunda a sexta-feira, das **8h às 12h e das 13h às 17h**, associando a disponibilidade de atendentes e técnicos aos períodos de trabalho.

Procedimento geral:

1. Alterar para **Level 4 — Calendar Analysis**.
2. Abrir a opção **Calendars** e criar os períodos de disponibilidade, com horários e recorrência apropriados.
3. Acessar **Resources** e informar a disponibilidade de cada tipo de recurso nos calendários criados.
4. Executar novamente a simulação e comparar tempos de espera, conclusão e utilização.

**Limitação importante do simulador:** de acordo com a documentação oficial, no nível de calendários, a geração de chegadas é considerada ao longo de **24 horas por dia, sete dias por semana**; os calendários restringem a disponibilidade dos **recursos**, não a janela de chegada de novas instâncias. Portanto, explique essa premissa aos estudantes ao interpretar filas fora do expediente.

Guia oficial: [Level 4 — Calendar Analysis](https://help.bizagi.com/platform/en/level_4_example.htm).

---

## 11. Entrega da atividade

Cada dupla deverá entregar:

1. **Modelo BPMN** criado no Bizagi (`.bpm`, ou formato equivalente disponível na instalação).
2. **Evidências da simulação:** capturas de tela ou relatórios exportados dos níveis 1, 2 e 3.
3. **Tabela preenchida** de comparação dos cenários A e B.
4. **Análise breve** (aproximadamente 10 a 15 linhas) respondendo:
   - Onde estava o principal gargalo do processo?
   - Qual foi o impacto do segundo técnico?
   - Qual melhoria recomendam e com base em quais indicadores?
   - Quais limitações existem por se tratar de dados hipotéticos?

**Critérios de avaliação sugeridos (10 pontos):** correção do BPMN (2), configuração dos três níveis (3), construção dos dois cenários (2), qualidade da comparação e justificativa da recomendação (3).

### Checklist antes de entregar

- [ ] Diagrama com início, atividades, gateway XOR e fim corretamente conectados.
- [ ] Probabilidades das saídas totalizando 100%.
- [ ] Evento inicial configurado com 120 chegadas máximas.
- [ ] Intervalo entre chegadas de 12 minutos.
- [ ] Tempos configurados em todas as tarefas.
- [ ] Recursos criados e atribuídos corretamente às atividades.
- [ ] Cenário A com 1 atendente e 1 técnico.
- [ ] Cenário B com 1 atendente e 2 técnicos.
- [ ] Resultados registrados, sem substituir valores observados por números teóricos.
- [ ] Conclusão fundamentada nos indicadores da simulação.

---

## 12. Orientações ao professor — roteiro de condução

| Tempo | Atividade | Estratégia |
|---|---|---|
| 0–10 min | Conceitos básicos de simulação | Perguntar por que um BPMN correto pode apresentar filas |
| 10–30 min | Construção do BPMN | Modelagem guiada em duplas |
| 30–45 min | Nível 1 | Validar caminhos e discutir probabilidades |
| 45–65 min | Nível 2 | Configurar tempos e calcular média teórica de 27,2 min |
| 65–90 min | Nível 3 | Adicionar recursos, identificar espera e estimar carga |
| 90–110 min | Cenários *what-if* | Comparar um versus dois técnicos |
| 110–120 min | Discussão e fechamento | Solicitar recomendação justificada com indicadores |

**Pontos a reforçar durante a aula:**

- **Tempo de execução não é tempo de espera.** No nível 2, a capacidade é ilimitada; no nível 3, podem surgir filas.
- **Um gateway com probabilidade 40%/60% não garante exatamente essa divisão** em uma amostra de 120 instâncias.
- **Aumentar os recursos não reduz automaticamente a duração intrínseca da tarefa.** A melhoria pode vir da diminuição da espera.
- **Gargalos podem mudar de lugar.** Ao aliviar o suporte técnico, a Central de Atendimento pode passar a limitar o desempenho.
- **Simular não é automatizar um processo.** O Bizagi Modeler avalia o comportamento do modelo; não executa as atividades de negócio reais.

### Solução conceitual de referência

- **Nível 1:** os dois caminhos devem ser percorridos, aproximadamente na proporção informada.
- **Nível 2:** com tempos constantes e sem esperas, a média teórica de processamento é **27,2 minutos por chamado**.
- **Nível 3, cenário A:** a carga média de trabalho técnico (81 min/h) ultrapassa a capacidade de um técnico (60 min/h) durante a geração de chamados. Espera-se formação de fila, dependendo da dinâmica da execução.
- **Nível 3, cenário B:** a capacidade de dois técnicos passa a ser de **120 min/h**, superior à demanda técnica média de 81 min/h. A espera no suporte tende a diminuir; o atendente permanece com demanda média de **55 min/h**, próxima da capacidade de uma pessoa.
- **A conclusão deve se apoiar nos relatórios:** não há valores exatos pré-definidos para tempos de espera, utilização ou instâncias concluídas em cada cenário.

---

## 13. Documentação oficial e referências de apoio

Materiais da **Bizagi** utilizados como base para os procedimentos e as limitações descritas:

- [Bizagi Modeler — versão gratuita e funcionalidades](https://help.bizagi.com/platform/en/free_getting_started_with.htm)
- [Simulation in Bizagi — visão geral e procedimento de execução](https://help.bizagi.com/platform/en/simulation_in_bizagi.htm)
- [Simulation levels — os quatro níveis](https://help.bizagi.com/platform/en/simulation_levels.htm)
- [Level 1 — Process Validation](https://help.bizagi.com/platform/en/level_1_example.htm)
- [Level 2 — Throughput Time Analysis](https://help.bizagi.com/platform/en/level_2_example.htm)
- [Level 3 — Resource Analysis](https://help.bizagi.com/platform/en/level_3_example.htm)
- [Level 4 — Calendar Analysis](https://help.bizagi.com/platform/en/level_4_example.htm)
- [Scenarios — criação e duplicação de cenários](https://help.bizagi.com/platform/en/scenarios.htm)
- [What-if Analysis — comparação de cenários](https://help.bizagi.com/platform/en/what_if_analysis.htm)
- [Configure Simulation — propriedades, duração e replicações](https://help.bizagi.com/platform/en/configure_simulation.htm)

**Observação:** este material é um roteiro didático autoral baseado nas funcionalidades documentadas pelo fabricante. Telas e rótulos podem variar entre versões do Bizagi Modeler.
