<h1>Simple SQL Injection Lab with BurpSuite/DVWA/Mutillidae</h1>

<h2>Description</h2>
This basic SQL Injection Lab, leveraging the capabilities of Burp Suite, DVWA (Damn Vulnerable Web Application), and Mutillidae, represents an educational toolkit for mastering the intricacies of web security, specifically focusing on SQL Injection—one of the most potent threats to web applications. Burp Suite, a comprehensive set of tools for web application security testing, acts as a critical intermediary, allowing users to intercept and manipulate communications between clients and servers, thereby identifying potential vulnerabilities. DVWA and Mutillidae, both intentionally vulnerable web applications, serve as practical arenas for cybersecurity training. They simulate a wide array of security weaknesses, including SQL Injection, offering a hands-on experience in a controlled, legal environment. This setup not only aids security professionals in honing their penetration testing skills but also assists educators and students in integrating practical cybersecurity exercises into their curricula.
<br />
<br />
The confluence of these tools within the lab environment is beneficial to the cybersecurity community. It provides an invaluable platform for gaining firsthand experience in detecting, exploiting, and mitigating SQL Injection vulnerabilities, thereby fostering a deeper understanding of web application security. Moreover, by encouraging the development of security testing skills through real-world scenarios, the lab prepares individuals to better protect digital assets against emerging threats. This holistic approach to cybersecurity education underscores the importance of practical knowledge in complementing theoretical learning, making it an essential practice for those aspiring to excel in the cybersecurity field.
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

<h2>Preparatory Steps for the Lab:</h2>

### Using Kali Machine and Metasploitable

1. **Verify IP Addresses:**
   - Kali Machine IP: `192.168.59.129`.
     <img src="https://imgur.com/KzWo9YI.png" height="80%" width="80%" alt="Pentest"/>
   
   - Metasploitable IP: `192.168.59.130`.
     <img src="https://imgur.com/H7ySJ8Q.png" height="80%" width="80%" alt="Pentest"/>


2. **Ensure Connectivity:**
   - Verifying the connection between the Kali and Metasploitable machines by sending a ping to the Metasploitable IP from Kali. The ping went through successfully.
     <img src="https://imgur.com/Z9tctcJ.png" height="80%" width="80%" alt="Pentest"/>


3. **DVWA Setup:**
   - Activating the DVWA on the Metasploitable machine by selecting the DVWA option, following navigation to the Metasploitable IP and login with:

     <img src="https://imgur.com/1x0cRHF.png" height="80%" width="80%" alt="Pentest"/>
     
     - Username: `admin`
     - Password: `password`
       
     <img src="https://imgur.com/xgEnQXY.png" height="80%" width="80%" alt="Pentest"/>
        
   - Set DVWA Security to Low.
      <img src="https://imgur.com/PuyzI0O.png" height="80%" width="80%" alt="Pentest"/>

4. **Proxy Setup in Browser:**
   - Activating the browser's proxy settings, switching from 'no proxy' to 'Manual proxy configuration'. Configuring `127.0.0.1` as the HTTP proxy and using port number `8080`.:
   - 
        <img src="https://imgur.com/ISDp1ZE.png" height="80%" width="80%" alt="Pentest"/>
        <img src="https://imgur.com/7zfPAOe.png" height="80%" width="80%" alt="Pentest"/>

5. **BurpSuite Configuration:**
   - Launching BurpSuite and selecting the 'Temporary project' along with the 'default setting' option. Ensuring the 'Intercept is Off' within the Proxy tab.
     
      <img src="https://imgur.com/PkCznCs.png" height="80%" width="80%" alt="Pentest"/>
      
<h2>SQL Injection Practice:</h2>


1. **Engage with SQL Injection (Blind) in DVWA:**
   - Input `1` in the User ID field.
      <img src="https://imgur.com/77JUqxJ.png" height="80%" width="80%" alt="Pentest"/>
   - Turn on Intercept in BurpSuite before submitting.
   - Following the submission of the User ID on DVWA, BurpSuite generates raw data, from which the cookie value will be copied.
      <img src="https://imgur.com/XqOrgwJ.png" height="80%" width="80%" alt="Pentest"/>
      
 

2. **Analysis and Further Steps:**
   - After turning off the intercept feature in BurpSuite, the displayed output shows ID: 1, First Name: admin, and Surname: admin.
     <img src="https://imgur.com/vyk7PaP.png" height="80%" width="80%" alt="Pentest"/>
      
   - Change browser proxy settings back to no proxy.
     <img src="https://imgur.com/dzEDIP6.png" height="80%" width="80%" alt="Pentest"/>
     
   - Utilize Sqlmap with the URL of DVWA and the copied cookie value for further exploration. Sqlmap identifies the database, allowing us to view the databases that are present.
     <img src="https://imgur.com/pcKKxtH.png" height="80%" width="80%" alt="Pentest"/>
     <img src="https://imgur.com/7uc1wUk.png" height="80%" width="80%" alt="Pentest"/>

   - Exploring all the columns within the DVWA database. 
     <img src="https://imgur.com/kZfMaEl.png" height="80%" width="80%" alt="Pentest"/>

   - Accessing the OWASP Top 10 Database.
     <img src="https://imgur.com/mDilxns.png" height="80%" width="80%" alt="Pentest"/>

   - Extracting the user password files from the DVWA database.
     <img src="https://imgur.com/qYdzxGy.png" height="80%" width="80%" alt="Pentest"/>
     <img src="https://imgur.com/VsVnJNK.png" height="80%" width="80%" alt="Pentest"/>

   - Reconfiguring the proxy to manual settings to execute sqlmap with an HTTP Request.
     <img src="https://imgur.com/k5lfLwj.png" height="80%" width="80%" alt="Pentest"/>

   - Ensuring that the intercept feature is turned off again in BurpSuite.
     <img src="https://imgur.com/TjgKRy9.png" height="80%" width="80%" alt="Pentest"/>

   - Navigating to http://192.168.59.130/mutillidae/.
     <img src="https://imgur.com/S49XeNM.png" height="80%" width="80%" alt="Pentest"/>

   - Selecting the User Info page under OWASP Top 10 -> SQLi Extract Data. Entering the credentials: Name as `MI5Group` and Password as `M15Grouppass`. Remember to turn on the intercept before submitting the name and password.
     <img src="https://imgur.com/Jvo19Yn.png" height="80%" width="80%" alt="Pentest"/>
     <img src="https://imgur.com/FgmxTG2.png" height="80%" width="80%" alt="Pentest"/>
     <img src="https://imgur.com/raydYqJ.png" height="80%" width="80%" alt="Pentest"/>

   - Storing the raw data on the desktop under the file name request1.txt. This file is then used as the input for executing an SQL HTTP request on the Kali machine for SQLmap enumeration for further actions.
     <img src="https://imgur.com/qjYq7Um.png" height="80%" width="80%" alt="Pentest"/>
     <img src="https://imgur.com/nvXslbC.png" height="80%" width="80%" alt="Pentest"/>
     

<h2>Jupyter Notebook Setup:</h2>

1. **Anaconda Installation:**
   - Downloading Anaconda from its official website, followed by a successful installation and the launch of Anaconda Navigator. Proceeding to open the Anaconda Command Prompt to install Python packages.
   <img src="https://imgur.com/OWuPtnG.png" height="80%" width="80%" alt="Pentest"/>
   <img src="https://imgur.com/p64J7wK.png" height="80%" width="80%" alt="Pentest"/>
   <img src="https://imgur.com/4SzOV0i.png" height="80%" width="80%" alt="Pentest"/>

2. **Jupyter Notebook:**
   
   <img src="https://imgur.com/IWKrYLF.png" height="80%" width="80%" alt="Pentest"/>


<h2>Bonus: Penetration Testing on Bugbounty Target: www.nasa.gov:</h2>

1. **Footprinting:**
   - Executing a `dig` command on the website's domain name to retrieve comprehensive details about the site.
   <img src="https://imgur.com/fcah96I.png" height="80%" width="80%" alt="Pentest"/>
   
   - Perform domain footprinting, HTTP request and response analysis, port scanning, and HTTP header analysis.
   <img src="https://imgur.com/9MiRgqa.png" height="80%" width="80%" alt="Pentest"/>
   <img src="https://imgur.com/R72w69T.png" height="80%" width="80%" alt="Pentest"/>
   <img src="https://imgur.com/Pl1vInj.png" height="80%" width="80%" alt="Pentest"/>
   <img src="https://imgur.com/AAYwowh.png" height="80%" width="80%" alt="Pentest"/>

