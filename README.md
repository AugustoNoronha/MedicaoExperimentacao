# Plano de Experimento – Scoping e Planejamento  
## Tema: Impacto da Adoção de Testes Automatizados em Sistemas Móveis Baseados em Arquitetura de Microserviços Distribuídos

---

## 1. Identificação Básica

### 1.1 Título do Experimento  
Avaliação do Impacto de Testes Automatizados no Tempo de Entrega de Funcionalidades em Sistemas Móveis com Backend em Microserviços Distribuídos.

### 1.2 ID / Código  
EXP-MSD-TA-2025

### 1.3 Versão do Documento e Histórico de Revisão  

| Versão | Data | Descrição |
|--------|-------|------------|
| v1.0 | 23/11/2025 | Versão inicial do documento |
| v1.1 | 24/11/2025 | Revisão com inclusão das tabelas GQM e Métricas |

### 1.4 Datas  
- **Criação:** 23/11/2025  
- **Última atualização:** 24/11/2025  

### 1.5 Autores  
- **Nome:** Augusto Noronha Leite  
- **Área:** Engenharia de Software / Arquitetura de Sistemas Distribuídos  
- **Contato:** augustonoronha03@gmail.com  

### 1.6 Responsável Principal 
Augusto Noronha Leite.

### 1.7 Projeto / Produto / Iniciativa Relacionada  
Aplicações móveis corporativas consumindo APIs de microserviços distribuídos em nuvem (AWS/ECS).

---

## 2. Contexto e Problema

### 2.1 Descrição do Problema / Oportunidade

O desenvolvimento de sistemas móveis apoiados por arquiteturas de microserviços distribuídos impõe desafios significativos às equipes de engenharia, especialmente relacionados ao equilíbrio entre velocidade de entrega e qualidade do software. Ambientes altamente distribuídos tendem a apresentar maiores tempos de entrega devido ao número de serviços, às dependências entre sistemas e à necessidade de integração contínua. Além disso, é comum observar taxas elevadas de erros pós-deploy, o que afeta a estabilidade da aplicação e o tempo gasto com retrabalho.

Embora testes automatizados sejam amplamente reconhecidos como boas práticas, ainda há escassez de evidências empíricas que demonstrem o impacto direto dessa abordagem no tempo de entrega, na redução de incidentes e na melhoria operacional em pipelines CI/CD dentro de ecossistemas móveis. Straubinger et al. (2023) demonstram que muitos desenvolvedores desejam testar mais, mas enfrentam tanto limitações técnicas quanto motivacionais, e frequentemente subestimam a importância prática dos testes no fluxo de trabalho cotidiano :contentReference[oaicite:0]{index=0}. Outros estudos, como o de Rafi et al. (2012), reforçam que a automação de testes oferece benefícios mensuráveis — como aumento da confiabilidade, ampliação da cobertura e redução de tempo de execução — embora exista um custo inicial elevado para implementação e manutenção :contentReference[oaicite:1]{index=1}.

### 2.2 Contexto Organizacional e Técnico

O ambiente organizacional deste experimento envolve um ecossistema composto por aplicativos móveis (Android/iOS) que se comunicam com APIs hospedadas em microserviços distribuídos via AWS ECS. Cada serviço é empacotado em contêineres Docker e integrado por pipelines automatizados de CI/CD no GitHub Actions. As tecnologias mais utilizadas incluem Java, Spring Boot, Flutter/Kotlin, JUnit, Mockito, Postman/Newman e CloudWatch. Contudo, ainda não há um processo consolidado de automação de testes em todas as etapas do pipeline, o que motivou a necessidade deste estudo.

### 2.3 Trabalhos e Evidências Prévias

Diversos estudos destacam que testes automatizados podem elevar a estabilidade e reduzir retrabalho. Pesquisas focadas no comportamento de desenvolvedores, como a de Beller et al. (2019), mostram que muitos programadores acreditam testar mais do que realmente testam, apontando uma lacuna entre prática e percepção :contentReference[oaicite:2]{index=2}. Na área de confiabilidade, Malaiya et al. (2002) descrevem modelos que relacionam cobertura de testes e crescimento de confiabilidade, reforçando a importância da automação para detectar falhas mais rapidamente :contentReference[oaicite:3]{index=3}. Trabalhos que abordam TDD, como Kayongo et al. (2016), discutem fatores psicossociais que influenciam a adoção dessa prática e seus impactos em qualidade, defeitos e eficiência :contentReference[oaicite:4]{index=4}.

### 2.4 Referencial Teórico e Empírico Essencial

O experimento se fundamenta na Engenharia de Software Experimental (Wohlin), nos princípios de microserviços de Newman e Fowler, nos modelos e práticas de CI/CD descritos por Humble e Farley e nos conceitos de testes automatizados presentes na literatura empírica. Além disso, estudos recentes oferecem um panorama atualizado sobre benefícios, limitações e comportamentos de equipes frente à automação de testes, reforçando a relevância deste experimento.

---

## 3. Objetivos e Questões (Goal / Question / Metric)

### 3.1 Objetivo Geral  
O objetivo geral consiste em analisar o impacto da adoção de testes automatizados no processo de desenvolvimento de sistemas móveis baseados em microserviços distribuídos, buscando evidências sobre sua influência no tempo de entrega, estabilidade operacional e percepção de qualidade das equipes de engenharia.

### 3.2 Objetivos Específicos  

O experimento possui quatro objetivos principais. O primeiro consiste em medir o impacto da automação de testes no lead time de entrega, avaliando se a introdução de testes unitários, de integração e de contrato contribui para diminuir o tempo total necessário para disponibilizar novas funcionalidades. O segundo objetivo busca verificar se há redução na quantidade e severidade de defeitos registrados em produção após a automação. O terceiro pretende compreender a percepção das equipes sobre clareza, confiança e motivação após a inclusão de testes automatizados no fluxo de trabalho. O quarto objetiva comparar o comportamento do pipeline CI/CD antes e depois da inclusão de testes, analisando fatores como taxa de falhas, estabilidade e variabilidade entre execuções.

### 3.3 Questões de Pesquisa  

As questões de pesquisa associadas a cada objetivo buscam responder como a adoção de testes automatizados influencia o lead time, reduz incidentes, altera a percepção dos desenvolvedores e modifica o comportamento do pipeline CI/CD.

### 3.4 Tabela GQM – Objetivos, Perguntas e Métricas

| **Objetivo** | **Perguntas (Q)** | **Métricas (M)** |
|--------------|------------------|------------------|
| O1 – Impacto no tempo de entrega | Q1.1 A automação reduz o lead time? <br> Q1.2 O ciclo de build diminui após testes? <br> Q1.3 A cadência de releases aumenta? | M1, M2, M3 |
| O2 – Redução de defeitos | Q2.1 Há menos incidentes após a automação? <br> Q2.2 A severidade média dos erros diminui? <br> Q2.3 O tempo para detecção de falhas melhora? | M4, M5, M6 |
| O3 – Percepção dos desenvolvedores | Q3.1 A confiança no código aumenta? <br> Q3.2 A clareza do código melhora? <br> Q3.3 A motivação para testar evolui? | M7, M8, M9 |
| O4 – Comportamento do pipeline CI/CD | Q4.1 Pipelines falham menos? <br> Q4.2 O tempo total de execução diminui? <br> Q4.3 A variabilidade entre execuções é reduzida? | M10, M11, M12 |

---

## Tabela Geral de Métricas

| **Métrica** | **Descrição** | **Unidade** |
|-------------|---------------|-------------|
| M1 – Lead Time | Tempo entre início e deploy | horas/dias |
| M2 – Tempo de Build | Tempo total de compilação/teste | minutos |
| M3 – Frequência de Deploy | Quantidade de deploys por semana | contagem |
| M4 – Defeitos Pós-Deploy | Erros registrados após release | contagem |
| M5 – Severidade Média | Grau médio de criticidade | escala 1–5 |
| M6 – MTTA | Tempo médio até detecção | minutos/horas |
| M7 – Confiança Percebida | Sentimento dos devs sobre estabilidade | escala Likert |
| M8 – Clareza do Código | Avaliação subjetiva de legibilidade | escala Likert |
| M9 – Motivação para Testar | Disposição dos devs para testar | escala Likert |
| M10 – Falhas de Pipeline | Execuções do CI que resultam em erro | contagem |
| M11 – Tempo do Pipeline | Duração da pipeline completa | minutos |
| M12 – Variabilidade de Execução | Desvio entre execuções da pipeline | percentual |

---

