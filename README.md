# Weekend-Hackathon-7---Covid-Statistics
Run node /src/createDatabase.js .


GET localhost:8080/totalRecovered
will calculate the total number of recovered patients across all the given states(also UTs).
Returned response is in the format {data: {_id: "total", recovered:135481}}.



GET localhost:8080/totalActive
will calculate the total number of active patients across all the given states(also UTs).
Active cases = (infected-recovered)
Returned response is in the format {data: {_id: "total", active:11574}}.



GET localhost:8080/totalDeath
will calculate the total number of deaths across all the given states(also UTs).
Returned response is in the format {data: {_id:"total", death:11574}}.



GET localhost:8080/hotspotStates
Every state is declared as a hotspot of its rate value is greater than 0.1.
rate value is calculated as ((infected - recovered)/infected)
rate value is rounded to 5th decimal point using MonogDb built-in feature $round.

Returned response is in the format {data: [{state: "Maharastra", rate: 0.17854}, {state: "Punjab", rate: 0.15754}]}.

GET localhost:8080/healthyStates
Every state is declared as a healthy state of its mortality value is less than 0.005.
mortality value is calculated as (death/infected).
mortality value is rounded to 5th decimal point using MonogDb built-in feature $round.

Returned output is in the format {data: [{state: "Maharastra", mortality: 0.0004}, {state: "Punjab", mortality: 0.0007}]}.
