#pull self
#Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://raw.githubusercontent.com/JordanNiphan/SlaetChoco/refs/heads/main/README.md'))

#pull choco (if not installed)
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))

#pull packager.config
Invoke-WebRequest https://raw.githubusercontent.com/JordanNiphan/SlaetChoco/refs/heads/main/packages.config -OutFile .\packages.config

#run choco
choco install .\packages.config -y
