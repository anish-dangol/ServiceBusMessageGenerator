# ServiceBusMessageGenerator

Add-Type -Path "C:\Program Files (x86)\Reference Assemblies\Microsoft\Framework.NETFramework\v4.5\System.IO.Compression.FileSystem.dll"

$url = "https://github.com/linuxacademy/content-azure-labs/blob/master/zips/azure-service-bus-queues.zip?raw=true" $zipfile = "C:\Users\azureuser\Desktop\azure-service-bus-queues.zip" $folder = "C:\Users\azureuser\Desktop"

[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12 Invoke-WebRequest -UseBasicParsing -OutFile $zipfile $url

[System.IO.Compression.ZipFile]::ExtractToDirectory($zipfile, $folder)

Remove-Item -Path $zipfile
