# Plano de Experimento – Scoping e Planejamento  
## Tema: Impacto da Adoção de Testes Unitários Automatizados em Sistemas Móveis Baseados em Arquitetura de Microserviços Distribuídos

## 1. Identificação Básica

### 1.1 Título do Experimento  
Avaliação do Impacto de Testes Unitários Automatizados no Tempo de Entrega de Funcionalidades em Sistemas Móveis com Backend em Microserviços Distribuídos Desenvolvidos em Python.

### 1.2 ID / Código  
EXP-MSD-TU-2025

### 1.3 Versão do Documento e Histórico de Revisão  

| Versão | Data | Descrição |
|--------|------|-----------|
| v1.0   | 23/11/2025 | Versão inicial do documento |
| v1.1   | 24/11/2025 | Inclusão das tabelas GQM e métricas |
| v1.2   | 27/11/2025 | Inclusão das seções de modelo conceitual, variáveis e desenho experimental |
| v1.3   | 28/11/2025 | Ajustes conceituais alinhados ao trade-off entre lead time e qualidade |
| v1.4   | 28/11/2025 | Revisão final com integração dos diagramas conceitual e experimental |
| v1.5   | 29/11/2025 | Inclusão de dados Pré-execução |
| v1.6   | 04/12/2025 | Inclusão de ameaças a validade |
| v2.0   | 05/12/2025 | Conclusao do Trabalho |


### 1.4 Datas  

Criação do plano: 23/11/2025  
Última atualização: 05/12/2025  

### 1.5 Autores  

Nome: Augusto Noronha Leite  
Área: Engenharia de Software / Arquitetura de Sistemas Distribuídos  
Contato: augustonoronha03@gmail.com  

### 1.6 Responsável Principal  
Augusto Noronha Leite.

### 1.7 Projeto / Produto / Iniciativa Relacionada  
Aplicação móvel consumindo APIs Python em microserviços com pipelines automatizadas.

---

## 2. Contexto e Problema

### 2.1 Descrição do Problema / Oportunidade

Equipes que desenvolvem sistemas móveis baseados em microserviços distribuídos enfrentam desafios relacionados à previsibilidade, qualidade e tempo de entrega. A arquitetura distribuída aumenta a necessidade de integração contínua e eleva o risco de defeitos pós-deploy, tornando o processo sujeito a retrabalho. A adoção sistemática de testes unitários é frequentemente citada como um mecanismo capaz de reduzir incidentes e melhorar estabilidade, mas exige esforço adicional que tende a aumentar o lead time no curto prazo.

Este experimento busca analisar esse trade-off, verificando se o aumento inicial no tempo de entrega é compensado por benefícios em qualidade, confiabilidade e estabilidade da pipeline ao longo de três sprints de desenvolvimento de funcionalidades equivalentes.

### 2.2 Contexto Organizacional e Técnico

O backend consiste em microserviços Python que expõem APIs REST consumidas por um aplicativo móvel. Cada alteração dispara automaticamente pipelines configuradas com Pytest (grupo tratamento) ou apenas build (grupo controle). Métricas como duração de pipeline, falhas, timestamps e cobertura são coletadas automaticamente em banco relacional.

### 2.3 Trabalhos e Evidências Prévias

Estudos mostram que testes unitários aumentam a confiabilidade e diminuem defeitos, mas exigem esforço adicional inicial. A literatura destaca que desenvolvedores testam menos do que acreditam e que a adoção disciplinada de testes aumenta a detecção precoce de falhas, o que pode reduzir retrabalho e incidentes em produção.

### 2.4 Referencial Teórico e Empírico Essencial

Este experimento se apoia em engenharia de software experimental, CI/CD, confiabilidade de software, cobertura de testes e estudos empíricos sobre adoção de testes unitários, fornecendo base para análise das relações entre esforço inicial e benefícios posteriores.

---

## 3. Objetivos e Questões (Goal / Question / Metric)

### 3.1 Objetivo Geral  
Analisar o impacto da adoção sistemática de testes unitários automatizados em microserviços Python, avaliando o trade-off entre maior lead time e melhoria de qualidade, previsibilidade e estabilidade da pipeline.

## 3.2 Objetivos Específicos

### 3.2.1 Objetivo Específico 1 – Impacto no Lead Time  
Mensurar como a obrigatoriedade de testes unitários impacta o lead time de desenvolvimento, considerando a expectativa de aumento inicial do tempo.

### 3.2.2 Objetivo Específico 2 – Redução de Defeitos  
Avaliar se equipes que adotam testes unitários apresentam menor quantidade e severidade de defeitos pós-deploy.

### 3.2.3 Objetivo Específico 3 – Percepção das Equipes  
Investigar como testes unitários influenciam confiança, clareza percebida e motivação dos desenvolvedores.

### 3.2.4 Objetivo Específico 4 – Estabilidade da Pipeline  
Avaliar a relação entre testes unitários e estabilidade da pipeline, considerando falhas, tempo total e variabilidade de execução.

### 3.3 Questões de Pesquisa  
As questões de pesquisa consideram explicitamente o trade-off entre esforço inicial e benefícios posteriores. Reconhece-se que o lead time tende a aumentar no curto prazo, mas esse custo pode ser compensado ao reduzir defeitos, retrabalho e instabilidade operacional ao longo das sprints.

### 3.4 Tabela GQM – Objetivos, Perguntas e Métricas

| Objetivo | Perguntas (Q) | Métricas (M) |
|----------|---------------|-------------|
| O1 – Lead Time | Q1.1 A obrigatoriedade de testes unitários aumenta o lead time? Q1.2 O esforço de testes impacta o tempo de build? Q1.3 A cadência de releases diminui no curto prazo? | M1, M2, M3 |
| O2 – Defeitos | Q2.1 Defeitos pós-deploy diminuem? Q2.2 A severidade média dos defeitos é menor? Q2.3 O tempo até detecção de falhas é reduzido? | M4, M5, M6 |
| O3 – Percepção | Q3.1 A confiança aumenta? Q3.2 A clareza do código melhora? Q3.3 A motivação para testar aumenta? | M7, M8, M9 |
| O4 – Pipeline | Q4.1 Falhas de pipeline diminuem? Q4.2 O tempo total muda? Q4.3 A variabilidade por execução é reduzida? | M10, M11, M12 |

## Tabela Geral de Métricas

| Métrica | Descrição | Unidade |
|--------|-----------|---------|
| M1 – Lead Time | Tempo entre início e deploy | horas ou dias |
| M2 – Tempo de Build | Duração do pipeline | minutos |
| M3 – Cadência de Releases | Releases por sprint | contagem |
| M4 – Defeitos Pós-Deploy | Incidentes após deploy | contagem |
| M5 – Severidade Média | Gravidade média | escala 1–5 |
| M6 – MTTA | Tempo até detecção | minutos/horas |
| M7 – Confiança Percebida | Avaliação subjetiva | Likert |
| M8 – Clareza do Código | Avaliação subjetiva | Likert |
| M9 – Motivação para Testar | Avaliação subjetiva | Likert |
| M10 – Falhas de Pipeline | Número de falhas | contagem |
| M11 – Tempo da Pipeline | Tempo total | minutos |
| M12 – Variabilidade | Variação percentual | percentual |

---

# 4. Escopo e Participantes

(… conteúdo preservado …)

---

# 5. Instrumentação e Materiais – Versão Final (somente Pytest)

A única ferramenta de testes utilizada no experimento será o **Pytest**, com cobertura medida por meio do plugin oficial **pytest-cov**. A pipeline do grupo tratamento executará Pytest a cada commit, gerando métricas de cobertura, tempo de execução, falhas e duração do build. Todos os dados serão armazenados automaticamente em um banco relacional, sem intervenção manual.

Ambiente padronizado com mesma versão do Python, mesmas bibliotecas e mesmos frameworks web. Scripts auxiliares transformarão logs em tabelas para análise estatística.

---

## 6. Procedimentos Operacionais

(… conteúdo preservado …)

---

# 7. Modelo Conceitual e Hipóteses

## 7.1 Modelo Conceitual  
A relação esperada entre testes unitários e variáveis observadas envolve aumento inicial do lead time, seguido de redução de defeitos, maior confiança no código e maior estabilidade da pipeline. O efeito global esperado é um trade-off entre esforço inicial e benefícios posteriores.

### **Diagrama Conceitual (Mermaid)**

<img width="567" height="540" alt="image" src="https://github.com/user-attachments/assets/bf5e6087-19bb-44cf-bc9e-4d139a0d03a9" />

### 7.2 Hipóteses Formais  

**Hipóteses relacionadas ao objetivo O1 – Lead Time**  
H0_1: Não há diferença significativa no lead time entre equipes com e sem testes unitários.  
H1_1: O lead time médio por funcionalidade é maior nas equipes que adotam testes unitários automatizados.  
H1_1b: O aumento do lead time inicial é compensado por redução de defeitos e retrabalho ao longo das sprints.

**Hipóteses relacionadas ao objetivo O2 – Defeitos**  
H0_2: Não há diferença significativa no número de defeitos pós-deploy entre os grupos.  
H1_2: O número de defeitos pós-deploy é menor nas equipes que adotam testes unitários.

**Hipóteses relacionadas ao objetivo O3 – Percepção**  
H0_3: Não há diferença significativa na percepção de confiança, clareza e motivação.  
H1_3: Equipes que adotam testes unitários relatam maior confiança, clareza percebida e motivação.

**Hipóteses relacionadas ao objetivo O4 – Pipeline**  
H0_4: Não há diferença significativa na estabilidade da pipeline.  
H1_4: A pipeline apresenta menor variabilidade e menor número de falhas quando testes unitários são obrigatórios.

---

## 8. Variáveis, Fatores, Tratamentos e Objetos de Estudo

### 8.1 Objetos de Estudo  

Os objetos de estudo são as funcionalidades de uma aplicação de lista de tarefas implementadas em microserviços Python ao longo de um conjunto de sprints. Cada funcionalidade envolve alterações em código de produção e, no caso do grupo tratamento, a criação ou atualização dos testes unitários correspondentes. Também são considerados objetos de estudo os registros das execuções de pipeline e dos incidentes pós-deploy associados a essas funcionalidades.

### 8.2 Sujeitos / Participantes (Visão Geral)  

Os participantes do experimento são desenvolvedores de software organizados em duas equipes. Cada equipe é composta por um desenvolvedor sênior, um desenvolvedor pleno e um desenvolvedor júnior. A composição é mantida equivalente entre os grupos para reduzir o impacto de diferenças de experiência no resultado.

### 8.3 Variáveis Independentes (Fatores) e seus Níveis  

O fator principal é a prática de testes unitários automatizados.  

Fator F1 – Prática de testes unitários automatizados  
Nível 1: Sem obrigatoriedade de testes unitários (grupo controle).  
Nível 2: Com obrigatoriedade de testes unitários, incluindo critérios mínimos de cobertura (grupo tratamento).

Um segundo fator implícito é o tempo, representado pelas sprints do projeto, utilizado principalmente para análise por período, mas não tratado como fator experimental principal.

### 8.4 Tratamentos (Condições Experimentais)

Serão consideradas duas condições experimentais.  

Tratamento T0 – Controle: equipes desenvolvem as funcionalidades da aplicação em Python sem a obrigação de escrever testes unitários automatizados. Podem realizar testes manuais ou verificações informais conforme sua prática usual.  

Tratamento T1 – Testes unitários obrigatórios: equipes desenvolvem as mesmas funcionalidades, mas com a obrigação de escrever e manter testes unitários automatizados para o código novo ou modificado, com meta de cobertura previamente acordada.

### 8.5 Variáveis Dependentes (Respostas)

As principais variáveis de resposta são diretamente associadas às métricas definidas no GQM. São observados o lead time por funcionalidade, a quantidade e severidade de defeitos pós-deploy, o tempo médio para detecção de falhas, os indicadores de percepção das equipes (confiança, clareza e motivação) e os indicadores de comportamento da pipeline de integração contínua, como número de falhas, tempo de execução e variabilidade entre execuções.

### 8.6 Variáveis de Controle / Bloqueio  

Alguns fatores serão mantidos constantes ou utilizados como base de bloqueio, para reduzir variações externas. O tipo de projeto é o mesmo para todos os participantes, consistindo em uma aplicação de lista de tarefas. A linguagem de implementação é sempre Python, com conjunto semelhante de bibliotecas e ferramentas. A composição das equipes é balanceada, com uma combinação semelhante de sênior, pleno e júnior em cada grupo. As tarefas por sprint serão definidas de forma equivalente para as equipes, com o mesmo escopo funcional e critérios de aceitação.

### 8.7 Possíveis Variáveis de Confusão Conhecidas  

São reconhecidas como potenciais variáveis de confusão as diferenças individuais de habilidade entre desenvolvedores, mesmo dentro dos mesmos níveis de senioridade, variações de motivação ao longo do tempo, diferenças de familiaridade com Python ou com as ferramentas de CI e possíveis mudanças de requisitos durante os sprints. Essas variáveis serão monitoradas qualitativamente e, quando possível, registradas para posterior discussão na análise de ameaças à validade.

---

## 9. Desenho Experimental

### 9.1 Tipo de Desenho  

O desenho experimental adotado é um estudo controlado com dois grupos paralelos, um grupo controle e um grupo tratamento, em que cada grupo é composto por uma equipe de três desenvolvedores (sênior, pleno e júnior). Ambos os grupos implementam o mesmo backlog de funcionalidades ao longo de um número fixo de sprints. A principal diferença entre os grupos é a obrigatoriedade de testes unitários automatizados no grupo tratamento.

### 9.2 Randomização e Alocação  

Os participantes serão alocados às equipes de forma a equilibrar níveis de experiência entre os grupos. Quando houver mais desenvolvedores disponíveis, será possível realizar a distribuição por sorteio estratificado, garantindo que cada equipe contenha um sênior, um pleno e um júnior. As tarefas por sprint serão distribuídas de maneira equivalente entre as equipes, de modo que a dificuldade média e o esforço estimado sejam comparáveis.

### 9.3 Balanceamento e Contrabalanço  

O balanceamento será obtido pelo uso do mesmo conjunto de funcionalidades para ambas as equipes, pela manutenção da mesma composição de senioridade e pela adoção do mesmo ambiente técnico de desenvolvimento, repositório e ferramentas. Como as sprints seguem a mesma ordem de funcionalidades, não haverá contrabalanço de ordem de tarefas; a análise considerará o efeito de aprendizado ou de adaptação das equipes ao longo do tempo como parte da interpretação dos resultados.

### 9.4 Número de Grupos e Sprints  

O experimento considera dois grupos de desenvolvimento, um sob tratamento T0 e outro sob tratamento T1. O projeto será organizado em três sprints principais. Em uma configuração típica, a primeira sprint cobre o CRUD básico de tarefas em Python e a infraestrutura inicial do projeto. A segunda sprint amplia funcionalidades com atributos adicionais de tarefas, como prioridade e data de vencimento. A terceira sprint introduz funcionalidades adicionais, como autenticação simples ou categorização de tarefas. Em todas as sprints, as equipes trabalharão sobre o mesmo backlog funcional, permitindo a comparação direta das métricas entre os grupos.

<img width="1146" height="372" alt="image" src="https://github.com/user-attachments/assets/264c0a2b-f460-4973-882c-3fcb7e03ab6c" />
<img width="443" height="547" alt="image" src="https://github.com/user-attachments/assets/1b0a63bc-cc00-4efb-b045-fc561facbce7" />

## 10. População, Sujeitos e Amostragem

A população-alvo deste experimento é composta por desenvolvedores de software distribuídos em três níveis de senioridade: júnior, pleno e sênior. A seleção dos participantes utiliza um processo de amostragem aleatória estratificada, no qual cada nível de senioridade representa um estrato distinto.

Primeiro, os desenvolvedores são organizados nesses três estratos; em seguida, realiza-se um sorteio aleatório dentro de cada estrato para determinar quais profissionais participarão do experimento. Após essa etapa de seleção, procede-se à alocação aleatória balanceada, garantindo que ambos os grupos experimentais contenham exatamente um desenvolvedor sênior, um pleno e um júnior.

Essa abordagem mantém equivalência entre as equipes, reduz a influência de diferenças individuais de habilidade ou experiência e permite isolar o efeito do fator experimental a presença ou ausência de testes unitários obrigatórios sobre as variáveis observadas.

Como ambos os grupos implementam o mesmo backlog em três sprints e sob condições controladas, a amostra é suficiente para comparar métricas de desempenho, qualidade e percepção ao longo das etapas do experimento.

## 11. Instrumentação e Protocolo Operacional

O experimento utiliza um repositório Git como ambiente central para versionamento de código e execução automática das pipelines. O Pytest é a ferramenta obrigatória para o grupo tratamento, com coleta de cobertura via pytest-cov. As pipelines são responsáveis por executar build, rodar testes e registrar logs estruturados contendo métricas como tempo de execução, sucesso ou falha, timestamps e cobertura, quando aplicável.

O protocolo operacional inicia com a preparação do repositório, criação dos microserviços Python e configuração das pipelines no GitHub Actions. Cada funcionalidade implementada em uma sprint deve ser desenvolvida em uma branch específica, permitindo identificar claramente o início e o fim do lead time por funcionalidade. A equipe controle realiza apenas as etapas de desenvolvimento e build, enquanto o grupo tratamento executa automaticamente testes unitários e valida a cobertura mínima de 70%.

Os logs gerados são enviados para um banco relacional, constituindo o repositório de dados do experimento. Cada registro contém identificadores da sprint, funcionalidade, commit, desenvolvedor responsável, métricas de pipeline e indicadores de erros pós-deploy. Após cada sprint, os dados são consolidados e validados para garantir integridade, consistência e ausência de registros duplicados.
## 12. Plano de Análise de Dados (Pré-Execução)

A análise dos dados será conduzida em três etapas. A primeira etapa consiste na preparação dos dados, envolvendo limpeza, normalização, identificação de inconsistências e remoção de outliers quando justificável. Os registros do banco relacional serão exportados para um ambiente de análise, como um script Python , onde serão aplicadas técnicas estatísticas adequadas.

A segunda etapa compreende a comparação estatística entre os grupos controle e tratamento. Para métricas contínuas, como lead time, tempo de pipeline e variabilidade, será aplicado o teste de Mann–Whitney, adequado para distribuições que não assumem normalidade. Para métricas discretas, como número de falhas de pipeline e incidentes pós-deploy, será utilizado o teste Qui-quadrado. Cada hipótese definida previamente em H0/H1 será avaliada considerando um nível de significância de 5%.

A terceira etapa envolve interpretação dos resultados à luz do modelo conceitual. Se houver aumento significativo no lead time mas redução significativa nos defeitos e na instabilidade da pipeline, o trade-off esperado será confirmado. Também serão analisados os dados qualitativos de percepção coletados junto aos desenvolvedores, integrando métricas subjetivas e métricas objetivas. A análise final consolidará os achados, destacará padrões observados e relacionará os resultados às hipóteses e às ameaças à validade.

# 13. Avaliação da Validade

Nesta seção, identificamos e abordamos as principais ameaças à validade do experimento, garantindo que as conclusões sobre o impacto da adoção de testes unitários obrigatórios sejam robustas e bem fundamentadas.

---

## 13.1 Validade de Conclusão

A validade de conclusão se concentra em garantir que as inferências estatísticas entre o tratamento (Testes Unitários) e os resultados observados sejam corretas. As principais ameaças são:

* Tamanho Reduzido da Amostra: O número limitado de participantes e grupos reduz o poder estatístico, aumentando o risco de resultados inconclusivos (Erro Tipo II) ou de não detectar um efeito real.
* Ruído da Infraestrutura: Variações de desempenho de serviços externos (Railway e GitHub Actions) podem introduzir ruído nas medições de tempo de pipeline e build, reduzindo a precisão das estimativas de tempo.
* Inconsistências nos Dados: A confiabilidade das conclusões depende da integridade dos dados, que pode ser comprometida por falhas de coleta, registros incompletos ou inconsistências nos logs.

### 13.1.1 Estratégias de Mitigação: Padronização e Limpeza

A mitigação envolve a padronização rigorosa da infraestrutura antes do início das sprints e a aplicação de procedimentos de limpeza e verificação dos dados.

### 13.1.2 Estratégias de Mitigação: Testes Estatísticos

Para lidar com a amostra reduzida, serão empregados testes estatísticos não paramétricos, que são adequados ao tamanho da amostra e não dependem do pressuposto de normalidade dos dados: Mann–Whitney para variáveis contínuas e Qui-quadrado para variáveis discretas.

---

## 13.2 Validade Interna

A validade interna garante que o efeito observado é, de fato, causado pela variável independente (obrigatoriedade de testes) e não por fatores de confusão não controlados. As ameaças primárias são:

* Diferenças Individuais de Habilidade: Variações na habilidade e produtividade entre desenvolvedores, mesmo dentro do mesmo nível de senioridade, podem influenciar o tempo de entrega e a qualidade do código.
* Efeito de Aprendizagem: O desempenho das equipes pode melhorar ao longo das sprints devido à familiaridade crescente com o código-base ou o ambiente técnico, confundindo o efeito do tratamento.
* Interrupções Externas: Instabilidades inesperadas em serviços de hospedagem ou integrações podem alterar artificialmente as métricas de tempo de execução (builds e testes).

### 13.2.1 Estratégias de Mitigação: Controle de Grupos

O desenho experimental busca isolar o efeito do tratamento por meio de amostragem aleatória estratificada, que garante o equilíbrio de senioridade entre os grupos (sênior, pleno, júnior) para reduzir vieses de seleção.

### 13.2.2 Estratégias de Mitigação: Controle de Tarefas e Ambiente

Será utilizado backlog idêntico, tarefas equivalentes e manutenção da mesma ordem de implementação para ambos os grupos. O ambiente técnico e as ferramentas serão padronizados.

### 13.2.3 Estratégias de Mitigação: Registro de Ocorrências

Será realizado um registro estruturado de quaisquer ocorrências ou interrupções inesperadas (instabilidades em serviços, falhas de rede) que possam impactar as medições.

---

## 13.3 Validade de Constructo

A validade de constructo trata da adequação das métricas operacionais para representar os conceitos teóricos que se deseja medir (e.g., Qualidade, Confiança, Lead Time). As ameaças incluem a sub-representação dos conceitos:

* Cobertura $\neq$ Qualidade: A meta mínima de cobertura de testes (70%) é uma métrica estrutural que não garante a qualidade ou eficácia dos testes unitários escritos.
* Viés em Métricas Subjetivas: As medidas de percepção (Confiança, Clareza e Motivação) podem ser vulneráveis a vieses individuais e diferenças de interpretação na escala Likert.
* Ruído em Métricas Operacionais: O lead time e a variabilidade da pipeline podem refletir ruído técnico externo não relacionado ao constructo principal do "impacto da adoção de testes unitários".

### 13.3.1 Estratégias de Mitigação: Definição e Coleta

A mitigação é alcançada pelo fortalecimento do alinhamento entre o conceito teórico e sua medição por meio de definições operacionais claras para cada variável.

### 13.3.2 Estratégias de Mitigação: Padronização de Instrumentos

Será utilizada a coleta automatizada de métricas para eliminar a interferência humana e a aplicação consistente dos mesmos questionários, escalas e formulários para todos os participantes.

---

## 13.4 Validade Externa

A validade externa refere-se à capacidade de generalizar os resultados do experimento para outros contextos, sistemas ou populações de desenvolvedores.

* Limitação do Contexto: O experimento é conduzido em um ambiente controlado, utilizando uma aplicação de complexidade moderada (lista de tarefas) e infraestrutura simplificada.
* Escopo Reduzido: Os resultados podem não se generalizar para sistemas enterprise maiores, equipes numerosas, pipelines de CI/CD complexas ou arquiteturas altamente distribuídas.
* Especificidade Tecnológica: O foco em microserviços Python e na ferramenta Pytest restringe a extrapolação para outras linguagens ou ecossistemas de testes.

### 13.4.1 Estratégias de Mitigação: Delimitação Explícita

A generalização deve ser explicitamente restrita a cenários que compartilham as características do experimento: times pequenos, microserviços de baixa complexidade, pipelines leves e adoção disciplinada de testes unitários.

### 13.4.2 Estratégias de Mitigação: Interpretação Restrita

As diferenças significativas de contexto em relação ao ambiente de produção (enterprise) serão detalhadas e delimitadas no relatório final, restringindo a interpretação a cenários similares.

---

## 13.5 Resumo das Ameaças e Estratégias de Mitigação

| Tipo de Validade | Ameaças Principais | Estratégias de Mitigação |
|---|---|---|
| Conclusão | Amostra pequena; Ruído da infraestrutura/tempo; Inconsistências de dados | Testes estatísticos robustos (Mann-Whitney, Qui-quadrado); Padronização e Limpeza de Dados |
| Interna | Diferenças de habilidade individual; Efeito de aprendizado; Instabilidades externas | Amostragem Estratificada; Backlog/Tarefas Equivalentes; Registro de Ocorrências e Ambiente Padronizado |
| Constructo | Cobertura $\neq$ Qualidade de Teste; Viés em Métricas Subjetivas; Ruído em Métricas Operacionais | Definições Operacionais Claras; Coleta Automatizada; Padronização de Questionários |
| Externa | Baixa Generalização para Projetos Maiores, Outras Arquiteturas ou Linguagens | Delimitação Explícita do Escopo; Interpretação Restrita a Cenários Similares |
## 14. Ética, Privacidade e Conformidade

### 14.1 Questões Éticas

O principal risco ético identificado neste experimento é o de **exposição involuntária do desempenho individual dos participantes**. Como métricas como lead time, número de defeitos, falhas de pipeline e outros indicadores técnicos são coletadas automaticamente, existe a possibilidade de que participantes se sintam avaliados, julgados ou comparados entre si, mesmo que o experimento não tenha finalidade de medir produtividade pessoal.

Esse tipo de risco é relevante mesmo em ambientes neutros ou voluntários, pois desenvolvedores podem interpretar os resultados como reflexo direto de suas habilidades. Para mitigar esse risco, todas as métricas serão tratadas de forma anonimizada, associadas apenas a identificadores internos e nunca aos nomes reais dos participantes. Resultados individuais não serão divulgados; somente dados agregados por grupo serão analisados e apresentados.

Além disso, todos os participantes serão informados previamente de que o objetivo do experimento é avaliar práticas de desenvolvimento com ou sem testes unitários, e não avaliar desempenho ou habilidade de cada indivíduo. Os participantes poderão solicitar a remoção de sua identificação a qualquer momento, reforçando que sua participação é totalmente voluntária e não implica qualquer forma de avaliação pessoal.

### 14.2 Consentimento Informado
Antes do início das atividades, todos os participantes receberão um documento de explicação contendo:  
• o objetivo do experimento  
• os procedimentos envolvidos  
• os riscos e benefícios potenciais  
• o tipo de dados coletados  
• como esses dados serão analisados  
• como sua identidade será preservada  
• o direito de desistência a qualquer momento  

Após a leitura desse documento, os participantes deverão registrar seu consentimento informado por meio de um formulário digital, confirmando que compreenderam todas as informações e concordam voluntariamente em participar. Esse consentimento será armazenado de forma segura para fins de auditoria e transparência metodológica.

### 14.3 Privacidade e Proteção de Dados
O experimento coleta apenas dados técnicos relacionados ao desenvolvimento, tais como:  
• timestamps de commits  
• tempos de pipeline  
• métricas de testes  
• cobertura  
• falhas de execução  
• quantidade e severidade de defeitos  

Nenhum dado pessoal sensível será coletado. A única informação identificável é o nome ou identificador de usuário no repositório Git, utilizado exclusivamente para associar commits às funcionalidades. Esses identificadores serão anonimizados durante a análise, substituídos por códigos numericos, impedindo a associação direta entre dados e indivíduos.  
O banco relacional utilizado para armazenar as métricas ficará protegido por autenticação, controle de acesso e criptografia em repouso. Os dados serão mantidos por até 12 meses após o término do experimento exclusivamente para fins de auditoria e replicação, sendo posteriormente removidos de forma segura.

### 14.4 Aprovações Necessárias

Como o experimento não é conduzido em ambiente acadêmico nem profissional formal, não há necessidade de submissão a comitês institucionais de ética ou aprovação de órgãos jurídicos internos. No entanto, para garantir transparência e responsabilidade no tratamento dos dados, o estudo seguirá as diretrizes gerais de ética em pesquisa com seres humanos e as boas práticas de proteção de dados definidas pela LGPD.

Os participantes serão informados sobre os procedimentos, riscos e formas de proteção de dados antes do início do experimento, e sua participação ocorrerá somente após o registro de consentimento informado. Não há outras aprovações externas obrigatórias para a realização deste estudo.

## 15. Recursos, Infraestrutura e Orçamento

### 15.1 Recursos Humanos e Papéis

O experimento contará com um grupo reduzido de participantes e funções claramente definidas para garantir organização e rastreabilidade. Os papéis são distribuídos da seguinte forma:

• Pesquisador responsável : conduz o experimento, elabora o plano, organiza os dados, supervisiona a execução das sprints, consolida as métricas e realiza a análise estatística.  
• Desenvolvedores participantes (6 no total)– distribuídos em dois grupos, cada qual composto por um desenvolvedor sênior, um pleno e um júnior. São responsáveis por implementar as funcionalidades conforme o backlog, interagir com o repositório Git e acionar as pipelines que geram os dados analisados.  
• Apoio técnico opcional: responsável pela configuração inicial do ambiente, incluindo criação do repositório, configuração das pipelines de CI/CD e integração com o banco de dados. Se necessário, também presta suporte durante a coleta automática de métricas.

Todos os participantes atuam de forma independente no desenvolvimento, e nenhum deles é avaliado individualmente.

### 15.2 Infraestrutura Técnica Necessária

Para garantir a execução uniforme e reprodutível do experimento, é necessária a seguinte infraestrutura:

• Repositório Git para versionamento e registro dos commits.  
• Pipeline de CI/CD configurada em GitHub Actions, com execução automática a cada commit.  
• Ambiente de execução Python padronizado, com dependências definidas em `requirements.txt`.  
• Ferramentas de teste: Pytest, exclusivamente.  
• Banco relacional para armazenar registros das execuções das pipelines: PostgreSQL.  
• Servidor simples para hospedar os microserviços Python em homologação, permitindo detecção de defeitos pós-deploy.  
• Acesso a máquinas de desenvolvimento equivalentes entre os participantes, garantindo condições homogêneas.  

Toda a infraestrutura pode ser disponibilizada localmente ou em ambiente em nuvem, desde que mantenha consistência entre os grupos.

### 15.3 Materiais e Insumos

Antes do início do experimento, é necessário disponibilizar os seguintes materiais:

• Máquinas de desenvolvimento com Python 3 instalado .  
• Licenças ou acessos gratuitos às ferramentas que serão utilizadas utilizadas.  
• Templates de backlog e checklist por funcionalidade para padronizar a execução das sprints.  
• Formulário digital de consentimento informado.  
• Scripts auxiliares para coleta e transformação dos logs de pipeline.  
• Estrutura inicial dos microserviços Python de forma que o projeto base seja idêntico para ambas as equipes.  

Não há necessidade de materiais físicos, dispositivos especializados ou aquisições de software proprietários.

### 15.4 Orçamento e Custos Estimados

O experimento utiliza ferramentas essencialmente gratuitas, o que reduz significativamente o custo total. A participação dos desenvolvedores é voluntária e não envolve pagamentos ou compensações financeiras. Dessa forma, os custos diretos concentram-se apenas na infraestrutura necessária para execução do experimento.

Os custos previstos são:

• Hospedagem dos microserviços no Railway: será utilizado um plano básico pago para manter os serviços acessíveis durante as sprints e possibilitar a coleta de dados e detecção de defeitos pós-deploy. Este é o principal custo operacional do experimento.  
• Infraestrutura de CI/CD no GitHub Actions: a camada gratuita é suficiente para o volume esperado de execuções, não havendo previsão de custos adicionais.  
• Ferramentas de desenvolvimento e testes: Python, Pytest, pytest-cov, Git e demais ferramentas utilizadas são gratuitas e não geram custos diretos.  
• Banco de dados relacional: será hospedado no Railway, utilizando o mesmo ambiente de nuvem dos microserviços, permitindo consumo e visualização dos dados durante todo o experimento. Esse serviço está incluído no custo de hospedagem já previsto.  
• Ambiente local dos participantes: não gera custos ao experimento, uma vez que utiliza máquinas e ferramentas já disponíveis aos desenvolvedores.

Fonte de financiamento: os custos de infraestrutura, incluindo o plano de hospedagem no Railway, serão arcados pelo pesquisador responsável, não havendo financiamento externo ou institucional.

Com essa configuração, o orçamento total do experimento permanece reduzido e não representa obstáculo para sua execução.

# 16. Cronograma, Marcos e Riscos Operacionais

## 16.1 Macrocronograma (até o início da execução)

O cronograma abaixo apresenta os principais marcos necessários para que o experimento esteja pronto para ser executado. As datas são estimativas realistas, considerando tempo para preparação, revisões e configuração da infraestrutura.

| Marco | Descrição | Data Estimada |
|-------|-----------|----------------|
| Conclusão do Plano Experimental | Finalização do documento completo, incluindo validade, ética e orçamento | 05/12/2025 |
| Configuração do Repositório e Pipelines | Criação da estrutura dos microserviços, GitHub Actions e banco na Railway | 10/12/2025 |
| Execução de Piloto Técnico | Teste preliminar de uma funcionalidade para validar coleta de métricas | 12/12/2025 |
| Revisão do Piloto e Ajustes | Correções de logs, ajustes de pipeline e validação da infraestrutura | 15/12/2025 |
| Reunião de Alinhamento com Participantes | Explicação do fluxo, regras, backlog e consentimento informado | 18/12/2025 |
| Início Oficial da Sprint 1 | Início da execução real do experimento | 20/12/2025 |

---

## 16.2 Dependências entre atividades

As atividades do experimento possuem dependências diretas que condicionam seu início. Abaixo estão listadas as principais relações:

- A execução do piloto **depende da configuração da infraestrutura técnica** (repositório, CI/CD, banco de dados).
- A revisão e ajustes do piloto **dependem da análise dos resultados coletados no piloto**.
- A reunião de alinhamento com participantes **só ocorre após a versão final do plano e a infraestrutura validada pelo piloto**.
- O início das sprints **depende do consentimento informado** de todos os participantes.
- A coleta automatizada de métricas **depende da pipeline estar funcional e integrada ao banco no Railway**.

Essas dependências garantem que cada etapa inicie apenas quando os pré-requisitos estiverem completamente preparados.

---

## 16.3 Riscos Operacionais e Plano de Contingência

A seguir, são descritos os principais riscos operacionais associados ao cronograma e à disponibilidade de recursos, bem como as ações planejadas caso tais riscos se materializem.

### 16.3.1 Instabilidade dos Serviços de Hospedagem (Railway e GitHub Actions)

**Risco:** Interrupções ou lentidão podem afetar o tempo de pipeline, introduzindo ruído ou inviabilizando a coleta de métricas.  
**Mitigação:** Monitoramento constante do status dos serviços; repetição de pipelines afetadas; registro de incidentes.  
**Contingência:** Migração temporária para ambiente local ou para outro provedor gratuito (Render, Fly.io) caso a instabilidade persista.

---

### 16.3.2 Indisponibilidade de Participantes Durante as Sprints

**Risco:** Ausência de um desenvolvedor pode atrasar a execução das tarefas e comprometer a equivalência entre os grupos.  
**Mitigação:** Planejamento de janelas flexíveis e comunicação antecipada.  
**Contingência:** Redistribuição temporária das tarefas dentro da equipe; substituição por outro participante do mesmo nível de senioridade, se disponível.

---

### 16.3.3 Atraso na Configuração da Infraestrutura

**Risco:** Problemas técnicos na configuração do Railway, GitHub Actions ou banco podem atrasar o início do experimento.  
**Mitigação:** Realizar configuração com antecedência e testar com um piloto técnico.  
**Contingência:** Simplificar a arquitetura (monorepo temporário, pipelines reduzidas) até que o ambiente completo esteja operacional.

---

### 16.3.4 Falhas na Coleta Automática de Dados

**Risco:** Logs incompletos, falhas nos scripts ou erros de conexão com o banco podem comprometer o dataset.  
**Mitigação:** Scripts validados no piloto; logging detalhado; testes de integridade periódicos.  
**Contingência:** Execução manual de coleta corretiva baseada nos logs originais do GitHub Actions e histórico de deploys.

---

### 16.3.5 Atrasos no Cronograma por Sobrecarga do Pesquisador

**Risco:** O pesquisador responsável centraliza múltiplas tarefas (instrumentação, supervisão, análise), o que pode gerar gargalos.  
**Mitigação:** Planejamento conservador do cronograma; automatização máxima das tarefas de coleta.  
**Contingência:** Prorrogação de prazos internos ou delegação de tarefas técnicas simples (como revisão de logs).

---

### 16.3.6 Divergência de Entendimento do Backlog Entre os Grupos

**Risco:** Equipes podem interpretar tarefas de forma diferente, quebrando a equivalência experimental.  
**Mitigação:** Backlog detalhado, checklist por funcionalidade e exemplos claros de aceitação.  
**Contingência:** Revisão conjunta e redefinição das tarefas antes de retomar a sprint.

---

### 16.3.7 Risco de Perda de Dados no Railway

**Risco:** Quedas ou resets na instância podem resultar em perda parcial de registros.  
**Mitigação:** Backups automatizados semanais; exportação dos dados após cada sprint.  
**Contingência:** Recuperação a partir de logs brutos das pipelines, armazenados no GitHub.

---

## 17. Governança do Experimento

A governança estabelece como o experimento será conduzido, supervisionado e mantido antes do início da execução, garantindo rastreabilidade, organização e tomada de decisão clara.

---

### 17.1 Papéis e Responsabilidades Formais

A seguir, apresentam-se os papéis envolvidos e suas responsabilidades formais no experimento:

• Pesquisador responsável  
  - Define o desenho experimental, conduz ajustes metodológicos e supervisiona todas as etapas.  
  - Aprova mudanças estruturais no plano.  
  - Consolida dados, conduz análises e produz os relatórios finais.  

• Desenvolvedores participantes  
  - Executam as implementações conforme o backlog, gerando dados por meio das pipelines.  
  - Reportam problemas técnicos ou inconsistências observadas durante o desenvolvimento.  

• Apoio técnico 
  - Auxilia na preparação do ambiente, configuração das pipelines e integração com o banco de dados.  
  - Suporta o pesquisador em eventuais ajustes de infraestrutura.  

• Observadores externos 
  - Não tomam decisões, mas são informados sobre o andamento e podem revisar resultados consolidados.  

Fluxo de responsabilidade 
- Pesquisador responsável: responsável e aprovador.  
- Desenvolvedores: executores.  
- Apoio técnico: consultado quando necessário.  
- Observadores: informados.

---

### 17.2 Ritos de Acompanhamento Pré-Execução

Antes do início da Sprint 1, serão realizados três tipos de encontros para garantir que o experimento esteja alinhado técnica e operacionalmente:

• Reunião inicial de alinhamento  
  - Participantes: pesquisador, desenvolvedores e apoio técnico.  
  - Objetivos: revisar regras do experimento, validar o backlog, apresentar ferramentas e esclarecer dúvidas.  
  - Realização: uma única vez antes da preparação do ambiente.

• Checkpoints de preparação  
  - Participantes: pesquisador e apoio técnico.  
  - Objetivos: validar repositório Git, pipelines, banco de dados no Railway e ambiente Python.  
  - Frequência: conforme necessidade, até que toda a instrumentação esteja funcional.

• Revisão final pré-execução  
  - Participantes: pesquisador e desenvolvedores.  
  - Objetivos: confirmar que todos compreendem o fluxo de trabalho, consentimento informado e forma de registro de ocorrências.  
  - Realização: imediatamente antes do início da Sprint 1.

Esses ritos garantem que a execução não seja prejudicada por problemas estruturais evitáveis.

---

### 17.3 Processo de Controle de Mudanças no Plano

Alterações no desenho experimental, escopo ou métricas somente poderão ocorrer antes do início da Sprint 1. Mudanças durante a execução serão evitadas, exceto em casos de falhas críticas.

O processo formal segue as etapas abaixo:

1. Proposição  
   - Qualquer participante pode sugerir uma mudança.  
   - A proposta deve explicar a necessidade da alteração e o impacto esperado.

2. Análise  
   - O pesquisador responsável avalia a consistência da proposta, impactos metodológicos e riscos ao estudo.  
   - Se necessário, o apoio técnico verifica a viabilidade de implementação.

3. Aprovação ou rejeição  
   - Apenas o pesquisador responsável pode aprovar mudanças no plano.  
   - Alterações significativas (como mudança de métrica ou protocolo) devem ser registradas no histórico de versões.

4. Registro  
   - Toda mudança aprovada será documentada no histórico de revisão do plano de experimento.  
   - O registro incluirá data, descrição, motivação e impacto esperado.

5. Comunicação  
   - Todas as partes afetadas serão informadas antes que a mudança entre em vigor.

Esse fluxo garante rastreabilidade, evita decisões improvisadas e mantém a confiabilidade metodológica do experimento.

---

# 18. Plano de Documentação e Reprodutibilidade

Esta seção detalha como o experimento será organizado, documentado e disponibilizado de forma que possa ser reproduzido por outras equipes ou replicado futuramente com mínimo esforço adicional.

---

## 18.1 Repositórios e Convenções de Nomeação

Toda a documentação, scripts, instrumentos e dados coletados serão armazenados em um repositório Git público ou privado, organizado de forma padronizada para garantir rastreabilidade e reprodutibilidade.

**Repositório principal do experimento:**
`experiment-microservices-unittesting-2025`

**Estrutura inicial recomendada:**
/docs/ → Plano do experimento, anexos e diagramas
/scripts/ → Scripts de coleta, transformação e análise
/instrumentation/ → Pipelines, workflows e configurações do CI/CD
/data_raw/ → Dados brutos coletados automaticamente
/data_processed/ → Dados tratados para análise
/templates/ → Questionários, checklists e formulários
/microservices_base/ → Estrutura inicial padronizada dos microserviços
/analysis/ → Notebooks ou scripts de análise estatística


**Convenções de nomeação:**
- Arquivos de dados: `metric_<sprint>_<grupo>_<YYYYMMDD>.csv`
- Scripts: `collect_metrics.py`, `clean_dataset.py`, `analyze_results.py`
- Relatórios: `report_<versao>.md`
- Pipelines: `ci_pipeline.yml`, `pytest_pipeline.yml`

A versão final do documento será sempre registrada em `/docs/` com controle de versão Git.

---

## 18.2 Templates e Artefatos Padrão

Os seguintes artefatos serão disponibilizados para garantir consistência entre participantes e replicações futuras:

**1. Formulário de Consentimento Informado**
- Local: `/templates/consentimento.pdf`
- Usado antes do início da participação.

**2. Checklists Operacionais**
- Checklist por funcionalidade da sprint  
- Checklist de preparação do ambiente  
- Local: `/templates/checklists/`

**3. Questionários de Percepção**
- Avaliam confiança, clareza e motivação
- Aplicados ao final de cada sprint
- Local: `/templates/questionarios/`

**4. Scripts-padrão**
- Script para coleta automática: `/scripts/collect_metrics.py`
- Script de limpeza: `/scripts/clean_dataset.py`
- Script de análise: `/analysis/stats_mann_whitney.py`

**5. Configuração padrão do Pytest**
- Arquivo: `/instrumentation/pytest.ini`

**6. Workflow da pipeline**
- Arquivo: `/instrumentation/ci_pipeline.yml`

Esses artefatos garantem que tanto a execução quanto a futura replicação sigam exatamente o mesmo fluxo.

---

## 18.3 Plano de Empacotamento para Replicação Futura

Para garantir reprodutibilidade, todas as peças do experimento serão empacotadas de forma modular e reutilizável. O pacote de replicação conterá:

### **18.3.1. Documentação Completa**
- Plano do experimento (versão final)
- Diagramas conceitual e experimental
- Procedimentos operacionais detalhados
- Política de ética e privacidade
- Guia rápido de execução

### **18.3.2. Ambiente Técnico Reproduzível**
- Arquivo `requirements.txt` com versões fixas (pinadas)
- Arquivo `Dockerfile` opcional para execução padronizada dos microserviços
- Workflow CI/CD pré-configurado

### **18.3.3. Scripts Automatizados**
- Coleta de métricas
- Transformação e limpeza dos dados
- Geração dos datasets finais
- Execução de testes estatísticos

### **18.3.4. Artefatos Padronizados**
- Templates de questionários e checklists
- Estrutura-base dos microserviços
- Formulários de consentimento
- Modelo de relatório final

### **18.3.5. Instruções de Replicação**
Um documento chamado **`REPLICATE.md`** será incluído no repositório contendo:
- Como clonar o repositório
- Como configurar o ambiente (local e Railway)
- Como executar as pipelines
- Como iniciar as sprints
- Como coletar e validar dados
- Como executar a análise estatística
- Como comparar resultados com o experimento original

Esse empacotamento permitirá que novos pesquisadores repliquem o experimento mesmo anos após sua execução original, garantindo robustez científica e continuidade do estudo.

---
# 19. Plano de Comunicação

## 19.1 Públicos e Mensagens-Chave Pré-Execução

A comunicação pré-execução tem como objetivo garantir que todos os participantes compreendam o experimento, seu propósito e suas responsabilidades. Os públicos identificados e suas respectivas mensagens-chave são:

### • Participantes 
- Propósito do experimento.
- Descrição das atividades que deverão executar.
- Cronograma geral das sprints.
- Confirmação de que não haverá avaliação individual de desempenho.
- Garantia de anonimização e proteção de dados.

### • Pesquisador responsável
- Confirmação das datas oficiais de início das sprints.
- Regras para coleta e armazenamento dos dados.
- Checklist de infraestrutura necessária para a execução.

### • Apoio técnico 
- Configurações esperadas do repositório, pipelines, banco de dados e ambiente Railway.
- Deadlines para disponibilização da infraestrutura.

---

## 19.2 Canais e Frequência de Comunicação

A comunicação será realizada por meio de canais digitais de fácil acesso e registro:

| Canal | Uso Principal | Frequência |
|-------|---------------|------------|
| E-mail | Comunicados formais, documentação, atualizações importantes | Conforme necessidade (pontos-chave) |
| Grupo de mensagens (WhatsApp/Telegram) | Comunicação rápida, avisos operacionais, dúvidas | Diária durante as sprints |
| Reuniões virtuais | Alinhamentos, revisões e esclarecimentos | 1 reunião pré-execução e 1 por sprint |
| GitHub (issues / README) | Registro técnico, instruções e notificações da pipeline | Contínuo |

---

## 19.3 Pontos de Comunicação Obrigatórios

Alguns eventos exigem comunicação formal e registrada:

1. **Aprovação final do plano de experimento**  
   Comunicado enviado a todos os participantes confirmando datas, papéis e regras gerais.

2. **Disponibilização da infraestrutura**  
   Mensagem confirmando que o repositório, pipelines, Railway e banco de dados estão operacionais.

3. **Inicio oficial da Fase de Execução (Sprint 1)**  
   Comunicação com o marco de partida e responsabilidades de cada participante.

4. **Alterações relevantes no desenho experimental**  
   - Mudanças no backlog  
   - Ajustes de métricas  
   - Alterações nos critérios de coleta  
   Qualquer alteração deve ser documentada e enviada por e-mail.

5. **Interrupções ou incidentes críticos**  
   Exemplos: falhas graves no Railway, pipelines inutilizáveis ou perda de dados.

6. **Encerramento da Coleta de Dados**  
   Comunicado formal registrando o término da fase experimental.

7. **Entrega do Relatório Final**  
   O pesquisador envia a análise consolidada, resultados estatísticos e conclusões.

---

# 20. Critérios de Prontidão para Execução 

Esta seção define os critérios formais que precisam ser atendidos antes do início da execução do experimento. O objetivo é garantir que todas as condições mínimas de infraestrutura, documentação, comunicação e governança estejam estabelecidas, prevenindo falhas operacionais e riscos metodológicos.

---

## 20.1 Checklist de Prontidão

A execução do experimento somente poderá começar quando **todos os itens abaixo** estiverem concluídos, revisados e aprovados:

### 1. Documentação e Plano Experimental
- Plano de Experimento finalizado, revisado e aprovado.
- Modelo conceitual e desenho experimental concluídos e validados.
- Seções de validade, ética, governança, cronograma e orçamento finalizadas.
- Todos os instrumentos documentais (consentimento informado, questionários, checklists) concluídos.

### 2. Ambiente Técnico e Infraestrutura
- Repositório Git criado e acessível aos participantes.
- Estrutura base dos microserviços Python configurada e idêntica para ambas as equipes.
- Pipeline de CI/CD no GitHub Actions testada e funcional.
- Pytest configurado no repositório com coleta de cobertura (pytest-cov).
- Servidor Railway configurado para hospedagem dos microserviços.
- Banco de dados PostgreSQL no Railway criado, acessível e com tabelas necessárias para coleta automática de métricas.
- Scripts de coleta, transformação e consolidação dos dados revisados e testados.

### 3. Participantes e Comunicação
- Seleção final dos participantes por amostragem estratificada (júnior, pleno, sênior).
- Alocação aleatória dos participantes em seus respectivos grupos.
- Comunicação prévia enviada aos desenvolvedores com:
  - objetivos do experimento  
  - datas previstas  
  - responsabilidades  
  - instruções operacionais  
- Confirmação de recebimento e entendimento das instruções por todos os participantes.

### 4. Ética e Conformidade
- Texto de consentimento informado entregue aos participantes.
- Registro formal do aceite de todos os participantes.
- Garantias de anonimização e proteção de dados verificadas no banco e na pipeline.

### 5. Operação e Governança
- Definição do responsável por acompanhar cada sprint.
- Calendário com marcos, checkpoints e reuniões definido.
- Fluxo de controle de mudanças estabelecido.
- Critérios de bloqueio e retomada (go/no-go) documentados.

### 6. Teste Piloto
- Execução de um piloto técnico contendo:
  - commit de teste
  - execução da pipeline
  - coleta automática de métricas no Railway
- Verificação de ponta a ponta do fluxo completo (commit → pipeline → microserviço → banco de dados).

---

## 20.2 Aprovações Finais para Iniciar a Operação

Antes do início oficial da Sprint 1, é necessário registrar o aceite formal das seguintes partes:

### 1. Pesquisador Responsável
Confirma que:
- todo o plano está completo,
- infraestrutura foi testada,
- riscos foram avaliados,
- participantes estão instruídos.

Registro do aceite:  
**Assinatura digital ou formulário de confirmação.**

### 2. Participantes do Experimento
Confirmam que:
- compreenderam os objetivos,
- conhecem suas responsabilidades,
- concordam voluntariamente em participar,
- entenderam os riscos e garantias de privacidade.

Registro do aceite:  
**Formulário de consentimento informado.**

### 3. Apoio Técnico (se aplicável)
Confirma que:
- ambiente técnico está funcional,
- pipelines e integrações foram verificadas,
- servidor Railway está operacional.

Registro do aceite:  
**Checklist técnico assinado digitalmente.**

---

Após o registro de todas as aprovações, o experimento está oficialmente **“READY”**, autorizado para início da Sprint 1.







