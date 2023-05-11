# Purpos
For CICD demo with GitHubActions

## Current status
pipeline steps work fine :
    - build with maven
    - sonarcloud scan
    - deployement to cloudhub
    
## todo list
- Find some way to out source the Sonar Instance URL, have to hard code into pipeline file to make it work.

## How to trigger the pipelines
1. We must have an Anypoint account with an organization.
2. We need a technical user to communicate with anypoint platform : Management Center ==> Access Management ==> Connected Apps ==> Owned Apps ==> Create app
3. The technical account should be set into GitHub : (project) Settings ==> secrets and variables ==> Actions ==> New Repository secrets ==> add ANYPOINT_CLIENT_ID & ANYPOINT_CLIENT_SECRET with technical account information
4. A SonarQube instance with Mule plugin installed is necessary for this project, refer to this page of sonar installation : https://github.com/MaximeBAI/mule-sonarqube-plugin
5. ~~Add SonarQube instance URL to GitHub : (project) Settings ==> secrets and variables ==> Actions ==> New repository variable ==> add SONAR_INSTACE with URL value (ex: http://34.71.131.196:9000)

Once deployed, try with http://hostURL:8081/api/flights?airline=american&code=SFO

Should get resault in JSON as the flowing:

[
    {
        "flightCode": "rree1093",
        "availableSeats": 1,
        "destination": "SFO",
        "planeType": "Boeing 737",
        "price": 142.0,
        "origination": "MUA",
        "departureDate": "2016-02-11T00:00:00",
        "airlineName": "American"
    },
    {
        "flightCode": "eefd1994",
        "availableSeats": 0,
        "destination": "SFO",
        "planeType": "Boeing 777",
        "price": 676.0,
        "origination": "MUA",
        "departureDate": "2016-01-01T00:00:00",
        "airlineName": "American"
    },
    {
        "flightCode": "ffee2000",
        "availableSeats": 30,
        "destination": "SFO",
        "planeType": "Boeing 737",
        "price": 300.0,
        "origination": "MUA",
        "departureDate": "2016-02-20T00:00:00",
        "airlineName": "American"
    },
    {
        "flightCode": "eefd3000",
        "availableSeats": 0,
        "destination": "SFO",
        "planeType": "Boeing 737",
        "price": 900.0,
        "origination": "MUA",
        "departureDate": "2016-02-01T00:00:00",
        "airlineName": "American"
    },
    {
        "flightCode": "rree4567",
        "availableSeats": 100,
        "destination": "SFO",
        "planeType": "Boeing 737",
        "price": 456.0,
        "origination": "MUA",
        "departureDate": "2016-01-20T00:00:00",
        "airlineName": "American"
    }
]
