# FND-OT

Instances and results from '*An Adaptive Heuristic for Feeder Network Design withOptional Transshipment*' by Morten Bergmann, Mohamed Kais Msakni, Ahmad Hemmati and Kjetil Fagerholt.

Instance files can be found in the instance folder. mother_ships.txt contains data used for all instances. The remaing files found in adapted-liner-lib, abc-class and generated folders contain instance specific data. To read an instance read mother_ship.txt along with any other file in the instance folder.

Results for all instances can be found in the instance folder.

### Calculating objective values

Objective value for each route:
- **tc rate**: r * w where r is the vessels tc rate and w is the numer of whole weeks (rounded up) it takes to complete the route.
- **cargo costs**: (l * handling_cost) * 2 where l is the total number containers to be loaded/unloaded in the route.
- **bunker costs**: t * bunker_fee where t is the time it takes to sail the whole route and returning to the hub port/origin.
- **port costs**: n * k where n is the number of ports in the route and k is the cost of visiting a port. For daughter routes k will be smaller.

We considered the port costs a fixed cost and therefore excluded it from the objective values. To find the final objective value, sum the objective values for each route (as explained above) and subtract num_ports * mother_visit_cost. 

