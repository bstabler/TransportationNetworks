# Transportation Networks

Transportation Networks is a networks repository for transportation research.

If you are developing algorithms in this field, you probably asked yourself
more than once: where can I get good data?  The purpose of this site is to
provide an answer for this question! This site currently contains several examples
for the traffic assignment problem.  Suggestions and additional data are always welcome.

Many of these networks are for studying the Traffic Assignment Problem, which is one of the most
basic problems in transportation research.  Theoretical background can be found in
“The Traffic Assignment Problem – Models and Methods” by Michael Patriksson, VSP 1994,
as well as in many other references.

This repository is an update to Dr. Hillel Bar-Gera's [TNTP](http://www.bgu.ac.il/~bargera/tntp).
As of May 1, 2016, data updates will be made only here, and not in the original website.

# How To Download Networks

Each individual network and related files is stored in a separate folder. There
are a number of ways to download the networks and related files:
  - Click on a file, click view as Raw, and then save the file
  - Clone the repository to your computer using the repository's clone URL. This is done with a Git
      tool such as [TortoiseGit](https://tortoisegit.org).  Cloning will download the
      entire repository to your computer.

# How To Add Networks

There are two ways to add a network:
  - Fork the repo
     - Create a GitHub account if needed
     - Fork (copy) the repo to your account
     - Make changes such as adding a new folder and committing your data
     - Issue a pull request for us to review the changes and to merge your changes into the master
  - Create an issue, which will notify us.  We will then reply to coordinate adding your network to the site.  

Make sure to create a README in [Markdown](https://guides.github.com/features/mastering-markdown) for your
addition as well.  Take a look at some of the existing README files in the existing network folders to see what
is expected.  

# License

All data is currently donated.  Data sets are for academic research purposes only.  
Users are fully responsible for any results or conclusions obtained by using these data sets.
Users must indicate the source of any dataset they are using in any publication that relies
on any of the datasets provided in this web site.  The Transportation Networks for Research team is not
responsible for the content of the data sets. Agencies, organizations, institutions and
individuals acknowledged in this web site for their contribution to the datasets are not
responsible for the content or the correctness of the datasets.

# How to Cite

Transportation Networks for Research Core Team. *Transportation Networks for Research*. https://github.com/bstabler/TransportationNetworks.  Accessed Month, Day, Year.

# Core Team
This repository is maintained by the Transportation Networks for Research Core Team.  The current members are:
  - [Ben Stabler](https://github.com/bstabler)
  - [Hillel Bar-Gera](https://github.com/bargera)
  - [Elizabeth Sall](https://github.com/e-lo)

This effort is also associated with the [TRB Network Modeling Committee](https://trb-aep40.org).  If you are interested in contributing in a more significant role, please get in touch.  Thanks!

# Formats

Any documented text-based format is acceptable.  Please include a README.MD that describes the files,
conventions, fields names, etc.  It is best to use formats that can be easily read in with technologies
like R, Python, etc.  Many of the datasets on TransportationNetworks are in TNTP format.  

## TNTP Data format
TNTP is tab delimited text files, with each row terminated by a semicolon.  The files have the following format:
 - First lines are metadata; each item has a description.  An important one is the `<FIRST THRU NODE>`.
   In the some networks (like Sioux-Falls) it is equal to 1, indicating
   that traffic can move through all nodes, including zones. In other networks when traffic is not
   allow to go through zones, the zones are numbered 1 to n and the `<FIRST THRU NODE>` is set to n+1.
 - Comment lines start with ‘~’.
 - Network files (must be named `<network>_net.tntp`) – one line per link; links are directional, going from “init node” to “term node”.
     - Link travel time = free flow time * ( 1 + B * (flow/capacity)^Power ).
     - Link generalized cost = Link travel time + toll_factor * toll + distance_factor * distance
     - The network files also contain a "speed" value for each link. In some cases the "speed" values
     are consistent with the free flow times, in other cases they represent posted speed limits, and
     in some cases there is no clear knowledge about their meaning. All of the results reported below
     are based only on free flow travel times as described by the functions above, and do not use the speed values.
     - The standard order of the fields in the network files is:
       - Init node
       - Term node
       - Capacity
       - Length
       - Free Flow Time
       - B
       - Power
       - Speed limit
       - Toll
       - Link Type
 - Trip tables (must be named `<network>_trips.tntp`) – An Origin label and then Origin node number, followed by Destination node numbers and OD flow

```
Origin origin#
destination# , OD flow ; …..
```
## Import scripts

The networks' formatting has been harmonized to facilitate programatic imports, and import scripts are provided inside the folder **_scripts**:

| Language     |Format               | Networks                      | Trip matrix                       |
| ---          |---                  | ---                           | ---                               |
| Python       | Jupyter Notebook    | Instructions on using Pandas  | Code to import into OMX           |
| Julia        | Jupyter Notebook    | Using Julia package           | Using Julia package               |

# Summary of Networks

| Network                                            | Zones | Links  | Nodes  | Compatible with provided scripts |
| ---                                                | ---   | ---    | ---    | ---                              |
| Anaheim                                            |    38 |    914 |    416 | Yes                              |
| Austin                                             |  7388 |  18961 |   7388 | Yes                              |
| Barcelona                                          |   110 |   2522 |   1020 | Yes                              |
| Berlin-Center                                      |   865 |  28376 |  12981 | Yes                              |
| Berlin-Friedrichshain                              |    23 |    523 |    224 | Yes                              |
| Berlin-Mitte-Center                                |    36 |    871 |    398 | Yes                              |
| Berlin-Mitte-Prenzlauerberg-Friedrichshain-Center  |    98 |   2184 |    975 | Yes                              |
| Berlin-Prenzlauerberg-Center                       |    38 |    749 |    352 | Yes                              |
| Berlin-Tiergarten                                  |    26 |    766 |    361 | Yes                              |
| Birmingham-England                                 |   898 |  33937 |  14639 | Yes                              |
| Braess-Example                                     |     2 |      5 |      4 | Yes                              |
| chicago-regional                                   |  1790 |  39018 |  12982 | Yes                              |
| Chicago-Sketch                                     |   387 |   2950 |    933 | Yes                              |
| Eastern-Massachusetts                              |    74 |    258 |     74 | Yes                              |
| GoldCoast, Australia                               |  1068 |  11140 |   4807 | Yes                              |
| Hessen-Asymmetric                                  |   245 |   6674 |   4660 | Yes                              |
| Philadelphia                                       |  1525 |  40003 |  13389 | Yes                              |
| SiouxFalls                                         |    24 |     76 |     24 | Yes                              |
| Sydney, Australia                                  |  3264 |  75379 |  33837 | Yes                              |
| Symmetrica Transportation Electrification          |  N.A. |   624  |    169 | No. Not in the TNTP format       |
| Terrassa-Asymmetric                                |    55 |   3264 |   1609 | Yes                              |
| Winnipeg                                           |   147 |   2836 |   1052 | Yes                              |
| Winnipeg-Asymmetric                                |   154 |   2535 |   1057 | Yes                              |

# Publications
A partial list of publications where datasets from this repository have been used. All website users are kindly requested to add their publications to this list.
  - Bar-Gera, H.(2002), Origin-based algorithm for the traffic assignment problem, Transportation Science 36(4), 398-417.
Bar-Gera, H. & Boyce, D. (2003), Origin-based algorithms for combined travel forecasting models, Transportation Research Part B - Methodological  37 (5), 405-422.
  - Boyce, D. & Bar-Gera, H. (2003), Validation of urban travel forecasting models combining origin-destination, mode and route choices, Journal of Regional Science, 43, 517-540.
  - Boyce, D., Ralevic-Dekic, B. & Bar-Gera, H. (2004), Convergence of Traffic Assignments: How Much Is Enough? The Delaware Valley Region Case Study, ASCE Journal of Transportation Engineering, 130 (1), 49-55.
  - Boyce, D. & Bar-Gera, H. (2004), Multiclass Combined Models for Urban Travel Forecasting, Networks and Spatial Economics, 4 (1), 115-124.
  - Bar-Gera, H. & Boyce D. (2006), Solving a non-convex combined travel forecasting model by the Method of Successive Averages with constant step sizes, Transportation Research Part B - Methodological, 40 (5), 351-367.
  - Bar-Gera, H. (2006), Primal Method for Determining the Most Likely Route Flows in Large Road Networks, Transportation Science, 40 (3), 269-286.
  - Bar-Gera, H., Mirchandani, P.B. & Wu, F.ST (2006), Evaluating the assumption of independent turning probabilities, Transportation Research Part B - Methodological, 40 (10), 903-916.
  - Bar-Gera, H. & Luzon, A. (2007), Differences among route flow solutions for the user-equilibrium traffic assignment problem, ASCE Journal of Transportation Engineering, 133 (4), 232-239.
  - Bar-Gera, H. & Luzon, A. (2007), Non-unique route flow solutions for user-equilibrium assignments. Traffic Engineering and Control, 48 (9), 408-412.
  - Bar-Gera, H. (2010), Traffic assignment by paired alternative segments, Transportation Research Part B - Methodological, 44 (8-9), 1022-1046.
  - Bar-Gera, H., Boyce, D. & Nie, Y. (2012), User-equilibrium route flows and the condition of proportionality. Transportation Research Part B - Methodological 46 (3), 440–462.
  - Bar-Gera, H., Hellman, F. & Patriksson, M. (2013), Efficient design and pricing of equilibrium traffic networks precise calculations of equilibria and sensitivities. Transportation Research Part B - Methodological, 57, 485-500.
  - Rey, D.PI, Bar-Gera, H.PI, Dixit, V.PI, Waller, S.T.PI (2019). A Branch and Price Algorithm for the Work-zone Scheduling Problem. Accepted for publication in Transportation Science.

# Other Related Projects
  - [GMNS Plus Dataset](https://github.com/HanZhengIntelliTransport/GMNS_Plus_Dataset) is a publicly available, standardized transportation network collection based on the General Modeling Network Specification (GMNS).
  - [TRB Network Modeling Committee](https://trb-aep40.org)
  - [InverseVIsTraffic](https://github.com/jingzbu/InverseVIsTraffic) is an open-source repository that implements some inverse Variational Inequality (VI) formulations proposed for both single-class and multi-class transportation networks. The package also implements algorithms to evaluate the Price of Anarchy in real road networks. Currently, the package is maintained by [Jing Zhang](http://people.bu.edu/jzh).
  - [Frank-Wolfe algorithm](http://www.bgu.ac.il/~bargera/tntp/FW.zip) that demonstrates how to read these
   data formats and runs a FW assignment.  The header file "stdafx.h" is for Microsoft Visual C (MSVC) compiler. On
   Unix and other compilers it can be simply omitted.
  - [seSue](http://people.sutd.edu.sg/~ugur_arikan/seSue/) is an open source tool to aid research on static path-based
   Stochastic User Equilibrium (SUE) models. It is designed to carry out experiments to analyze the effects of
   (1) different path-based SUE models associated with different underlying discrete choice models
   (as well as hybrid models), and (2) different route choice set generation algorithms on the route choice
   probabilities and equilibrium link flows. For additional information, contact [Ugur Arikan](ugur_arikan@sutd.edu.sg)
  - [TrafficAssignment.jl](https://github.com/chkwon/TrafficAssignment.jl) is an open-source, [Julia](http://www.julialang.org) package that implements some traffic assignment algorithms. It also loads the transportation network test problem data in vector/matrix forms. The packages is maintained by [Changhyun Kwon](http://www.chkwon.net).
  - [DTALite-S](https://github.com/xzhou99/DTALite-S) - Simplified Version of DTALite for Education and Research
  - [NeXTA](https://code.google.com/archive/p/nexta/) open-source GUI for visualizing static/dynamic traffic assignment results
  - [Transit Network Design Instances](https://github.com/RenatoArbex/TransitNetworkDesign) - transit network design instances for research repository
  - [Fast-Trips](http://fast-trips.mtc.ca.gov/) - open source dynamic transit assignment software, data standards, and research project
  - [AMS Data Hub](https://docs.google.com/document/d/1d1Zhnhm-QnCdOpqoe4-EO0U8I4ej17JprGbSgo0zNxU/edit) is an FHWA research project to develop a prototype data hub and data schema for transportation simulation models
  - [GTFS-PLUS](https://github.com/osplanning-data-standards/GTFS-PLUS) -  GTFS-based data transit network data standard suitable for dynamic transit modeling
  - [Open matrix](https://github.com/osPlanning/omx) - Open matrix standard for binary matrix data management that is supported by the major commercial travel demand modeling packages and includes code for R, Python, Java, C#, and C++.
  - [AequilibraE](http://www.aequilibrae.com/) - Python package for transportation modeling
  - [General Modeling Network Specification](https://github.com/zephyr-data-specs/GMNS) - GMNS defines a common human and machine readable format for sharing routable road network files. It is designed to be used in multi-modal static and dynamic transportation planning and operations models.
