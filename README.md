<img width="1000" height="500" src="https://github.com/xiv3r/acunetix_23.11.231123131_x64/blob/main/logo/acunetix-logo.png">

# <h1 align="center">Acunetix_23.9.231020153_x64</h1>

<p align="center"> Acunetix is an automated web application security testing tool that audits your web applications by checking for vulnerabilities like SQL Injection, Cross site scripting and other exploitable vulnerabilities. In general, Acunetix scans any website or web application that is accessible via a web browser and uses the HTTP/HTTPS protocol.
<p align="center">Acunetix offers a strong and unique solution for analyzing off-the-shelf and custom web applications including those utilizing JavaScript, AJAX and Web 2.0 web applications. Acunetix has an advanced crawler that can find almost any file. This is important since what is not found cannot be checked.
</p>

## Setup:

    git clone https://github.com/xiv3r/acunetix_23.9.231020153_x64

    cd acunetix_23.9.231020153_x64
    
    wget https://github.com/xiv3r/acunetix_23.9.231020153_x64/releases/download/acunetix/acunetix_23.9.231020153_x64.sh

    
- Before installing the tool, add to your hosts file (usually /etc/hosts) at the end:

```
  127.0.0.1  erp.acunetix.com
  127.0.0.1  erp.acunetix.com.
  ::1  erp.acunetix.com
  ::1  erp.acunetix.com.

  192.178.49.174  telemetry.invicti.com
  192.178.49.174  telemetry.invicti.com.
  2607:f8b0:402a:80a::200e  telemetry.invicti.com
  2607:f8b0:402a:80a::200e  telemetry.invicti.com.
```

- Now install the tools with sudo : `sudo bash acunetix_23.9.231020153_x64.sh`

- Once installed let's stop its service with: `sudo systemctl stop acunetix`

- Replace the `wvsc` file:

 ```
  sudo mkdir -p /home/acunetix/.acunetix/v_231020153/scanner
  sudo cp wvsc /home/acunetix/.acunetix/v_231020153/scanner/wvsc
  sudo chown acunetix:acunetix /home/acunetix/.acunetix/v_231020153/scanner/wvsc
  sudo chmod +x /home/acunetix/.acunetix/v_231020153/scanner/wvsc
 ```

- Adding licenses:
 
 ```
  sudo rm /home/acunetix/.acunetix/data/license/*
  sudo mkdir -p /home/acunetix/.acunetix/data/license
  sudo cp license_info.json /home/acunetix/.acunetix/data/license/
  sudo cp wa_data.dat /home/acunetix/.acunetix/data/license/
  sudo chown acunetix:acunetix /home/acunetix/.acunetix/data/license/license_info.json
  sudo chown acunetix:acunetix /home/acunetix/.acunetix/data/license/wa_data.dat
  sudo chmod 444 /home/acunetix/.acunetix/data/license/license_info.json
  sudo chmod 444 /home/acunetix/.acunetix/data/license/wa_data.dat
  sudo chattr +i /home/acunetix/.acunetix/data/license/license_info.json
  sudo chattr +i /home/acunetix/.acunetix/data/license/wa_data.dat
```

- Restart acunetix service:

```
  sudo systemctl start acunetix

```

- Run [https://localhost:3443](https://localhost:3443)
