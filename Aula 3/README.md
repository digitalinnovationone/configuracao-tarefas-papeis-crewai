# Aula 3: Configuração de Tarefas com Parâmetros e Objetivos

## Conteúdo Teórico (Configurando Tarefas: Parâmetros, Condições e Objetivos no CrewAI)

**Objetivo:** Ensinar como configurar tarefas no CrewAI, detalhando a definição de parâmetros, condições e objetivos claros, além de conectar um LLM para dar "inteligência" aos agentes.

Bem-vindos de volta! Na Aula 2, definimos nosso primeiro agente ("Especialista em Didática para TI") e criamos a estrutura básica do projeto. Agora que sabemos o "quem" e o "o quê", é hora de refinar o "como" e o "porquê". Nesta aula, vamos nos aprofundar na **configuração das Tarefas**, explorando como adicionar **parâmetros, condições e objetivos claros**. Mais importante ainda: vamos **conectar um LLM** para dar vida ao nosso agente!

**Por que Configurar Tarefas com Detalhes?**

Definir tarefas de forma precisa é vital para o sucesso dos seus agentes. Pense nisso: um professor só consegue dar uma boa aula se entender bem o que é esperado dele e para quem está ensinando. Com agentes de IA, é a mesma coisa! Uma configuração detalhada garante que o agente:

*   **Entenda o Contexto:** Parâmetros tornam a tarefa flexível e adaptável a diferentes tópicos.
*   **Saiba o que Entregar:** Objetivos claros e um "expected output" guiam o agente para o resultado desejado.
*   **Atue de Forma Eficiente:** Condições (se aplicáveis) ajudam a otimizar quando uma tarefa deve ou não ser executada.

Isso tudo contribui para a **automação inteligente** e para um **monitoramento** mais eficaz do desempenho dos agentes.

**Parâmetros em Tarefas: Tornando-as Dinâmicas**

Na tarefa "Criar Resumo Didático" que criamos, já inserimos um `{topic}`. Isso é um **parâmetro**.

*   **O que são:** São variáveis que você passa para a tarefa no momento da execução.
*   **Para que servem:** Permitem que a mesma tarefa seja reutilizada para diferentes entradas, sem precisar reescrever o código. Por exemplo, a mesma tarefa pode explicar "Python", "Banco de Dados" ou "Redes de Computadores".
*   **Como usar:** Você os define na `description` da tarefa (usando chaves `{}`), e os passa para o método `kickoff()` da Crew no `main.py`.

**Objetivos Claros e `expected_output`:**

O `expected_output` (resultado esperado) é uma das propriedades **mais importantes** de uma tarefa.

*   **Para que serve:** Ele diz ao agente **exatamente o formato e o conteúdo** que se espera como resultado da tarefa. É como uma lista de verificação para o agente.
*   **Benefício:** Ajuda o LLM (o "cérebro" do agente) a focar na entrega correta e padronizada. Também é crucial para que a saída de uma tarefa sirva como **entrada (contexto)** para a próxima tarefa em um fluxo de trabalho.
*   **Exemplo:** Em vez de "Explicar um tópico", um bom `expected_output` seria "Um texto em markdown com: título, introdução simples, 3 conceitos principais com exemplos, e conclusão prática. Máximo 500 palavras, linguagem acessível para iniciantes."

**Markdown: A Linguagem dos Nossos Arquivos**

Como nossos agentes vão gerar conteúdo educacional, é importante entender o **Markdown**:

*   **O que é:** Uma linguagem de marcação simples para formatar texto (títulos, listas, negrito, etc.)
*   **Por que usar:** É padrão em documentação, fácil de ler e converter para outros formatos
*   **Exemplos básicos:** `# Título`, `**negrito**`, `- item de lista`, `` `código` ``

**Conectando um LLM: Dando Inteligência ao Agente**

Até agora, criamos a "estrutura" do agente, mas ele ainda não tem "inteligência". Para isso, precisamos conectar um **Large Language Model (LLM)**:

*   **Opções:** OpenAI GPT, Google Gemini, modelos locais via Ollama, entre outros
*   **Configuração:** Definir API keys e configurar o LLM no agente
*   **Resultado:** O agente passa a "pensar" e gerar respostas inteligentes baseadas no seu papel e tarefas

**Recapitulando a Importância:**

Definir bem cada propriedade de uma tarefa e conectar um LLM é como dar instruções precisas e inteligência a um especialista. Quanto mais claras as instruções e mais "inteligente" o especialista, melhor o resultado. Isso otimiza o uso do LLM, aumenta a eficiência e permite que seus agentes trabalhem de forma mais autônoma e eficaz.

## Conteúdo Prático (Projeto Hands-On: Refinando e Executando Nosso Agente Didático)

**Objetivo da Prática:** Refinar o agente criado na aula anterior, melhorar os prompts, configurar um LLM e executar nosso primeiro teste prático.

**Duração Estimada:** 15 minutos

### O Que Vamos Fazer

Nesta aula prática, vamos:
- Refinar o prompt do nosso agente didático
- Melhorar o `expected_output` da tarefa
- Conectar um LLM (OpenAI ou Google Gemini)
- Executar nosso primeiro teste
- Analisar o resultado gerado

### Refinamentos no Projeto

**1. Melhorando o Agente**
- Ajustar a descrição do papel para ser mais específica
- Adicionar backstory mais detalhada sobre didática
- Configurar o LLM no agente

**2. Refinando a Tarefa**
- Melhorar a descrição para ser mais clara sobre o formato desejado
- Criar um `expected_output` detalhado mencionando markdown
- Especificar o tom didático e público-alvo (iniciantes)

**3. Configuração do LLM**
- Configurar variáveis de ambiente (API keys)
- Testar conectividade com o modelo escolhido
- Ajustar parâmetros básicos (temperatura, etc.)

**4. Primeira Execução**
- Executar com um tópico simples (ex: "O que é Python")
- Analisar o arquivo markdown gerado
- Verificar se o formato está conforme esperado

### Pontos de Aprendizado

Durante a prática, vamos observar:
- Como prompts bem estruturados influenciam a qualidade da resposta
- A importância do `expected_output` para padronizar resultados
- Como diferentes LLMs podem gerar estilos diferentes
- A diferença entre um agente "configurado" vs "executando"

### Desmistificando o Markdown

Vamos mostrar na prática:
- Como o agente estrutura o conteúdo com títulos (`#`, `##`)
- Uso de formatação (`**negrito**`, `*itálico*`)
- Criação de listas e exemplos de código
- Como o resultado fica visualmente organizado

**Recapitulando:** Nesta aula, você **refinou seu agente didático** com prompts mais precisos, **conectou um LLM** para dar inteligência ao projeto e **executou seu primeiro teste**! Você viu como a configuração detalhada das tarefas, combinada com um LLM bem configurado, permite que o agente gere conteúdo educacional de qualidade.

Na próxima aula, vamos **adicionar o segundo agente** - nosso "Criador de Exercícios Práticos" - e fazer com que ele trabalhe em conjunto com o primeiro agente, criando um fluxo colaborativo completo!