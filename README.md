# ssl-tomcat
To add SSL to Tomcat using PositiveSSL

sudo keytool -genkey -keysize 2048 -keyalg RSA -alias your_domain -keystore your_domain.com.jks
PASS: ***remember***
sudo keytool -certreq -keyalg RSA -alias your_domain -file your_domain.com.csr -keystore your_domain.com.jks

COMPRADO EN: Comodo PositiveSSL
WEB: https://certpanel.com/comodo

USING P7B
I go to SSL converter, in my case this web: https://decoder.link/converter
Select PEM TO PKCS > Upload Files, your_domain.com.crt & CA_Bundle

keytool -import -trustcacerts -alias your_domain -file file.p7b -keystore your_domain.com.jks

Using PEM
keytool -import AAA Certificate Services
  keytool -import -trustcacerts -alias root -file root.crt -keystore your_domain.com.jks
  
keytool -import USERTrust RSA Certification Authority
  keytool -import -trustcacerts -alias intermediate2 -file intermediate_2.crt -keystore your_domain.com.jks
  
keytool -import Sectigo RSA Domain Validation Secure Server CA
  keytool -import -trustcacerts -alias intermediate1 -file intermediate_1.crt -keystore your_domain.com.jks
  
keytool -import example.com.crt
  keytool -import -trustcacerts -alias your_domain -file your_domain.com.crt -keystore your_domain.com.jks
