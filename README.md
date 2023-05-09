# Purpos
For CICD demo with GitHubActions

## Current status
pipeline steps work fine :
    - build with maven
    - sonarcloud scan
    - deployement to cloudhub
    
## todo list
- A globle pipeline which will organize all these pipeline steps

## How to trigger the pipelines
1. We must have an Anypoint account with an organization.
2. We need a technical user to communicate with anypoint platform : Management Center ==> Access Management ==> Connected Apps ==> Owned Apps ==> Create app
3. The technical account should be set into GitHub : (project) Settings ==> secrets and variables ==> Actions ==> New Repository secrets ==> add ANYPOINT_CLIENT_ID & ANYPOINT_CLIENT_SECRET with technical account information
4. Automatic Analysis must be desactived on SonarCloud : Administration ==> Analysis Method ==> Automatic Analysis ==> disabled
5. We need a SonarCloud project set for Java, add SONAR_TOKEN to GitHub with previous step : (SonarCloud Project)cicddemo ==> Administration ==> Analysis Method ==> Supported analysis methods ==> GitHub Actions ==> Follow the tutorial ==> Create a GitHub Secret

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
