# Windows2019DockerInstall
Instalacja Dockera na Windows 2019
1. Instalacja Docker-Microsoft PackageManagement Provider
  Install-Module -Name DockerMsftProvider -Repository PSGallery -Force

2. Instalacja Docker Engine
  Install-Package -Name docker -ProviderName DockerMsftProvider

3. Aktualizacja opcja + przyszłość 
  Install-Package -Name Docker -ProviderName DockerMsftProvider -Update -Force

4. Start serwisu Start-Service Docker

5. Restart
  Restart-Computer -Force

6. Weryfikacja
  docker --version
  docker pull microsoft/dotnet-samples:dotnetapp-nanoserver-1809
  docker run microsoft/dotnet-samples:dotnetapp-nanoserver-1809


Uruchomienie kontenerów linuxowych
1. Usunięcie Dockera CE
  Uninstall-Package -Name docker -ProviderName DockerMSFTProvider
2. Uruchomienie virtualizacji nestet 
  Get-VM WinContainerHost | Set-VMProcessor -ExposeVirtualizationExtensions $true
  #Get-Module -Name Hyper-V -ListAvailable
  #Add-WindowsFeature -Name Hyper-V -IncludeManagementTools
  #Add-WindowsFeature -Name RSAT-Hyper-V-Tools
  #Add-WindowsFeature -Name Hyper-V-PowerShell

3. Instalacja Dockera EE
  Install-Module DockerProvider
  Install-Package Docker -ProviderName DockerProvider -RequiredVersion preview
  
4. Włączenie LinuxKit
[Environment]::SetEnvironmentVariable("LCOW_SUPPORTED", "1", "Machine")

5. Restart 
Restart-Service docker

6. Pull Debiana
 docker run -it --rm ubuntu /bin/bash
7. Na windowsy powrót
[Environment]::SetEnvironmentVariable("LCOW_SUPPORTED", "$null", "Machine")

