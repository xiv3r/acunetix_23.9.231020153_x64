# acunetix_23.9.231020153_x64


## Setup:

- Download Archive File, password is on our post
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
- Now install the tools with sudo : `"sudo bash acunetix_xxxxx.sh"`

- Once installed let's stop its service with: `"sudo systemctl stop acunetix"`
- Let's replace wvsc file:
 ```
  - sudo cp wvsc /home/acunetix/.acunetix/v_231020153/scanner/wvsc
  - sudo chown acunetix:acunetix /home/acunetix/.acunetix/v_231020153/scanner/wvsc
  - sudo chmod +x /home/acunetix/.acunetix/v_231020153/scanner/wvsc
 ```
- Time to add licenses:
 ```
  - sudo rm /home/acunetix/.acunetix/data/license/* (Pay attention to copy and paste right, this can damage your entire OS!!!)
  - sudo cp license_info.json /home/acunetix/.acunetix/data/license/
  - sudo cp wa_data.dat /home/acunetix/.acunetix/data/license/
  - sudo chown acunetix:acunetix /home/acunetix/.acunetix/data/license/license_info.json
  - sudo chown acunetix:acunetix /home/acunetix/.acunetix/data/license/wa_data.dat
  - sudo chmod 444 /home/acunetix/.acunetix/data/license/license_info.json
  - sudo chmod 444 /home/acunetix/.acunetix/data/license/wa_data.dat
  - sudo chattr +i /home/acunetix/.acunetix/data/license/license_info.json (Pay attention to copy and paste right, this can damage your entire  OS!!!)
  - sudo chattr +i /home/acunetix/.acunetix/data/license/wa_data.dat
```
- Now let's restart acunetix:
 ```
- sudo systemctl start acunetix

```
- Now login back to application, and you should be able to use it :)
