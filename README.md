
# Prodevans Demo Project

## How to Build and Run

1. **Build the Docker Image:**

   First, build the Docker image from the custom Dockerfile:

   ```bash
   docker build -f ubuntu_apache -t myapache .
   ```

   - This will build the Docker image and tag it as `myapache`.

2. **Run the Container:**

   Run the container, mapping the local `html/` directory to `/var/www/html` inside the container:

   ```bash
   docker run -d -p 81:80 --name myapache -v ./html:/var/www/html ubuntu_apache
   ```

   - `-d` — Run the container in detached mode (background).
   - `-p 81:80` — Maps port 81 on your host to port 80 in the container.
   - `--name myapache` — Names the container `myapache`.
   - `-v ./html:/var/www/html` — Mounts the local `html/` folder to the container's `/var/www/html` directory.

3. **Access the Web Page:**

   Open your browser and go to:

   ```
   http://localhost:81
   ```

   You should see the contents of your `index.html` file, served by Apache.

---
