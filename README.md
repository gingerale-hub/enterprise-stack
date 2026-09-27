Enterprise Self-Hosted Object Storage Pipeline

A highly secure, containerized private cloud storage solution built using Infrastructure as Code principles. This architecture deploys an enterprise S3-obeject storage server using the secure and private Docker network 


Architecture Overview

Object Storage Layer: Utilizes MinIO to provide a fast, local, S3-compliant API and graphical management console for object management.
Volume Persistence: Implements isolated Docker named volumes (`minio_enterprise_data`) to abstract the storage backend and ensure resilient data persistence.
Secret Management: Implements strict DevSecOps boundaries by injecting configuration keys dynamically through environment variables, preventing credential exposure in source control.

Getting Started

## Getting Started

1. Clone this repository.
2. Duplicate the environment configuration template file (`env.example`) and rename it to `.env`:

   **Windows (PowerShell):**
   powershell:
   Copy-Item env.example .env
  

   **Windows (Command Prompt):**
   cmd
   copy env.example .env
   

   **Linux / macOS (Bash):**
   bash
   cp env.example .env
   

3. Open `.env` and fill in your secure root credentials.
4. Launch the stack in detached mode:
   **Linux/ macOS (bash)**
   bash
   docker compose up -d

   **Windows (Powershell or Command Prompt)**
    docker compose up -d
   
5. Access your local network endpoints:
   - **MinIO Web Console UI:** [http://console.localhost](http://console.localhost)
   - **MinIO S3 API Endpoint:** [http://s3.localhost](http://s3.localhost)
   - **Traefik Control Dashboard:** [http://localhost:8888](http://localhost:8888)
