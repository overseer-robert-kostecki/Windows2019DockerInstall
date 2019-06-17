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
