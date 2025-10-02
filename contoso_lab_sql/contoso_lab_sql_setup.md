# contoso lab sql setup

contoso lab sql setup    

Windows Features   
---

> `--- for wsl`  
> Enable-WindowsOptionalFeature -Online -FeatureName VirtualMachinePlatform -NoRestart  
>
> `--- to wsl`    
> Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux -NoRestart  
> 
> `--- for docker desktop`  
> Enable-WindowsOptionalFeature -Online -FeatureName HypervisorPlatform -NoRestart  
>
> Restart-Computer -Force  

WSL
---

> `-- wsl setup`  
>
> wsl --status  
>
> `--- updgrade to wsl2`  
> wsl --update  
> wsl --status

> `-- install wsl ubuntu`  
> wsl --install  
> `user@ubuntu> sudo apt update`  
> `user@ubuntu> sudo apt full-upgrade`  

> `--- wsl --install --distribution ubuntu`  
> `--- wsl -d ubuntu`  
> `--- wsl`
 
> wsl --list  
> wsl --list --online  
> wsl --list --verbose  
> wsl --shutdown  

> `--- wsl --set-default-version 2`    
> `--- wsl --set-default ubuntu`

Docker
---

> `Start-Process 'C:\Users\<username>\Downloads\Docker Desktop Installer.exe' -Wait -ArgumentList 'install', '--accept-license', '--backend=wsl-2'`
  
`hello-world`  
> docker run hello-world  
> docker ps --all  

`pg17`  
> docker run -d --name pg_1 -p 5432:5432 -e POSTGRES_PASSWORD=postgres postgres:17  
> docker stop pg_1

`pg17 + cutom data volume location`  
> `docker run -d --name pg_2 -p 5432:5432 -e POSTGRES_PASSWORD=postgres -v C:\Users\username\wsl\vol_pg_2:/var/lib/postgresql/data postgres:17`   
> docker stop pg_2  

`pg18/latest`
> docker run -d --name pg_3 -e POSTGRES_PASSWORD=postgres -p 5432:5432 postgres:latest  
> docker stop pg_3  

---
