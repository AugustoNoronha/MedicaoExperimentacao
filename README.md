# Plano de Experimento 
## Tema: Impacto da Adoção de Testes Automatizados em Sistemas Móveis Baseados em Arquitetura de Microserviços Distribuídos

---

## 1. Identificação Básica

### 1.1 Título do Experimento
**Avaliação do Impacto de Testes Automatizados no Tempo de Entrega de Funcionalidades em Sistemas Móveis com Backend em Microserviços Distribuídos**

### 1.2 ID / Código  
EXP-MSD-TA-2025

### 1.3 Versão do Documento e Histórico de Revisão  
| Versão | Data | Descrição |
|--------|-------|------------|
| v1.0 | 23/11/2025 | Versão inicial do documento |

### 1.4 Datas  
- **Criação:** 23/11/2025  
- **Última atualização:** 23/11/2025  

### 1.5 Autores  
- **Nome:** Augusto Noronha Leite  
- **Área:** Engenharia de Software / Arquitetura de Sistemas Distribuídos  
- **Contato:** augustonoronha03@gmail.com  

### 1.6 Responsável Principal (PI)  
- **Augusto Noronha Leite**

### 1.7 Projeto / Produto / Iniciativa Relacionada  
Aplicações móveis que consomem APIs de microserviços distribuídos em nuvem (AWS/ECS).

---

## 2. Contexto e Problema

### 2.1 Descrição do Problema / Oportunidade  
Equipes que desenvolvem sistemas móveis apoiados por backends de microserviços distribuídos enfrentam desafios como:
- aumento no tempo de entrega de funcionalidades;
- maior incidência de erros pós-deploy;
- complexidade no controle de qualidade em ambientes distribuídos.

Ainda não há evidências empíricas suficientes sobre como **testes automatizados** (unitários, integração, contrato) afetam o **tempo de entrega** nesse tipo de arquitetura.

### 2.2 Contexto Organizacional e Técnico  
- Aplicações móveis (Android/iOS) consumindo microserviços desacoplados.  
- Backend distribuído em containers (Docker/ECS).  
- Pipelines CI/CD para build, teste e deploy.  
- Tecnologias relevantes: Java, Spring Boot, Flutter/Kotlin, GitHub Actions, JUnit, Mockito, Postman, AWS CloudWatch.

### 2.3 Trabalhos e Evidências Prévias  
- Literatura sugere que testes automatizados podem melhorar estabilidade e reduzir retrabalho.  
- Pesquisas sobre microserviços indicam benefícios de testes de contrato, mas carecem de foco em **tempo de entrega** e **cenários móveis distribuídos**.  
- Internamente, equipes relatam variação significativa nos tempos de entrega dependendo do nível de testes aplicados.

### 2.4 Referencial Teórico e Empírico Essencial  
- Engenharia de Software Experimental (Wohlin).  
- Arquitetura de microserviços (Newman, Lewis & Fowler).  
- Práticas de CI/CD (Humble & Farley).  
- Fundamentos de testes unitários, integração e contrato.  
- Métricas de produtividade e qualidade em desenvolvimento ágil.

---

## 3. Objetivos e Questões (GQM)

### 3.1 Objetivo Geral  
**Analisar**, com o propósito de **avaliar o impacto de testes automatizados**, sob a perspectiva de **equipes de desenvolvimento**, no contexto de **sistemas móveis baseados em microserviços distribuídos**, para **entender se essa prática reduz o tempo de entrega e aumenta a qualidade percebida**.

### 3.2 Objetivos Específicos  
- **O1:** Medir o impacto da adoção de testes automatizados no tempo total de entrega.  
- **O2:** Avaliar a variação no número de defeitos pós-deploy após adoção dos testes.  
- **O3:** Identificar a percepção dos desenvolvedores sobre confiança e qualidade.  
- **O4:** Comparar pipelines CI/CD antes e depois da inclusão de testes.

### 3.3 Questões de Pesquisa  
- **Q1:** Testes automatizados reduzem o tempo total de entrega de funcionalidades?  
- **Q2:** A prática reduz erros detectados em produção?  
- **Q3:** Desenvolvedores percebem maior confiança no código?  
- **Q4:** Pipelines com testes automatizados apresentam maior estabilidade?

### 3.4 Métricas Associadas (GQM)

| Questão | Métrica | Definição | Unidade | Fonte |
|---------|---------|-----------|----------|--------|
| Q1 | Lead Time | Tempo total entre início e deploy | horas/dias | CI/CD |
| Q2 | Defeitos pós-deploy | Incidentes ligados à funcionalidade | quantidade | Logs / incident tracker |
| Q3 | Confiança percebida | Avaliação via escala Likert | escala 1–5 | Survey |
| Q4 | Falhas de pipeline | Execuções que falham antes do deploy | quantidade | Logs CI/CD |

