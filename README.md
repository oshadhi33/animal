# 🐶 Pet Care Animal Clinic Website

This is a responsive website for a **Pet Clinic** built with **HTML, CSS, and JavaScript**. The website includes multiple pages, a navigation bar, images, and a user-friendly interface. It is designed to be mobile-responsive and can be deployed in a **Docker container**.

## 📌 Features
- 🏠 Home Page with Hero Section
- ℹ️ About Page
- 🏥 Services Page
- 📞 Contact Page
- 🌐 Fully Responsive Design
- 📸 Image Gallery
- ⚡ Fast and Lightweight
- 🛠️ CI/CD Pipeline with Jenkins

---

## 🚀 Live Preview

🔗 **(https://your-github-username.github.io/pet-clinic/)**

---

## 🛠️ How to Run Locally

1. **Clone the Repository**
   ```sh
   git clone https://github.com/your-github-username/pet-clinic.git
   cd pet-clinic
   
2. Open index.html in a Browser Simply double-click index.html or open it in VS Code with Live Server.

---

## 📦 Run with Docker

#### **1️⃣ Build Docker Image**
```
docker build -t pet-clinic .
```

#### **2️⃣ Run the Container**
```
docker run -d -p 8080:80 pet-clinic
```

#### **3️⃣ Open in Browser**

Visit: http://localhost:8080

---

## 📜 Run with Docker Compose (Optional)

1. Create and start the container
```
docker-compose up -d
```

2. Stop the container
```
docker-compose down
```
---

## 🔄 CI/CD Pipeline with Jenkins

This project includes an automated Jenkins pipeline for building, testing, and deploying the website using Docker.

**Jenkins Pipeline Stages**
1. Clone Repository - Fetches the latest code from GitHub.
2. Build Docker Image - Creates a new Docker image of the website.
3. Run Tests - Executes basic tests (optional).
4. Push to Docker Hub (if configured) - Pushes the image to Docker Hub.
5. Deploy the Container - Runs the container on the server.
   
**Jenkinsfile Example**


```
pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/your-github-username/pet-clinic.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t pet-clinic .'
            }
        }
        stage('Run Tests') {
            steps {
                sh 'echo "No tests yet. Add test commands here!"'
            }
        }
        stage('Push to Docker Hub') {
            steps {
                withDockerRegistry([credentialsId: 'docker-hub-credentials']) {
                    sh 'docker tag pet-clinic your-dockerhub-username/pet-clinic:latest'
                    sh 'docker push your-dockerhub-username/pet-clinic:latest'
                }
            }
        }
        stage('Deploy Container') {
            steps {
                sh 'docker run -d -p 8080:80 your-dockerhub-username/pet-clinic:latest'
            }
        }
    }
}
```

**Jenkins Setup**

- Install Docker on the Jenkins server.
- Configure Jenkins to allow Docker commands.
- Add Docker Hub credentials in Jenkins.
- Set up a Jenkins job with a GitHub Webhook for automatic deployment.

---

## 📂 Project Structure
```
/pet-clinic
│── index.html
│── about.html
│── services.html
│── contact.html
│── styles.css
│── script.js
│── Dockerfile
│── docker-compose.yml
│── Jenkinsfile
│── README.md
```

---

## 🤝 Contributing

Feel free to fork the repository and submit a pull request if you have improvements!

---

## ⚖️ License

This project is open-source and free to use.

---

### 🔥 **Next Steps**

- Replace **"your-github-username"** with your actual GitHub username.
- Replace **"your-dockerhub-username"** with your Docker Hub username (if pushing images).
- Make sure your **Jenkins pipeline** matches your actual configuration.

