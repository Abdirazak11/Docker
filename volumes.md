<h2>Docker Volumes 📦</h2>

<h3>Problem Statement</h3>

<p>
It is a very common requirement to persist data in a Docker container
beyond the lifetime of the container.
</p>

<p>
However, the file system of a Docker container is deleted when the
container stops or is removed.
</p>

<hr>

<h3>Solution</h3>

<p>
Docker provides two main ways to persist data:
</p>

<ul>
  <li><strong>Volumes</strong></li>
  <li><strong>Bind Mounts (Bind Directory on Host)</strong></li>
</ul>

<hr>

<h2>1️⃣ Volumes</h2>

<p>
Volumes provide a way to store data on the host file system,
separate from the container’s internal file system.
This ensures data persists even if the container is deleted and recreated.
</p>

<h3>Create a Volume</h3>

<pre><code>docker volume create &lt;volume_name&gt;
</code></pre>

<h3>List Volumes</h3>

<pre><code>docker volume ls
</code></pre>

<h3>Mount Volume to a Container</h3>

<pre><code>docker run -it -v &lt;volume_name&gt;:/data &lt;image_name&gt; /bin/bash
</code></pre>

<p>
This mounts the volume <code>&lt;volume_name&gt;</code> to
<code>/data</code> inside the container.
</p>

<p>
Any data written to <code>/data</code> inside the container
will persist on the host system.
</p>

<h3>Inspect Volume</h3>

<pre><code>docker volume inspect &lt;volume_name&gt;
</code></pre>

<h3>Remove Volume</h3>

<pre><code>docker volume rm &lt;volume_name&gt;
</code></pre>

<hr>

<h2>2️⃣ Bind Mounts (Bind Directory on Host)</h2>

<p>
Bind mounts allow you to mount a specific directory from the host
machine into a container.
</p>

<p>
Unlike volumes, bind mounts directly reference a host path.
</p>

<h3>Mount Host Directory into Container</h3>

<pre><code>docker run -it -v &lt;host_path&gt;:&lt;container_path&gt; &lt;image_name&gt; /bin/bash
</code></pre>

<p>
Example:
</p>

<pre><code>docker run -it -v /home/ubuntu/data:/app/data ubuntu /bin/bash
</code></pre>

<p>
Here, the directory <code>/home/ubuntu/data</code> on the host
is mounted to <code>/app/data</code> inside the container.
</p>

<hr>

<h2>Key Differences: Volumes vs Bind Mounts</h2>

<table border="1" cellpadding="8">
<tr>
<th>Feature</th>
<th>Volumes</th>
<th>Bind Mounts</th>
</tr>
<tr>
<td>Managed by Docker</td>
<td>Yes</td>
<td>No</td>
</tr>
<tr>
<td>Location</td>
<td>Docker-managed directory</td>
<td>Specific host path</td>
</tr>
<tr>
<td>Portability</td>
<td>More portable</td>
<td>Host dependent</td>
</tr>
<tr>
<td>Backup & Migration</td>
<td>Easier</td>
<td>Manual</td>
</tr>
<tr>
<td>Best For</td>
<td>Production & complex setups</td>
<td>Development & simple use cases</td>
</tr>
</table>

<hr>

<h2>When to Use What?</h2>

<ul>
  <li>
    ✅ <strong>Use Volumes</strong> for production applications,
    databases, and persistent application data.
  </li>
  <li>
    ✅ <strong>Use Bind Mounts</strong> for development environments
    when you need to sync local code into a container.
  </li>
</ul>

<hr>

<h2>Conclusion</h2>

<p>
Docker volumes and bind mounts solve the same core problem:
<strong>data persistence</strong>.
</p>

<p>
Volumes are generally preferred in production environments,
while bind mounts are convenient for development workflows.
</p>
