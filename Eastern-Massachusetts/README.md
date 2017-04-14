# Eastern Massachusetts (EMA) network


Note: This is a highway subnetwork extracted from the entire EMA network.

## Source / History

Via: [InverseVIsTraffic](https://github.com/jingzbu/InverseVIsTraffic)

## Cost function

An inverse VI problem, as the inverse problem to the typical traffic assignment problem, was formulated in the following publications. The travel latency cost function was assumed unknown. Based on actual traffic data, the equilibrium flows were inferred and OD demand estimated. Finally, the cost function was estimated as a polynomial function with degree 8 (see EMA_intro.pdf). The data were derived for the PM period of Apr. 2012.


## Related publications

Jing Zhang, Sepideh Pourazarm, Christos G. Cassandras, and Ioannis Ch. Paschalidis, "***The Price of Anarchy in Transportation Networks by Estimating User Cost Functions from Actual Traffic Data***," Proceedings of the 55th IEEE Conference on Decision and Control, pp. 789-794, December 12-14, 2016, Las Vegas, NV, USA, Invited Session Paper.

Jing Zhang, Sepideh Pourazarm, Christos G. Cassandras, and Ioannis Ch. Paschalidis, "***Data-driven Estimation of Origin-Destination Demand and User Cost Functions for the Optimization of Transportation Networks***," The 20th World Congress of the International Federation of Automatic Control, July 9-14, 2017, Toulouse, France, accepted as Invited Session Paper. [arXiv:1610.09580](https://arxiv.org/abs/1610.09580#)

Jing Zhang and Ioannis Ch. Paschalidis, "***Data-Driven Estimation of Travel Latency Cost Functions via Inverse Optimization in Multi-Class Transportation Networks***," Proceedings of the 56th IEEE Conference on Decision and Control, December 12-15, 2017, Melbourne, Australia, submitted. [arXiv:1703.04010](https://arxiv.org/abs/1703.04010)

Jing Zhang, Sepideh Pourazarm, Christos G. Cassandras, and Ioannis Ch. Paschalidis, "***The Price of Anarchy in Transportation Networks: Data-Driven Evaluation and Reduction Strategies***," Proceedings of the IEEE: special issue on "Smart Cities," in preparation.


## Scenario

PM perod of Apr. 2012; EMA highway network

## Contents

 - `EMA_net.tntp` Network  
 - `EMA_trips.tntp` Demand  
 - `EMA_entire.png` Map of expanded network  
 - `EMA_highway.jpg` Map of EMA highway network  
 - `EMA_intro.pdf` Description of network and suggestion for cost function  

## Dimensions  
Zones: 74  
Nodes: 74  
Links: 258  
Trips: 65,576.37543099989  

## Units
Time: hours  
Distance: miles  

## Generalized Cost Weights
Toll: 0  
Distance: 0  
