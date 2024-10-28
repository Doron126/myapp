# **myapp**
## **Overview**
This project sets up a CI/CD pipeline for a basic Flask app using Jenkins and Docker. The pipeline automatically pulls code from GitHub, builds a Docker image, runs tests, and deploys the app.
It's an example of automating deployment with containerization and continuous integration.

## **Thecnologies Used**
* Python
* Python libaries: Flask
* Docker
* Jenkins
* GitHub

## **Instructions**
1. Set up an Ubuntu server machine.
   
2. Set up Jenkins:
   "sudo apt update"
   "sudo apt install openjdk-17-jdk -y"
   "curl -fsSL https://pkg.jenkins.io/debian/jenkins.io-2023.key | sudo tee \
    /usr/share/keyrings/jenkins-keyring.asc > /dev/null"
   "echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
    https://pkg.jenkins.io/debian binary/ | sudo tee \
    /etc/apt/sources.list.d/jenkins.list > /dev/null"
   "sudo apt update"
   "sudo apt install jenkins -y"
   "sudo systemctl start jenkins"
   "sudo systemctl enable jenkins"

3. Set up Docker:
   "sudo apt update"
   "sudo apt install apt-transport-https ca-certificates curl software-properties-common -y"
   "curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
    echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null"
   "sudo apt update"
   "sudo apt install docker-ce -y"
   "sudo usermod -aG docker jenkins"
   "sudo systemctl restart jenkins"

4. Create a directory in the Ubuntu server and create there the files added to the project (app.py, requirements.txt, Dockerfile)

5. Create a GitHub repository and push your code, from the directory you created in Ubuntu. type:
   "git init"
   "git add ."
   git commit -m "Initial commit"
   "git remote add origin 'GitHub_repository_URL'"
   "git push -u origin main"

6. Install the Jenkins plugins and configure the pipeline:
   Connect to Jenkins on port 8080 and go to Manage Jenkins > Plugins.
   Install "Git" and "Docker Pipeline" plugins.
   Click on "+ New Item" and then "Pipeline".
   When configuring the pipeline check "GitHub project" and enter the project URL.
   Choose "Pipeline script from SCM" and then "Git" as the SCM with the repository URL, click Save.

7. Run the job with "Builed Now" and check the results.
   
