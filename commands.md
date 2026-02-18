<h2>Docker Commands 🐳</h2>

<p>
Below are some of the most commonly used Docker commands.
</p>

<hr>

<h3>Image Management</h3>

<h4>docker images</h4>
<p>Lists Docker images available on the host machine.</p>

<pre><code>docker images
</code></pre>

<h4>docker build</h4>
<p>Builds a Docker image from a Dockerfile.</p>

<pre><code>docker build -t image-name .
</code></pre>

<h4>docker pull</h4>
<p>Downloads an image from the configured registry (e.g., Docker Hub).</p>

<pre><code>docker pull nginx
</code></pre>

<h4>docker push</h4>
<p>Uploads an image to the configured registry.</p>

<pre><code>docker push username/image-name
</code></pre>

<h4>docker rmi</h4>
<p>Removes an image from the host machine.</p>

<pre><code>docker rmi image-id
</code></pre>

<hr>

<h3>Container Management</h3>

<h4>docker run</h4>
<p>Runs a Docker container from an image.</p>

<pre><code>docker run image-name
</code></pre>

<p><strong>Commonly Used Options:</strong></p>

<ul>
  <li><code>-d</code> → Run container in background (detached mode)</li>
  <li><code>-p</code> → Port mapping (host:container)</li>
  <li><code>-it</code> → Interactive mode with terminal</li>
  <li><code>--name</code> → Assign a name to container</li>
</ul>

<p><strong>Examples:</strong></p>

<pre><code>docker run -d nginx
docker run -p 8080:80 nginx
docker run -it ubuntu /bin/bash
</code></pre>

<p>
Use the following command to see all available options:
</p>

<pre><code>docker run --help
</code></pre>

<hr>

<h4>docker ps</h4>
<p>Lists running containers on the host machine.</p>

<pre><code>docker ps
</code></pre>

<p>To list all containers (including stopped):</p>

<pre><code>docker ps -a
</code></pre>

<h4>docker stop</h4>
<p>Stops a running container.</p>

<pre><code>docker stop container-id
</code></pre>

<h4>docker start</h4>
<p>Starts a stopped container.</p>

<pre><code>docker start container-id
</code></pre>

<h4>docker rm</h4>
<p>Removes a stopped container.</p>

<pre><code>docker rm container-id
</code></pre>

<h4>docker exec</h4>
<p>Runs a command inside a running container.</p>

<pre><code>docker exec -it container-id /bin/bash
</code></pre>

<hr>

<h3>Network Management</h3>

<h4>docker network</h4>
<p>
Manages Docker networks such as creating, listing, removing networks,
and connecting containers to networks.
</p>

<p><strong>Common Examples:</strong></p>

<pre><code>docker network ls
docker network create my-network
docker network rm my-network
docker network connect my-network container-id
</code></pre>

<hr>

<h2>Summary</h2>

<p>
These commands form the foundation of working with Docker.
Mastering them will help you efficiently build, run, and manage
containers in any environment.
</p>
