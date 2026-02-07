# pythonpro-rag-api
# 🚀 End-to-End RAG Pipeline: API, Docker, Kubernetes & CI/CD

This repository contains a complete, production-ready MLOps pipeline for a Retrieval-Augmented Generation (RAG) API. The project evolves from a simple local Python script to a containerized, orchestrated, and automated application.

## 🏗️ Project Architecture

### Phase 1: Building the RAG API
We built a FastAPI application that interfaces with a vector database (**ChromaDB**) and a local LLM (**Ollama**). The system retrieves relevant context from documents to answer user queries accurately.

![RAG API Architecture](image_1acc8c.png)

* **Tech:** FastAPI, ChromaDB, Ollama
* **Feature:** Interactive Swagger UI documentation.

### Phase 2: Containerization with Docker
To ensure portability, the application was containerized. This standardizes the environment, ensuring the API runs identically on a laptop, a colleague's machine, or a cloud server.

![Docker Workflow](image_1acd40.png)

* **Tech:** Docker, Dockerfile
* **Result:** A portable, lightweight image ready for deployment.

### Phase 3: Orchestration with Kubernetes
We moved from running a single container to orchestrating the application using **Kubernetes (Minikube)**. This setup includes Deployments for state management and Services for stable networking.

![Kubernetes Architecture](image_1b1f61.png)

* **Tech:** Minikube, kubectl, Kubernetes Services & Deployments
* **Result:** A self-healing, scalable architecture.

### Phase 4: CI/CD & Semantic Testing
Reliability is key. We implemented a **GitHub Actions** workflow that triggers on every push. It rebuilds the embeddings and runs "Semantic Tests"—using an LLM to grade the accuracy of the API's responses.

![CI/CD Pipeline](image_1b1ffa.jpg)

* **Tech:** GitHub Actions, Python Unit Tests
* **Result:** Automated quality gates that block bad deployments.

## 🛠️ How to Run

1.  **Clone the repo:**
    ```bash
    git clone [https://github.com/yourusername/your-repo-name.git](https://github.com/yourusername/your-repo-name.git)
    ```

2.  **Run with Docker:**
    ```bash
    docker build -t rag-api .
    docker run -p 8000:8000 rag-api
    ```

3.  **Deploy to K8s:**
    ```bash
    kubectl apply -f k8s/deployment.yaml
    kubectl apply -f k8s/service.yaml
    ```
