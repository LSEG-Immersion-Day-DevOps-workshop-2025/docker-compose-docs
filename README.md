## Workshop Task: Docker Compose

### Step-by-Step: Create Your Own `docker-compose.yml`

1. **Understand Your Services**
   - You have two main services: `backend` (Node.js) and `frontend` (React).
   - Each service has its own Dockerfile.

2. **Create a New File**
   - In your project folder, create a file named `docker-compose.yml`.

3. **Write the Compose File**
   - Open `docker-compose.yml` and define both services.
   - Example structure:
     ```yaml
     version: '3.8'

     services:
       backend:
         image: <your-dockerhub-username>/trip-planner-backend:latest
         ports:
           - "5000:5000"
         environment:
           NODE_ENV: production
           # Add other environment variables here

       frontend:
         image: <your-dockerhub-username>/trip-planner-frontend:latest
         ports:
           - "3000:80"
         environment:
           NODE_ENV: production
           # Add other environment variables here
         depends_on:
           - backend
     ```
   - Replace `<your-dockerhub-username>` with your Docker Hub username.
   - Add any required environment variables under `environment:` for each service.

4. **Save and Run**
   - Save the file.
   - In your terminal, run:
     ```sh
     docker compose up
     ```
   - This will start both services using the images you pushed to Docker Hub.

---

**Tip:**  
If you want to build images locally instead of using Docker Hub, use the `build:` option instead of `image:`.