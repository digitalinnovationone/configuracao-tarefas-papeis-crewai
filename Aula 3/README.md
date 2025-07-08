# Aula 3: Configuração de Tarefas com Parâmetros e Objetivos

## Conteúdo Teórico (Configurando Tarefas: Parâmetros, Condições e Objetivos no CrewAI)

**Objetivo:** Ensinar como configurar tarefas no CrewAI, detalhando a definição de parâmetros, condições e objetivos claros.

Bem-vindos de volta! Na Aula 2, definimos nosso Agente ("Pesquisador de Mercado") e uma Tarefa inicial ("Pesquisa de Mercado"). Agora que sabemos o "quem" e o "o quê", é hora de refinar o "como" e o "porquê". Nesta aula, vamos nos aprofundar na **configuração das Tarefas**, explorando como adicionar **parâmetros, condições e objetivos claros**.

**Por que Configurar Tarefas com Detalhes?**

Definir tarefas de forma precisa é vital para o sucesso dos seus agentes. Pense nisso: um humano só consegue fazer um bom trabalho se entender bem o que é esperado dele. Com agentes de IA, é a mesma coisa! Uma configuração detalhada garante que o agente:

*   **Entenda o Contexto:** Parâmetros tornam a tarefa flexível e adaptável a diferentes cenários.
*   **Saiba o que Entregar:** Objetivos claros e um "expected output" guiam o agente para o resultado desejado.
*   **Atue de Forma Eficiente:** Condições (se aplicáveis) ajudam a otimizar quando uma tarefa deve ou não ser executada.

Isso tudo contribui para a **automação inteligente** e para um **monitoramento** mais eficaz do desempenho dos agentes.

**Parâmetros em Tarefas: Tornando-as Dinâmicas**

Na tarefa "Pesquisa de Mercado" que criamos, já inserimos um `{product_topic}`. Isso é um **parâmetro**.

*   **O que são:** São variáveis que você passa para a tarefa no momento da execução.
*   **Para que servem:** Permitem que a mesma tarefa seja reutilizada para diferentes entradas, sem precisar reescrever o código. Por exemplo, a mesma tarefa de pesquisa pode ser usada para "celulares", "automóveis" ou "software".
*   **Como usar:** Você os define na `description` da tarefa (usando chaves `{}`), e os passa para o método `kickoff()` da Crew no `main.py`.

**Objetivos Claros e `expected_output`:**

O `expected_output` (resultado esperado) é uma das propriedades **mais importantes** de uma tarefa.

*   **Para que serve:** Ele diz ao agente **exatamente o formato e o conteúdo** que se espera como resultado da tarefa. É como uma lista de verificação para o agente.
*   **Benefício:** Ajuda o LLM (o "cérebro" do agente) a focar na entrega correta e padronizada. Também é crucial para que a saída de uma tarefa sirva como **entrada (contexto)** para a próxima tarefa em um fluxo de trabalho (como veremos na Aula 4).
*   **Exemplos:** Em vez de "Fazer uma pesquisa", um bom `expected_output` seria "Um resumo em tópicos dos 5 principais concorrentes, incluindo seus pontos fortes e fracos".

**Condições de Execução (um breve toque para iniciantes):**

Embora o CrewAI permita definir **condições** para a execução de tarefas (por exemplo, "executar esta tarefa APENAS SE a tarefa anterior for concluída com sucesso" ou "se o sentimento for positivo"), para este curso de iniciantes, vamos focar mais nos parâmetros e objetivos. Saber que elas existem e tornam os fluxos mais robustos já é um bom começo. Em cenários mais avançados, elas são usadas para criar fluxos de trabalho complexos e ramificados.

**Monitoramento de Desempenho (Preliminar):**

Ter tarefas bem definidas, com parâmetros e objetivos claros, é o primeiro passo para poder monitorar o desempenho dos seus agentes. Se você sabe o que espera, pode facilmente verificar se o agente entregou o que foi pedido. Na Aula 5, vamos nos aprofundar nesse monitoramento.

**Recapitulando a Importância:**

Definir bem cada propriedade de uma tarefa é como dar instruções precisas a um time. Quanto mais claras as instruções, melhor o resultado. Isso otimiza o uso do LLM, aumenta a eficiência e permite que seus agentes trabalhem de forma mais autônoma e eficaz.

Na aula prática, vamos **refinar a tarefa de "Pesquisa de Mercado"** que criamos, adicionando parâmetros e ajustando o `expected_output`. E o mais empolgante: vamos **executar nosso primeiro agente** para ver a mágica acontecer!

## Conteúdo Prático (Projeto Hands-On: Configurando Tarefas no Setor de Saúde)

> TODO

**Recapitulando:** Nesta aula, você não só **aprofundou na configuração de tarefas** com parâmetros e objetivos claros, como também **executou seu primeiro agente CrewAI**!. Você viu como a definição precisa das tarefas, combinada com a configuração do LLM e ferramentas, permite que o agente realize ações inteligentes e gere resultados úteis. Essa é a base da automação com CrewAI.

Na próxima aula, vamos dar um passo adiante e introduzir um **segundo agente**. Veremos como eles podem **colaborar**, com cada um assumindo seu papel e contribuindo para um objetivo maior: a criação de um plano de campanha completo.
