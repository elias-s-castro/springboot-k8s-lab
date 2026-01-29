# Spring Boot + Docker + Kubernetes Lab

Projeto de estudo

O foco é **entendimento real dos conceitos**, não apenas execução mecânica de comandos.

## 🎯 Objetivo do Projeto

- Criar uma aplicação Spring Boot simples
- Containerizar a aplicação com Docker
- Preparar o ambiente para execução em Kubernetes
- Entender o papel de cada tecnologia no ciclo de vida da aplicação


---

## 🛠️ Tecnologias Utilizadas

- Java 11
- Spring Boot 2.7.x
- Maven
- Docker
- Kubernetes (etapas futuras)

---

## 📦 Estrutura do Projeto

```
springboot-k8s-lab/
├─ src/
│  └─ main
│     ├─ java/br/com/legalmanager/lab
│     │  ├─ Application.java
│     │  └─ controller
│     │     └─ HealthController.java
│     └─ resources
│        └─ application.yml
│
├─ docker/
│  └─ Dockerfile
│
├─ pom.xml
└─ README.md
```

---

## 🚀 Executando a Aplicação Localmente

### Pré-requisitos
- Java 11+
- Maven

### Comando

```bash
mvn spring-boot:run
```

### Endpoints disponíveis

- Health check  
  `GET http://localhost:8080/health`

- Hello  
  `GET http://localhost:8080/hello`

---


## 🐳 Executando com Docker

### Pré-requisitos
- Docker instalado e funcionando

### 1️⃣ Gerar o JAR

```bash
mvn clean package
```

### 2️⃣ Build da imagem Docker

```bash
docker build -t springboot-k8s-lab:1.0 -f docker/Dockerfile .
```

### 3️⃣ Executar o container

```bash
docker run -p 8080:8080 springboot-k8s-lab:1.0
```

### Testes

- http://localhost:8080/health
- http://localhost:8080/hello

---

## 🧠 Conceitos Abordados Até o Momento

- Aplicação Spring Boot independente de infraestrutura
- Empacotamento da aplicação como JAR
- Criação de imagem Docker
- Execução de aplicação Java dentro de container
- Exposição de portas e mapeamento host → container
- Otimização do Dockerfile (multi-stage build)

---

## 🔜 Próximos Passos

- Redução do tamanho da imagem
- Introdução ao Kubernetes
    - Deployment
    - Service
    - Health checks (liveness/readiness)
- Configurações externas com ConfigMap

---

## 📌 Observação

Este projeto é voltado para **estudo e aprendizado**.  
As decisões arquiteturais priorizam **clareza, boas práticas e entendimento**, não atalhos.