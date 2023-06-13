# demo-ui-baggage

## Running the project in Visual Builder Managed Service

Please contact me

## Running the project in IaaS or On-Premise

````
sudo su -
yum install -y httpd
systemctl enable  httpd.service
systemctl start  httpd.service
yum install jq 
firewall-cmd  --permanent --add-port=80/tcp 
firewall-cmd  --permanent --add-port=443/tcp 
systemctl restart firewalld
cd /var/www/html/
cp demo-ui-baggage/optimized.zip .
unzip optimized.zip -d demo
Some jq commands that can help you to change the API Gateway to use
#find the url in the json file
OLDGW=`jq -r ".servers[].url[8:-12]" /var/www/html/demo/services/apiBagaggeDemo/openapi3.json`
echo $OLDGW
#modify the url in the json file - provide your new APIGW url
find demo -type f -exec sed -i "s/$OLDGW/dqoqyovkqdd6tl6dxrgbamt6xu.apigateway.eu-paris-1.oci.customer-oci.com/g"   {} \;
#customize the links sections if desired
find . -type f -exec sed -i "s/Useful Links/You are at Paris Region/g"   {} \;
````

```
ls -lrt mobileApps/baggagedemo*/index.html
ls -lrt webApps/webbaggage*/index.html
```
NB If you've created your own version of Digital Assistant, Please modify webApps/webbaggagecustomer/index.html

## Use the following URL in order to test
- PWA from your mobile : https://<yourwebserver>/demo/mobileApps/baggagedemocustomer/index.html
- webApp from your browser : https://<yourwebserver>/demo/webApps/webbaggageairline/index.html
  
## Do not forget, the application is accessible also using our geo-distributed configuration

- http://ndcsdemo.com/ 

