# Moja Zastávka
## API and main repository
You are in a new city with the intention to visit some particular building or visit shopping center for example.
Ok, so what if your destination point is on the opposite side of this big city?
You probably want to use public city transport to get there.
But the question is: "Which bus/tram is right and where should I get off?"
The answer is **Moja Zastávka**.

## Tech stack
 - *iOS app:* React native, Redux, Google maps API
 - *API:* Lumen, Google maps API, MariaDB
 - *3rd party resources:* stops list parsed from [OMA Slovakia](http://www.oma.sk)

## Example of stops resource URL
- KE: http://www.oma.sk/api?region=-1690324&tabulka=poi&typ=zastavka,zastavka-elektricky,stanica&limit=1000

In database is currently more than **3500** stops that covers top **10** greatest Slovak cities

## API Endpoint
`
/find-stops?[params]
`

where `params` are: 
```
user_location[name] - optional if lat and lng are provided
user_location[lat] - optional
user_location[lng] - optional

destination[name] - optional if lat and lng are provided
destination[lat] - optional
destination[lng - optional
count - optional, defines count of stops you want to fetch in nearby of the point
```

**NOTE:** In current version of API optional parameters are required(except count) but may remain empty 

Example of valid URL: 

`http://mojazastavka.jozefcipa.com/find-stops?user_location[name]=&user_location[lat]=48.99123119999999&user_location[lng]=21.2459537&destination[name]=&destination[lat]=48.99866963431629&destination[lng]=21.22763914156817&count=3`


&copy;2016-2017 Jozef Cipa & [OMA Slovakia](http://www.oma.sk)

This project uses data from http://openstreetmap.org. These data are available under [ODbL](http://opendatacommons.org/licenses/odbl/summary) license.
