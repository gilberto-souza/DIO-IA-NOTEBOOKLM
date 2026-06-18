# DIO-IA-NOTEBOOKLM
Treinando uma IA de Aprendizagem: Explore o Poder do NotebookLM


## 📖 Contexto e Objetivos

### 🔍 Assunto de Interesse: T-SQL (Transact-SQL)
Este caderno temático foi desenvolvido com o propósito de centralizar estudos, anotações e práticas sobre o **T-SQL (Transact-SQL)**, a extensão proprietária da linguagem SQL utilizada no ecossistema do Microsoft SQL Server. 

O foco deste material vai além das consultas básicas (DML/DDL), explorando os recursos programáticos da linguagem, como o desenvolvimento de rotinas automatizadas, controle de fluxo, manipulação de variáveis e otimização de performance em bancos de dados relacionais.

---

### 🎯 Objetivos de Estudo
Os principais objetivos definidos para o aprendizado e consolidação de conhecimento através deste material são:

* **Dominar a Lógica Programática no Banco de Dados:** Compreender e aplicar estruturas de repetição (`WHILE`), blocos condicionais (`IF...ELSE`) e o tratamento de exceções/erros (`TRY...CATCH`).
* **Construção de Objetos Programáveis:** Desenvolver e gerenciar estruturas robustas como *Stored Procedures* (Procedimentos Armazenados), *User-Defined Functions* (UDFs) e *Triggers* (Gatilhos).
* **Manipulação Avançada de Dados:** Praticar o uso de tabelas temporárias (`#Tabelas`), variáveis de tabela, CTEs (*Common Table Expressions*) e funções de janela (*Window Functions*).
* **Performance e Otimização:** Entender o comportamento de cursores versus operações baseadas em conjuntos (set-based), visando a escrita de scripts mais rápidos e eficientes.
* **Criação de um Portfólio Prático:** Guardar scripts reutilizáveis, desafios resolvidos e soluções para problemas comuns do dia a dia de um desenvolvedor ou analista de dados.

## 🛠️ Engenharia de Prompts e "Cicatrizes" (Troubleshooting)

O desenvolvimento deste caderno contou com o apoio de Inteligência Artificial Estruturada. Abaixo está o registro de como os prompts foram refinados para extrair o melhor conhecimento técnico sobre T-SQL, demonstrando o raciocínio e os bastidores do aprendizado.

### 🧠 Perguntas Estratégicas e Variações de Prompts

#### Iteração 1: O Prompt Inadequado (Genérico)
* **Prompt:** *"Me explica o que é T-SQL e me dá exemplos."*
* **Resultado:** A IA retornou uma resposta muito superficial, confundindo comandos SQL padrão (ANSI) com recursos específicos do SQL Server. Os exemplos continham apenas `SELECT` e `WHERE` básicos.
* **Problema Encontrado:** Falta de especificidade. Não forçou a IA a focar no lado programático e de engenharia de dados do T-SQL.

#### Iteração 2: O Prompt Refinado (Direcionado com Fontes de Referência)
* **Prompt:** *"Atue como um Especialista em Banco de Dados SQL Server. Com base na documentação oficial da Microsoft e nos fundamentos do livro 'SQL Server T-SQL Fundamentals', explique a diferença prática entre uma operação baseada em conjuntos (Set-Based) e uma operação iterativa (Cursores) no T-SQL. Forneça exemplos de código limpo para ambos."*
* **Resultado:** A resposta foi altamente técnica. Separou perfeitamente o comportamento físico do processamento de queries e estruturou os scripts respeitando as boas práticas.

---

### 🩹 Cicatrizes e Desafios de Aprendizado (Troubleshooting da IA)
1. **Alucinação de Sintaxe:** Durante a requisição de exemplos de tratamento de erros, a IA inicialmente misturou a sintaxe do Oracle (`EXCEPTION WHEN OTHERS`) com o T-SQL. 
   * **Como foi resolvido:** Foi necessário aplicar um prompt de correção: *"Corrija o código anterior. No SQL Server/T-SQL, o tratamento de erros utiliza obrigatoriamente os blocos `BEGIN TRY ... END TRY` e `BEGIN CATCH ... END CATCH`."*
2. **Falta de Profundidade em Performance:** A IA tendia a recomendar o uso de funções definidas pelo usuário (UDFs) sem avisar sobre o impacto de performance que as *Scalar Functions* causam (execução linha por linha).
   * **Como foi resolvido:** Inclusão de restrições explícitas no prompt, como: *"Explique os prós e contras de cada abordagem, com foco em consumo de CPU e planos de execução."*

---

## 📚 Miniguia de Estudo (Entrega Final)

### 📋 Resumos Estruturados do Assunto
O **T-SQL (Transact-SQL)** estende o padrão ANSI SQL inserindo características de linguagens de programação procedurais. O fluxo de processamento do Microsoft SQL Server é otimizado para operações **Set-Based** (Baseadas em Conjuntos), onde o motor do banco decide a melhor forma de extrair os dados através do Query Optimizer. No entanto, o T-SQL permite programação procedural explícita (como blocos condicionais e loops) para manipulações complexas de dados e automação de rotinas diretamente no servidor.

#### Estruturas Elementares do T-SQL:
* **Elementos Programáticos:** Variáveis (`DECLARE @Var`), Controle de Fluxo (`IF...ELSE`, `WHILE`), e blocos de execução (`BEGIN...END`).
* **Objetos do Sistema:** Procedimentos Armazenados (*Stored Procedures*), Gatilhos (*Triggers*), e Funções (*UDFs*).

---

### 📖 Glossário de Conceitos Aprendidos

* **Set-Based Operation:** Abordagem padrão do SQL onde as operações são aplicadas a um conjunto inteiro de linhas de uma só vez (ex: `UPDATE` filtrado). É muito mais rápida devido à otimização de índices.
* **Cursor (Operação Iterativa):** Mecanismo que processa os dados linha por linha (RBAR - *Row By Agonizing Row*). Deve ser evitado para grandes volumes de dados devido ao alto consumo de memória e processamento.
* **Stored Procedure (Procedimento Armazenado):** Um conjunto pré-compilado de instruções T-SQL armazenado no banco de dados. Melhora a performance porque o plano de execução é reaproveitado e reduz o tráfego de rede.
* **Trigger (Gatilho):** Um tipo especial de procedimento armazenado que é executado automaticamente em resposta a um evento de DML (`INSERT`, `UPDATE` ou `DELETE`). Utiliza as tabelas virtuais `inserted` e `deleted` para validar os dados afetados.
* **CTE (Common Table Expression):** Um conjunto de resultados nomeado e temporário que pode ser referenciado dentro de uma instrução `SELECT`, `INSERT`, `UPDATE` ou `DELETE`. Excelente para melhorar a legibilidade de queries complexas ou realizar consultas recursivas.
* **TRY...CATCH:** Estrutura de tratamento de erros introduzida para capturar falhas de execução no banco de dados, permitindo realizar o `ROLLBACK` de transações e registrar logs de erros com funções como `ERROR_MESSAGE()`.

---

### 🔄 Prompts Reutilizáveis para Revisões Futuras

Guarde estes prompts para utilizar no seu chat de IA sempre que precisar revisar ou expandir seus conhecimentos neste repositório:

#### 📂 Prompt 1: Gerador de Desafios Práticos
Atue como um Tech Lead em Engenharia de Dados. Com base nos conceitos de T-SQL, crie um desafio prático de nível [Intermediário/Avançado] envolvendo [Escolha: Stored Procedures / Triggers / Janelas de Função]. O desafio deve conter um cenário de negócio fictício, a estrutura das tabelas necessárias e os critérios de aceitação da solução. Não dê a resposta imediatamente.

#### 🔍 Prompt 2: Code Reviewer de Queries e Performance
Você é um DBA especialista em SQL Server. Analise o script T-SQL abaixo buscando gargalos de performance, violações de boas práticas de indexação ou uso incorreto de cursores e funções escalares. Proponha uma versão otimizada utilizando abordagens set-based ou CTEs se aplicável. 
[Insira seu código T-SQL aqui]

#### 📑 Prompt 3: Simulador de Entrevistas Técnicas
Quero que você simule uma entrevista técnica para uma vaga de Desenvolvedor de Banco de Dados SQL Server. Me faça 3 perguntas conceituais difíceis sobre T-SQL (focando em concorrência, isolamento de transações ou planos de execução). Faça uma pergunta de cada vez e aguarde minha resposta para avaliá-la e me dar o feedback técnico.
