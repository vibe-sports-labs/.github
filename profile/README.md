# ⚡ Vibe Sports Lab

Bem-vindo ao braço de engenharia e tecnologia do **Vibe Sports Lab**. Somos uma startup focada em transformar a experiência esportiva local através de soluções de software inteligentes, unindo geolocalização em tempo real, alta performance e escalabilidade.

Nossa missão é conectar atletas, organizar partidas e otimizar a gestão de complexos esportivos de ponta a ponta.

---

### 🛠️ Nosso Stack Tecnológico & Arquitetura

Buscamos excelência técnica adotando uma arquitetura moderna, tipada e estritamente desacoplada:

* **Backend (Core & API Gateway):** Desenvolvido em **Spring Boot (Kotlin)** seguindo o padrão de Monolito Modular. Utilizamos **MongoDB** com indexação geoespacial nativa (`2dsphere`) para queries de alta performance por raio de distância, além de garantirmos a resiliência e entrega estável de eventos via **Transactional Outbox Pattern**.
* **Frontend & Mobile:** Construído em **Kotlin Multiplatform (KMP)** + Compose Multiplatform. Essa abordagem nos permite compartilhar 100% das regras de negócio, segurança e lógica de rede entre as plataformas Android e iOS, mantendo a experiência de UI nativa e eliminando gargalos de compilação.
* **Segurança & Real-Time:** Autenticação federada integrada via Firebase Auth (tokens portadores no Spring Security) e arquitetura de comunicação bidirecional em tempo real utilizando **Ktor WebSockets** para chats de arena.

---

### 🎯 Foco do Nosso MVP
Atualmente, nosso time está focado na entrega da versão **MVP v1.0**, que engloba:
* Hub de mapas interativos para listagem e criação de partidas baseadas na localização do atleta.
* Sistema transacional de matchmaking para inscrição em jogos em tempo real.
* Comunicação instantânea em salas de chat segmentadas por arena/estádio.
