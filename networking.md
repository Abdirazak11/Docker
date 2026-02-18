<h2>Docker Networking 🌐</h2>

<p>
Docker networking allows containers to communicate with each other
and with the host system.
Containers run in isolation, so networking enables controlled communication.
</p>

<p>
By default, Docker provides multiple network drivers such as:
</p>

<ul>
  <li><strong>bridge</strong></li>
  <li><strong>host</strong></li>
  <li><strong>overlay</strong></li>
  <li><strong>macvlan</strong></li>
  <li><strong>none</strong></li>
</ul>

<hr>

<h3>List Available Networks</h3>

<pre><code>docker network ls
</code></pre>

Example Output:

<pre><code>NETWORK ID          NAME        DRIVER
xxxxxxxxxxxx        none        null
xxxxxxxxxxxx        host        host
xxxxxxxxxxxx        bridge      bridge
</code></pre>

<hr>

<h2>Bridge Networking (Default)</h2>

<p>
Bridge is the default network mode in Docker.
It creates a private internal network between the host and containers.
Containers connected to the same bridge network can communicate with each other.
</p>

<h3>Create Custom Bridge Network</h3>

<p>
To isolate containers from the default bridge network,
you can create your own bridge network:
</p>

<pre><code>docker network create -d bridge my_bridge
</code></pre>

Now check networks again:

<pre><code>docker network ls
</code></pre>

Example Output:

<pre><code>NETWORK ID          NAME        DRIVER
xxxxxxxxxxxx        bridge      bridge
xxxxxxxxxxxx        my_bridge   bridge
xxxxxxxxxxxx        none        null
xxxxxxxxxxxx        host        host
</code></pre>

<h3>Run Container on Custom Network</h3>

<pre><code>docker run -d --net=my_bridge --name db training/postgres
</code></pre>

<p>
Containers attached to different bridge networks are isolated
and cannot communicate with each other.
</p>

<h3>Connect Existing Container to Network</h3>

<pre><code>docker network connect my_bridge web
</code></pre>

<p>
This allows the container <code>web</code> to communicate with containers
on the <code>my_bridge</code> network.
</p>

<hr>

<h2>Host Networking</h2>

<p>
Host networking allows a container to share the host system's
network stack directly.
</p>

<ul>
  <li>Container uses host’s IP address</li>
  <li>No network isolation</li>
  <li>No port mapping required</li>
</ul>

<h3>Run Container with Host Network</h3>

<pre><code>docker run --network="host" &lt;image_name&gt; &lt;command&gt;
</code></pre>

<p>
⚠ <strong>Warning:</strong> Host networking reduces isolation and
can introduce security risks. Use carefully.
</p>

<hr>

<h2>Overlay Networking</h2>

<p>
Overlay networking enables communication between containers
across multiple Docker hosts.
</p>

<ul>
  <li>Used in Docker Swarm</li>
  <li>Multi-host networking</li>
  <li>Containers appear on a single logical network</li>
</ul>

<hr>

<h2>Macvlan Networking</h2>

<p>
Macvlan networking allows a container to appear as a physical device
on the network.
</p>

<ul>
  <li>Container gets its own MAC address</li>
  <li>Appears like a separate machine on LAN</li>
  <li>Useful for legacy applications</li>
</ul>

<hr>

<h2>Network Modes Summary</h2>

<table border="1" cellpadding="8">
<tr>
<th>Network Driver</th>
<th>Use Case</th>
<th>Isolation Level</th>
</tr>
<tr>
<td>bridge</td>
<td>Single-host container communication</td>
<td>Medium</td>
</tr>
<tr>
<td>host</td>
<td>High-performance / direct host access</td>
<td>Low</td>
</tr>
<tr>
<td>overlay</td>
<td>Multi-host communication</td>
<td>High</td>
</tr>
<tr>
<td>macvlan</td>
<td>Container as physical network device</td>
<td>Medium</td>
</tr>
<tr>
<td>none</td>
<td>No networking</td>
<td>Full isolation</td>
</tr>
</table>

<hr>

<h2>Conclusion</h2>

<p>
Docker networking provides flexible options for:
</p>

<ul>
  <li>Container-to-container communication</li>
  <li>Container-to-host communication</li>
  <li>Multi-host networking</li>
  <li>Advanced production setups</li>
</ul>

<p>
Understanding networking is essential for building
secure and scalable containerized applications.
</p>
