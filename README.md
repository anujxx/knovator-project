***Dockerize Node.js & React App with Nginx Reverse Proxy
    Multi-stage Docker images (lightweight)
    Docker Compose for orchestration
    NGINX reverse proxy
    Run on Ubuntu 20.04
*****Install Docker & Docker Compose
    sudo apt update
    sudo apt install -y docker.io docker-compose
    sudo systemctl enable docker
*****Build & Run
    docker-compose up --build -d
*****Jenkins CI/CD to Deploy Dockerized App on VM
    sudo apt update
    sudo apt install -y openjdk-11-jdk
    wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
    sudo sh -c 'echo deb https://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
    sudo apt update
    sudo apt install -y jenkins
    sudo systemctl start jenkins
    
*****setup Docker Permissions for Jenkins
    sudo usermod -aG docker jenkins
    sudo systemctl restart jenkins
*****Add Jenkins Pipeline Job
    New Job
    New Item → Pipeline
    Use Git repo with Jenkinsfile in root

*****Plan for Laravel Distributed Architecture
  Distributed Docker Compose
  1.Security
      Use SSL (Let's Encrypt) for HTTPS
      
      Protect DB ports with firewall (ufw)
      
      Use Laravel Sanctum or Passport for auth
      
      Set strong .env values and do not expose
  2.Scalability
      Use Kubernetes for container orchestration
      
      Use external MySQL for HA setups
      
      Separate queue worker nodes for Horizon
      
      Use S3 or MinIO for file storage

  3.Cost-Effective
      Use Docker on a single VPS (DigitalOcean, Hetzner) for smaller apps
      
      Scale only necessary components (e.g., queue workers under load)

**final Steps
      Build the full code repo structure
      
      Push to Git
      
      Set up Jenkins job pointing to repo
      
      Test build/deploy via Docker Compose


