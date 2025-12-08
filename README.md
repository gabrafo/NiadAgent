# 🧠 Sistema Distribuído para Análise Inteligente de Áudios de Reuniões

Este repositório contém o sistema desenvolvido para o núcleo de estudos **NIAD (Núcleo de Inteligência Artificial e Ciência de Dados)** como projeto acadêmico da disciplina **Sistemas Distribuídos** da **UFLA**.

O objetivo do sistema é realizar a **análise inteligente de áudios de reuniões recebidos via Telegram**, utilizando **múltiplos agentes de Inteligência Artificial** orquestrados em **microserviços containerizados**.

---

## 🧑‍💻 Desenvolvedores:

- [Gabriel Fagundes](https://github.com/gabrafo)
- [Gilmar Filho](https://github.com/gilmar-filho)
- [João Marcus](https://github.com/JoaoMarcus12)
- [Samuel Vanoni](https://github.com/SamuVanoni)

## 🚀 Principais Funcionalidades

### 🤖 Integração via Telegram

O **bot** atua como interface principal do sistema, recebendo áudios de reuniões dos usuários e enviando os resultados processados.

### 🎙️ Transcrição de Áudio (Whisper)

Microserviço **local e containerizado**, responsável por converter áudios em texto com o modelo open source **Whisper**, garantindo **privacidade e eficiência** no processamento inicial.

### 🧩 Orquestração (LangChain + API do Gemini)

Microserviço de orquestração. Utiliza o **LangChain** para gerenciar o fluxo, vetorizar textos e construir prompts, e se conecta à **API do Gemini** (um LLM remoto) para realizar a **sumarização inteligente** e geração de respostas.

### 🌐 API Gateway (Express.js)

Coordena o fluxo de dados entre os microserviços, centralizando o controle das requisições e assegurando **escalabilidade, segurança e flexibilidade**.

### 📄 DOCX Service (Python)

Extrai resumo criado pelo orquestrador e constrói um documento em PDF ou DOCX a partir dele, baseando-se em um template pré-estabelecido.

### 🐳 Containerização com Docker

Todos os componentes são **distribuídos em containers Docker**, facilitando **implantação, testes, manutenção e portabilidade** entre diferentes ambientes.

---

## Arquitetura do Projeto

![Arquitetura do projeto](./docs/assets/Arquitetura.jpg)

---

## 🧱 Justificativa da Arquitetura Utilizada

A arquitetura foi projetada para atender aos requisitos de um **sistema distribuído moderno, seguro e escalável**, utilizando múltiplos agentes de IA de forma **orquestrada e independente**.

O uso de um **API Gateway** como controlador central permite o **desacoplamento lógico** entre os módulos, simplificando manutenção, escalabilidade e atualizações dos microserviços.

A separação dos agentes de IA em **serviços distintos** — um **agente local (Whisper)** para transcrição de áudio e um **orquestrador (LangChain)** que consome uma **IA remota (API do Gemini)** para sumarização — cumpre os requisitos acadêmicos de um sistema híbrido (local/remoto) e oferece **flexibilidade para evolução tecnológica**.

O **Bot do Telegram** foi escolhido por sua acessibilidade e ampla adoção, tornando a interação com o sistema intuitiva. O uso de **containers Docker** garante **isolamento, reprodutibilidade e portabilidade**, permitindo fácil implantação em diversos ambientes.

Além disso, a maior parte das tecnologias adotadas (**Docker, LangChain, Whisper, Express.js**) é **gratuita, open source e bem documentada**. O uso de uma API externa (Gemini) expõe o sistema a um modelo de ponta, mantendo a complexidade de infraestrutura baixa e focando no desafio de orquestração.

Por fim, o **desenho modular** favorece a aplicação de **conceitos de segurança** (como a modelagem de ameaças e a gestão de segredos), **validação de problema e documentação arquitetônica**, além de servir como **base sólida para futuras melhorias**, expansão de funcionalidades e integração de novos agentes de IA.

---

# 🧠 Distributed System for Intelligent Meeting Audio Analysis

This repository contains the system developed for the **NIAD Study Group (Núcleo de Inteligência Artificial e Ciência de Dados)** as an academic project for the **Distributed Systems course** at **UFLA**.

The goal of the system is to perform **intelligent analysis of meeting audio files received via Telegram**, using **multiple AI agents** orchestrated in **containerized microservices**.

> **Note:** The rest of the documentation is in **Brazilian Portuguese (pt-BR)**.

---

## 🧑‍💻 Developers

* [Gabriel Fagundes](https://github.com/gabrafo)
* [Gilmar Filho](https://github.com/gilmar-filho)
* [João Marcus](https://github.com/JoaoMarcus12)
* [Samuel Vanoni](https://github.com/SamuVanoni)

---

## 🚀 Key Features

### 🤖 Telegram Integration

The **bot** serves as the main interface, receiving meeting audio from users and sending back processed results.

### 🎙️ Audio Transcription (Whisper)

Containerized **local microservice** responsible for converting audio to text using the open-source **Whisper** model, ensuring **privacy and efficiency** in the initial processing stage.

### 🧩 Orchestration (LangChain + Gemini API)

Orchestration microservice that uses **LangChain** to manage workflow, vectorize text, and construct prompts. It connects to the **Gemini API** (remote LLM) to perform **intelligent summarization** and generate responses.

### 🌐 API Gateway (Express.js)

Coordinates data flow between microservices, centralizing request control and ensuring **scalability, security, and flexibility**.

### 📄 DOCX Service (Python)

Generates **PDF or DOCX documents** from summaries produced by the orchestrator, based on predefined templates.

### 🐳 Containerization with Docker

All components are **distributed in Docker containers**, facilitating **deployment, testing, maintenance, and portability** across different environments.

---

## 🧱 Architecture Justification

The architecture was designed to meet the requirements of a **modern, secure, and scalable distributed system**, using multiple AI agents in an **orchestrated and independent** manner.

The use of an **API Gateway** as the central controller allows **logical decoupling** between modules, simplifying maintenance, scalability, and updates.

The separation of AI agents into **distinct services** — a **local agent (Whisper)** for audio transcription and an **orchestrator (LangChain)** consuming a **remote AI (Gemini API)** for summarization — meets academic requirements for a hybrid system (local/remote) while providing **flexibility for future upgrades**.

The **Telegram bot** was chosen for accessibility and wide adoption, making interaction with the system intuitive. **Docker containers** guarantee **isolation, reproducibility, and portability**, enabling easy deployment in different environments.

Most of the technologies used (**Docker, LangChain, Whisper, Express.js**) are **free, open source, and well-documented**. The external Gemini API exposes the system to a **state-of-the-art AI model** while keeping infrastructure complexity low and focusing on the orchestration challenge.
