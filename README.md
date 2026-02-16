"# Docker" 
<h1>Docker Zero to Hero 🚀</h1>

<p>
A repository to learn <strong>Docker</strong> with practical examples.
Contributions are most welcome!
</p>

<p>
⭐ If you found this repo useful, give it a STAR!
</p>

<p>
🎥 Watch the video version on YouTube:
<a href="https://www.youtube.com/watch?v=7JZP345yVjw&list=PLdpzxOOAlwvLjb0vTD9BXLOwwLD_GWCmC" target="_blank">
Docker Zero to Hero Playlist
</a>
</p>

<hr>

<h2>What is a Container?</h2>

<p>
A container is a standard unit of software that packages application code along with
its dependencies so the application runs reliably across environments.
</p>

<p>
A Docker container image is a lightweight, standalone, executable package that includes:
</p>

<ul>
  <li>Application code</li>
  <li>Runtime</li>
  <li>System tools</li>
  <li>System libraries</li>
  <li>Configuration</li>
</ul>

<p>
In simple words:
</p>

<blockquote>
A container is a bundle of the application, required libraries, and minimum system dependencies.
</blockquote>

<hr>

<h2>Containers vs Virtual Machines</h2>

<table border="1" cellpadding="8">
<tr>
<th>Feature</th>
<th>Containers</th>
<th>Virtual Machines</th>
</tr>
<tr>
<td>Resource Usage</td>
<td>Lightweight (share host OS kernel)</td>
<td>Heavy (full OS + hypervisor)</td>
</tr>
<tr>
<td>Portability</td>
<td>Highly portable</td>
<td>Requires compatible hypervisor</td>
</tr>
<tr>
<td>Security</td>
<td>Process-level isolation</td>
<td>Full OS-level isolation</td>
</tr>
<tr>
<td>Management</td>
<td>Easier & faster</td>
<td>More complex</td>
</tr>
</table>

<hr>

<h2>Why Are Containers Lightweight?</h2>

<p>
Containers share the host OS kernel and only include necessary application components.
They do not bundle an entire operating system like VMs.
</p>

<p>
Example:
</p>

<ul>
  <li>Ubuntu Base Container Image ≈ 22 MB</li>
  <li>Ubuntu VM Image ≈ 2.3 GB</li>
</ul>

<p>
Containers are smaller because they only include what is required to run the application.
</p>

<hr>

<h2>Docker</h2>

<h3>What is Docker?</h3>

<p>
Docker is a containerization platform used to:
</p>

<ul>
  <li>Build container images</li>
  <li>Run containers</li>
  <li>Push images to registries (Docker Hub, Quay.io, etc.)</li>
</ul>

<p>
Containerization is the concept. Docker implements containerization.
</p>

<hr>

<h3>Docker Architecture</h3>

<p>
Docker Daemon (dockerd) is the brain of Docker.
If the daemon stops, Docker stops functioning.
</p>

<hr>

<h3>Docker Lifecycle</h3>

<ul>
  <li><code>docker build</code> → Build image from Dockerfile</li>
  <li><code>docker run</code> → Run container from image</li>
  <li><code>docker push</code> → Push image to registry</li>
</ul>

<hr>

<h2>Docker Terminology</h2>

<h3>Docker Daemon</h3>
<p>Manages Docker objects such as images, containers, networks, and volumes.</p>

<h3>Docker Client</h3>
<p>CLI tool used to communicate with Docker daemon.</p>

<h3>Docker Desktop</h3>
<p>
Application for Mac, Windows, and Linux including:
Docker Engine, Docker Compose, Kubernetes, and more.
</p>

<h3>Docker Registry</h3>
<p>
Stores Docker images. Example: Docker Hub.
</p>

<h3>Dockerfile</h3>
<p>
Text file containing instructions to build a Docker image.
</p>

<h3>Images</h3>
<p>
Read-only template used to create containers.
</p>

<hr>

<h2>Install Docker</h2>

<p>Official installation guide:</p>
<p>
<a href="https://docs.docker.com/get-docker/" target="_blank">
https://docs.docker.com/get-docker/
</a>
</p>

<h3>Install Docker on Ubuntu (EC2 Example)</h3>

<pre><code>sudo apt update
sudo apt install docker.io -y
</code></pre>

<hr>

<h3>Start Docker Daemon</h3>

<pre><code>sudo systemctl status docker
sudo systemctl start docker
</code></pre>

<hr>

<h3>Grant User Access</h3>

<pre><code>sudo usermod -aG docker ubuntu
</code></pre>

<p>
Logout and login again for changes to apply.
</p>

<hr>

<h3>Verify Docker Installation</h3>

<pre><code>docker run hello-world
</code></pre>

Expected Output:

<pre><code>Hello from Docker!
This message shows that your installation appears to be working correctly.
</code></pre>

<hr>

<h2>Clone the Repository</h2>

<pre><code>git clone https://github.com/iam-veeramalla/Docker-Zero-to-Hero
cd examples
</code></pre>

<hr>

<h2>Login to Docker Hub</h2>

<p>
Create account: <a href="https://hub.docker.com/" target="_blank">Docker Hub</a>
</p>

<pre><code>docker login
</code></pre>

<hr>

<h2>Build Your First Docker Image</h2>

<pre><code>docker build -t &lt;your-dockerhub-username&gt;/my-first-docker-image:latest .
</code></pre>

Verify:

<pre><code>docker images
</code></pre>

<hr>

<h2>Run Your First Container</h2>

<pre><code>docker run -it &lt;your-dockerhub-username&gt;/my-first-docker-image
</code></pre>

Expected Output:

<pre><code>Hello World</code></pre>

<hr>

<h2>Push Image to Docker Hub</h2>

<pre><code>docker push &lt;your-dockerhub-username&gt;/my-first-docker-image
</code></pre>

<hr>

<h2>Congratulations 🎉</h2>

<p>
You have:
</p>

<ul>
  <li>Installed Docker</li>
  <li>Built an image</li>
  <li>Ran a container</li>
  <li>Pushed image to Docker Hub</li>
</ul>

<p>
You're officially a Docker champ now 🏆
</p>

<p>
Happy Learning! 🚀
</p>
