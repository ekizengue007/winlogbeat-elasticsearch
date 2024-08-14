# winlogbeat

1. Create the certificate for the hosts ( windows client in this case ) - i create the certificates on elasticsearch server ))
   ./bin/elasticsearch-certutil cert \
  --out /etc/elasticsearch/certs/windowshost_example.zip \
  --ca-cert /etc/elasticsearch/certs/ca/ca.crt \
  --ca-key /etc/elasticsearch/certs/ca/ca.key \
  --dns *.example.com \
  --name example \
  --pem
   
2. Downloand URL https://www.elastic.co/fr/downloads/beats/winlogbeat
3. Extract and change the name winlogbeat-<version> directory to Winlogbeat
4. 5. Copy the file into C:\Program Files
5. Open a PowerShell prompt as an Administrator (right-click on the PowerShell icon and select Run As Administrator).
6. From the PowerShell prompt, run the following commands to install the service.
   PS > PowerShell.exe -ExecutionPolicy UnRestricted -File .\install-service-winlogbeat.ps1
7. Edit the config file to connect with elasticsearch ( i do have a config with example )
8. Test the config file
   PS > .\winlogbeat.exe test config -c .\winlogbeat.yml -e
9. Set up assets
   PS > .\winlogbeat.exe setup -e
10. Read the logs on C:\ProgramData\winlogbeat\Logs. if everything is ok we can initialise the service
    
   

