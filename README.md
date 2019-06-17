# Windows2019DockerInstall
Instalacja Dockera na Windows 2019
1. Instalacja Docker-Microsoft PackageManagement Provider
  Install-Module -Name DockerMsftProvider -Repository PSGallery -Force

2. Instalacja Docker Engine
  Install-Package -Name docker -ProviderName DockerMsftProvider

2a. Aktualizacja opja + przyszłość Install-Package -Name Docker -ProviderName DockerMsftProvider -Update -Force
Start-Service Docker

3. Restart
  Restart-Computer -Force

4. Weryfikacja
  docker --version
  docker pull microsoft/dotnet-samples:dotnetapp-nanoserver-1809
