This machine explores vulnerabilities of SMB Port 445


<img width="531" height="228" alt="image" src="https://github.com/user-attachments/assets/d9d19dec-1042-43d3-aab9-3f051168a32c" /></br>

Date: January 26,2026 | Difficulty: Very Easy
Platfrom: Hack The Box

<h2>Executive Summary</h2></br>
<p>In this engagement, I performed a security assessment on a Windows-based target. The primary goal was to identify open services and potential misconfigurations. I discovered an unauthenticated SMB share (Null Session) which allowed me to browse the file system and retrieve sensitive information (the flag).</p>


<pre>
<h2>Tools Used</h2>
-------------------------------------------------------------------
Tool           |   Purpose 
-------------------------------------------------------------------
Nmap           |   Network scanning and service detection
-------------------------------------------------------------------
smbclient      |   Interacting with SMB(Server Message Block) shares
-------------------------------------------------------------------
Linux Terminal |   Command-line execution and file management
-------------------------------------------------------------------

</pre>

<h2>Phase 1: Enumeration</h2>
Network Scanning

I initated the reconnaisance with an aggresive Nmap scan to map the atteck surface.</br>
<code> Nmap -sV -sC 10.129.31.45</code>
<h3>Key findings:</h3>
<pre>
Port  |  Service    | Version              | Status 
----------------------------------------------------------
135   | msrpc       |Microsoft Windows RPC | Open
----------------------------------------------------------
139   |netbios-ssn  | Microsoft Windows netbios-ssn | Open
----------------------------------------------------------
<b>445|microsoft-ds | Windows 10 Enterprise | Open(Vulnerable)</b>
------------------------------------------------------------------
</pre>

<h2>Phase 2: Exploitation</h2>
<h3><b>SMB Enumeration & Access</b></h3>
<p>After identifying the SMB service on port 445, I checked for anonymous access (Null Session) using  <code>smbclient</code></p>
<code>smbclient -L 10.129.31.45 -N</code></br>
<b>Observation: </b> The command succesfully listed the shares. I noticed a non-default named <em><b>Workshares</b></em>.</br>

<h3>Data Exfiltration</h3>
I connected to the <b>WorkShares</b> directory and explored the subdirectories.</br>
<pre>
  
<code>smbclient \\\\\\\10.129.31.45\\\WorkShares
      cd James.P
      get flag.txt
</code>
<h4> Flag Captured </h4>
</pre>


<h2>Phase 3: Remediation (The Consultant's View)</h2>
<p>To mitigate the risk of unathorized data access, I recommend the following securit controls: </p>
<ol>
  <li> <b>Diasble anonymous/Guset Access:</b>
    <pre>Configure the SMB service to require valid
    credentials foa all share listings and
    connections</pre></li>
  <li><b>Restrict Share Permissions:</b>
  <pre>Principle of Least Privilege.Only
  authorized users should have acces to the 
  WorkShares directory</pre></li>
  <li><b>SMB Signing: </b>
  <pre>Enable SMB signing to prevent Man-In-The-Middle attacks</pre></li>
</ol>

<h2>Final Reflection</h2>
<ul>
  <li><b>What I learned:</b> I practiced identifying SMB misconfigurations and learned how Null Sessions</br>
can be used to exfiltrate data without password.</li>
  <li> <b>Challenges: </b> Understanding the difference between Windows shares and custom user shares.</li>
</ul>
