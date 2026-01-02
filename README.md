<p align="center">
  <h1 align="center">Secure Netflix Clone on kubernetes</h1>
  <p align="center">
    For this project, I built a secure pipeline to deploy and manage a containerized Netflix clone web application in AWS. I implemented CI/CD automation with Jenkins and integrated security tooling including SonarQube, Trivy, and OWASP Dependency-Check so code quality issues, vulnerable dependencies, and insecure images are identified before deployment. Rather than deploying containers without visibility or safeguards, the application is monitored with Prometheus and Grafana and deployed on Kubernetes using Argo CD, supporting secure and observable application delivery.<br />
  </p>
</p>

## Features


- **Kubernetes (EKS)**
- **Jenkins**
- **Docker**
- **ArgoCD**
- **Helm**
- **SonarQube**
- **Trivy**
- **OWASP Dependency-Check**
- **Prometheus**
- **Grafana**


## Step 1.
I started by setting up a server in AWS that would support the application, automation tooling, and security controls. After connecting to the server, I pulled the project source code from GitHub to begin the deployment process.

<img width="1470" height="838" alt="Screenshot 2025-12-25 at 5 55 47 PM" src="https://github.com/user-attachments/assets/d7610da9-86af-43e7-ab8f-d1ca3c629c8b" />


## Step 2.
With the environment ready, I containerized the Netflix clone application using Docker and deployed it on the server. I then integrated an API key from TMDB into the build process, allowing the application to successfully fetch and display movie data on my Netflix application.

<img width="1470" height="837" alt="Screenshot 2025-12-25 at 9 05 40 PM" src="https://github.com/user-attachments/assets/9dc5434c-6e6c-4a1d-a4d2-bd68b28b1894" />


## Step 3.
Once the application was running, I then switched my focus on introducing security scanning into the workflow. I deployed SonarQube to analyze the source code for quality and security issues and installed Trivy to scan the filesystem and container images for vulnerabilities.

<img width="1470" height="797" alt="Screenshot 2025-12-25 at 10 28 30 PM" src="https://github.com/user-attachments/assets/b5853d7c-5caf-42ec-afe6-2a9568d417f8" />
<img width="1470" height="839" alt="Screenshot 2025-12-25 at 10 41 47 PM" src="https://github.com/user-attachments/assets/db7f4d9d-bfbc-4c61-80f9-0e3232639ebb" />


## Step 4.
Then, to automate the entire workflow, I deployed Jenkins and configured it to serve as the CI/CD platform. This included installing plugins and configuring integrations needed for code analysis, container builds, and deployments.



## Step 5.
With Jenkins configured, I created a pipeline to automate code retrieval, dependency installation, and static analysis. Also, quality gates were enforced to ensure only approved builds continued through the pipeline.

<img width="1470" height="837" alt="Screenshot 2025-12-26 at 12 34 48 AM" src="https://github.com/user-attachments/assets/f9bda444-69e7-459b-97c8-567733e4b5a7" />


## Step 6.
To further strengthen security, I extended the pipeline with OWASP Dependency-Check and Trivy scans. These steps ensured vulnerable dependencies and insecure files were identified before deployment.

## Step 7.
After all security and quality checks passed, the pipeline built and published the container image to my Docker Hub, ensuring only scanned and approved images were stored.

<img width="1470" height="837" alt="Screenshot 2025-12-26 at 2 44 22 PM" src="https://github.com/user-attachments/assets/59439a10-e985-4512-8ad6-9b317d2ace4e" />


## Step 8.
After the image was successfully pushed to my Docker Hub, I deployed the application using the container image produced by the pipeline and verified that the application started correctly and functioned as expected.

<img width="1470" height="837" alt="Screenshot 2025-12-26 at 2 56 35 PM" src="https://github.com/user-attachments/assets/e7257cc9-18bc-4580-b260-3cbfc8d8122e" />


## Step 9.
To improve observability, I installed Prometheus and Node Exporter to collect system and service metrics, providing visibility into resource usage and application performance.

<img width="1444" height="768" alt="Screenshot 2025-12-27 at 1 03 04 AM" src="https://github.com/user-attachments/assets/939ef58c-b6bc-470f-8acb-43cf1b801f74" />


## Step 10.
I deployed Grafana and connected it to Prometheus, creating dashboards to visualize system metrics and overall application performance for easier monitoring and troubleshooting.

<img width="1444" height="768" alt="Screenshot 2025-12-26 at 11 52 28 PM" src="https://github.com/user-attachments/assets/3eceba9d-16cb-4d48-99c0-7140f7cf7cd0" />


## Step 11.
To extend the deployment, I created a Kubernetes cluster in AWS and provisioned worker nodes, allowing the application to be managed through container orchestration rather than standalone containers.

## Step 12.
I then used Argo CD to deploy the application to Kubernetes, making it easier to manage application updates and maintain a consistent deployment state.

<img width="1416" height="616" alt="Screenshot 2025-12-27 at 4 10 12 AM" src="https://github.com/user-attachments/assets/8ee520e3-2631-45fd-b7cd-a9fe5f2ad5d5" />


## Step 13.
Finally, I re-established monitoring within the Kubernetes environment by deploying Prometheus and Grafana using Helm, ensuring consistent observability across all workloads.
