"# DevChallenge" 
"# DevChallenge" 


The service will does a RESTful POST to /shops with a JSON of shopName, shopAddress.number and shopAddress.postCode to the ShopsFacade (microservice) which utilizes the MapService to get latitude and longitude of the shop. The Mapservice responds with the longitude and latitude, which updates the shops array containing {shopName, shopAddress.number, shopAddress.postCode, longitude and latitude}.


The solution is run using chrome rest client api : chrome://restclient/content/restclient.html

Provide below input:

[
   {
      "name": "POST http://localhost:9000/shops",
      "method": "POST",
      "url": "http://localhost:9000/shops",
      "authuser": null,
      "authpwd": null,
      "accept": "application/json",
      "contenttype": "application/json",
      "headerarray": [],
      "data": {
         "shopName": "Rossmann",
         "shopAddress.number": "4",
         "shopAddress.postcode": "81543"
      }
   }
]

[source,json]{
         "shopName": "Rossmann",
         "shopAddress.number": "4",
         "shopAddress.postcode": "81543"
      }

Expected Output:
  Status Code: 201 Created
=========================================================

The service does a RESTful GET to the Shops API, providing the  current longitude and latitude of the customer(e.g. URL request params), and gets back the address, longitude and latitude of the shop nearest to them.

[{
url: http://localhost:9000/shops/?latitude=45&&longitude=14

Expected output:
Shop details of the nearest shop for example:
{"shopName":"Rossmann","shopAddress.number":"4","shopAddress.postcode":"81543","latitude":"47.0855924","longitude":"15.4721835"}]
