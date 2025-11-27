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
| v1.4   | 29/11/2025 | Revisão final com integração dos diagramas conceitual e experimental |

### 1.4 Datas  

Criação do plano: 23/11/2025  
Última atualização: 29/11/2025  

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



    P1 --> BD[(Banco Relacional)]
    P2 --> BD
    P3 --> BD
