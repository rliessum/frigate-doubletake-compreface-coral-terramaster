# **Installation Guide**  

## **Overview**  
This guide will walk you through setting up Frigate, Double Take, CompreFace, and a Coral TPU on a **Terramaster NAS** using **Docker Compose** or **Portainer**.  

---

## **Prerequisites**  
Before proceeding, ensure you have:  
- Docker and Docker Compose installed on your Terramaster NAS.  
- Portainer installed (if using it for deployment).  
- A Coral TPU properly connected to the NAS.  

---

## **Installation Steps**  

### **1. Clone the Repository**  
First, download the project files to your local machine:  

```shell
git clone https://github.com/rliessum/frigate-doubletake-compreface-coral-terramaster.git
```

Navigate to the project directory:  

```shell
cd frigate-doubletake-compreface-coral-terramaster
```

---

### **2. Configure Environment Variables**  
Copy the example environment file and update it with your configuration:  

```shell
cp .env.example .env
```

Open the `.env` file and modify the necessary variables based on your setup.  

---

### **3. Deploy the Stack**  

#### **Option 1: Using Docker Compose**  
Run the following command to build and start the containers in the background:  

```shell
docker-compose up -d
```

#### **Option 2: Using Portainer**  
1. Open the **Portainer dashboard** in your browser.  
2. Create a **new stack**.  
3. Copy and paste the contents of `docker-compose.yml` into the stack definition.  
4. Adjust the **environment variables** as needed.  
5. Click **Deploy the stack**.  

---

### **4. Monitor the Startup Process**  
Check the logs to verify that everything is running correctly:  

```shell
docker-compose logs -f
```

---

### **5. Access the Application**  
Once the containers are up and running, access the application using the specified port or URL in your `.env` file.  

---

## **Troubleshooting**  
- If you encounter permission errors, ensure your user has the correct privileges to run Docker commands.  
- For Coral TPU issues, check that the device is properly recognized using:  

  ```shell
  lsusb
  ```

- If a service fails to start, inspect its logs:  

  ```shell
  docker logs <container_name>
  ```

---

