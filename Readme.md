Run Server
./td.sh datasource=china-latest.osm.pbf
First run will cost lots of time to setting up the cache.

There is an endpoint to fetch all roads with changes which is used for the traffic info:
http://localhost:8989/roads

Feed data to '/datafeed':

Bash:
curl -H "Content-Type: application/json" --data @path-to-your-traffic.json http://localhost:8989/datafeed

Data format: json
[{
   "id": "1",
   "points": [[6.827273, 51.190264]],
   "value": 10,
   "value_type": "speed",
   "mode": "REPLACE"
}, {
   "id": "somethingelse",
   "points": ...
}
]
One points represent correspond road.

# License

This code stands under the Apache License 2.0