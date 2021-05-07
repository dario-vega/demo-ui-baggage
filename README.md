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
jq ".servers[].url" /var/www/html/demo/services/apiBagaggeDemo/openapi3.json
#modify the url in the json file and show only this modification
jq '.servers[].url="<your value>"' /var/www/html/demo/services/apiBagaggeDemo/openapi3.json | jq ".servers[].url"
#modify the url in the json file and show the all json document including the modification, the modification is not applied directly to the file, we need a redirection.
jq '.servers[].url="<your value>"' /var/www/html/demo/services/apiBagaggeDemo/openapi3.json 
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

