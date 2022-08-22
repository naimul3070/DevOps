# PowerBi

## Requirment Stafs Download Link

* <a href="">Operating System windows server (datacenter Desktop experiance)</a>

* <a href="https://go.microsoft.com/fwlink/p/?linkid=866662">MSSQL Server(For check the database connection status okay) </a>
 
 <img src="https://user-images.githubusercontent.com/43438240/180958732-ca9c0c64-5b33-4e78-b718-af7b5dd6e39b.png" width="400" height="350"/>

* <a href="https://aka.ms/ssmsfullsetup">MSSQL Management Studio </a>
 
* <a href="https://www.microsoft.com/en-us/download/details.aspx?id=56722" width="400" height="350">PowerBi Server</a>

<img src="https://user-images.githubusercontent.com/43438240/180958823-8201d703-f16e-441d-9af7-24e29ac8d3b2.png" width="400" height="350"/>

After restart check that the mmc is working properly according to image

<img src="https://user-images.githubusercontent.com/43438240/180979739-6bc0292c-c7c9-4130-b7c5-d2b8f181acbb.png" width="400" height="350"/>


## PowerBI Report Server Configuration Manager

* Start Report server configuration manager
* Login  with pc default connection 

<img src="https://user-images.githubusercontent.com/43438240/180976612-5c9fd268-5a3f-4807-bbf0-b97b9275f25e.png" width="400" height="350"/>


* Service Account >> use service account 

<img src="https://user-images.githubusercontent.com/43438240/180981373-ee197b76-3460-48b9-9bf0-2e34b35b806a.png" width="400" height="350"/>


select the server Ip address

<img src="https://user-images.githubusercontent.com/43438240/180979831-dfdd145e-d12c-4c39-9c5c-0b5700c7b512.png" width="400" height="350"/>

connect database  click change Database > choose an create new database

Test the Connection

<img src="https://user-images.githubusercontent.com/43438240/180979930-5d0afd52-723b-4163-aa74-a319fbfa7e50.png" width="400" height="350"/>

Select the service credentials / AC credentials

<img src="https://user-images.githubusercontent.com/43438240/180979960-a89dc30f-4a65-45e5-a07b-25ce23202a9c.png" width="400" height="350"/>

Web portal URL 

<img src="https://user-images.githubusercontent.com/43438240/180980329-302056b5-a764-428b-a807-b05830198dc4.png" width="400" height="350"/>



## [ Note: Web Service name & Web portal url must be different ]

## SSL Add

* Microsoft Management Console (MMC.exe search in windows Startup Menu >> if not run after click then >>> got to open file location and run it)
- Go to file >> Add/remove Snap-ins 
-Scroll Down >> Certificate (click Add)
-Service account
-Local computer 
-Power BI Report Server
- Console Root >>
-PowerBIReportServer\Trusted Root Certificate Authorities
-Certificates
-Right Click >> All tasks>> Import (SSL) >> Automatically select the certificate store based on the type of certificate >> Finish

