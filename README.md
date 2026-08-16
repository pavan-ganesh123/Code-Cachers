<div align="center">

# 🚀 CodeCache

### A Social Coding Platform for Developers

**Build · Solve · Share · Connect**

<br/>

[![Java](https://img.shields.io/badge/Java-21-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)](https://www.oracle.com/java/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.x-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)](https://spring.io/projects/spring-boot)
[![React](https://img.shields.io/badge/React-18-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://react.dev/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-17-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![Docker](https://img.shields.io/badge/Docker-Containerized-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com/)

<br/>

[**Backend**](https://github.com/pavan-ganesh123/CodeCache)
&nbsp;&nbsp;•&nbsp;&nbsp;
[**Frontend**](https://github.com/pavan-ganesh123/CodingFront)
&nbsp;&nbsp;•&nbsp;&nbsp;
[**Go Service**](https://github.com/pavan-ganesh123/ChatLoop)

</div>

---

## 📌 Overview

**CodeCache** is a full-stack social coding platform built around programming practice and developer interaction.

Users can discover coding problems, track their progress, share problems and solutions, connect with other developers, chat with friends, and receive notifications.

The project evolved from a simple backend application into a **multi-service product-oriented system**, combining Java Spring Boot, Go, Python, React, PostgreSQL, Redis, Kafka, and external services.

---

## ✨ What Can You Do With CodeCache?

| Area | Features |
|---|---|
| 🔐 **Authentication** | Login, authentication, authorization, protected resources |
| 🧩 **Problems** | Coding problems, platforms, difficulty, intuition & complexity |
| 🏷️ **Topics** | Organize problems using topics |
| 📝 **Posts** | Share coding problems and solutions |
| ❤️ **Interactions** | Likes, comments and post sharing |
| 👥 **Social** | Friend requests, relationships, blocking |
| 📰 **Feed** | Personalized feed with visibility rules and pagination |
| 💬 **Chat** | Friend-to-friend conversations and persistent messages |
| 🔔 **Notifications** | Event-driven notifications using Kafka |
| 🖼️ **Media** | Profile and post image uploads |
| 🤖 **AI** | Gemini-powered problem information |
| 📊 **Profile** | Coding activity, streaks and statistics |

---

# 🏗️ System Architecture

CodeCache follows a multi-service architecture where the React frontend communicates primarily with the Spring Boot backend.

The backend interacts with PostgreSQL for persistent data, Redis for fast-access data, Kafka for asynchronous event communication, and additional Go/Python services for specialized functionality.

![System Architecture](docs/architecture.png)

---

# 🔐 Authentication Flow

Authentication is handled by the Spring Boot backend using token-based authentication.

The flow covers:

**Login → Authentication → Token Generation → Request Authentication → Protected Resources**

![Authentication Flow](docs/authentication-flow.png)

---

# 📨 Event-Driven Notifications

CodeCache uses **Apache Kafka** for asynchronous event communication.

Instead of performing notification processing directly inside the original request, application events can be published to Kafka and processed asynchronously.

**Application Event → Kafka Producer → Kafka Topic → Consumer → Notification Processing**

![Kafka Notification Flow](docs/kafka-flow.png)

> The Kafka infrastructure used during development was hosted through Aiven.

---

# 📰 Feed

The feed combines posts with user relationships and post visibility rules.

Posts support three visibility levels:

```text
PUBLIC
FRIENDS
PRIVATE