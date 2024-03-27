<h1>SQL Injection Lab with BurpSuite/DVWA/Mutillidae</h1>

<h2>Description</h2>
The SQL Injection Lab, leveraging the capabilities of Burp Suite, DVWA (Damn Vulnerable Web Application), and Mutillidae, represents an educational toolkit for mastering the intricacies of web security, specifically focusing on SQL Injection—one of the most potent threats to web applications. Burp Suite, a comprehensive set of tools for web application security testing, acts as a critical intermediary, allowing users to intercept and manipulate communications between clients and servers, thereby identifying potential vulnerabilities. DVWA and Mutillidae, both intentionally vulnerable web applications, serve as practical arenas for cybersecurity training. They simulate a wide array of security weaknesses, including SQL Injection, offering a hands-on experience in a controlled, legal environment. This setup not only aids security professionals in honing their penetration testing skills but also assists educators and students in integrating practical cybersecurity exercises into their curricula.
<br />
<br />
The confluence of these tools within the lab environment is immensely beneficial to the cybersecurity community. It provides an invaluable platform for gaining firsthand experience in detecting, exploiting, and mitigating SQL Injection vulnerabilities, thereby fostering a deeper understanding of web application security. Moreover, by encouraging the development of security testing skills through real-world scenarios, the lab prepares individuals to better protect digital assets against emerging threats. This holistic approach to cybersecurity education underscores the importance of practical knowledge in complementing theoretical learning, making it an essential practice for those aspiring to excel in the cybersecurity field.
<br />
<br />

<h2>Tools or Utilities Used</h2>

- <b>BurpSuite</b> 
- <b>DVWA</b>
- <b>Mutillidae</b>
- <b>JupterNotebook</b>

<h2>Environments Used </h2>

- <b>Kali Linux 2023.1</b>
- <b>VMware Workstation 17 Pro</b> 

<h2>Lab walk-through:</h2>

### Using Kali Machine and Metasploitable

#### Preparatory Steps

1. **Verify IP Addresses:**
   - Kali Machine IP: `192.168.59.129`.
   - Metasploitable IP: `192.168.59.130`.

2. **Ensure Connectivity:**
   - Confirm connectivity between Kali and Metasploitable by pinging from Kali.

3. **DVWA Setup:**
   - Turn on DVWA on Metasploitable and log in with:
     - Username: `admin`
     - Password: `password`
   - Set DVWA Security to Low.

4. **Proxy Setup in Browser:**
   - Enable Proxy with manual configuration:
     - HTTP proxy: `127.0.0.1`
     - Port: `8080`

5. **BurpSuite Configuration:**
   - Open BurpSuite, choose Temporary project and default settings.
   - Ensure Intercept is Off in the Proxy tab.

#### SQL Injection Practice

1. **Engage with SQL Injection (Blind) in DVWA:**
   - Input `1` in the User ID field.
   - Turn on Intercept in BurpSuite before submitting.
   - After submission, copy the raw data generated on BurpSuite including the cookie value.

2. **Analysis and Further Steps:**
   - With Intercept off, note the output in DVWA.
   - Change browser proxy settings back to no proxy.
   - Utilize Sqlmap with the URL of DVWA and the copied cookie value for further exploration.

### Jupyter Notebook Setup

1. **Anaconda Installation:**
   - Download and install Anaconda from its official website.

2. **Jupyter Notebook:**
   - Launch Anaconda Navigator and Jupyter Notebook.
   - Create a new test notebook and execute a sample print statement.

### Penetration Testing on Bugbounty Target: www.nasa.gov

1. **Footprinting:**
   - Perform domain footprinting, HTTP request and response analysis, port scanning, and HTTP header analysis.

