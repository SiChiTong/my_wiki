## This week
**_Due Date_** : 30/09  
**_Task_** :  A* evaluation methods   
**_From_** :  Motion Planning Group

### Collected Materials  
http://cdn.intechopen.com/pdfs/10249.pdf

1. Mission success: number of successful missions.
2. Path length: distance traveled to accomplish the task.
3. Time: time taken to accomplish the task.
4. Collisions: number of collisions per mission, per distance and per time.
5. Obstacle clearance: minimum and mean distance to the obstacles.
6. Robustness in narrow spaces: number of narrow passages successfully traversed.
7. Smoothness of the trajectory: relative to control effort. 

 * [**Evaluation Metric**](https://www.researchgate.net/publication/290579828_The_Grid-Based_Path-Planning_Competition) : 
 
>The metrics tested will include:  
[http://movingai.com/GPPC/cfp.html]
* The total time to find a complete path.
* The time to find the first 20 steps of the path.
* The maximum time for returning any portion of a path.
* The total path length (suboptimality).
* The total memory (RAM) usage.
* The total disk usage.
* The pre-processing time

> 1.The total time required for finding a complete path.
This is one of the most common measurements used
for evaluating a path-planning system.  
2.The time required to find the first 20 steps of a path.
This metric is important in real-time systems, where
an agent can start moving as soon as a sufficiently
long initial path has been found.  
3.The maximum time for returning any set of actions.
This is another metric important for real-time systems,
when the amount of time for each planning step is
limited.  
4.The memory required for preprocessing. Memory can
almost always be used to speed things up; however,
mobile, embedded, or other memory-constrained
applications have hard limits on how much offline or
online storage must be used. (Online storage is that
which is dynamically allocated for search, while
offline storage is precomputed and stored or shipped
with an application.)  
5.The time required for preprocessing. Preprocessing can
usually be performed in an offline phase, amortizing
its cost over many problem instances, but in some
applications the cost of preprocessing matters.  
6.The memory required at run time. This is related to
the previous metrics, just measuring online memory
instead of offline memory.    
7.The quality of the paths found. Path quality is an
important metric, but can be misleading. It is meas-
ured in two ways. The first is comparing the sum of
the length of all paths found to the sum of the optimal
path lengths. This measurement gives more weight to
long paths. The second is by comparing the average
ratio of path lengths found. This measurement gives
equal weight to all paths.  

  1. calculation time **AND**  energy consumption, and success rate in terms of not colliding with obstacles.
  2.  length (path length), distance from the obstacle,  etc.
  3.   smoothness: geometric continuity of the robots path
  4.   memory footprint
  5.    dynamic nature of the algorithm:static environment **OR** dynamic environment 
  6.  ......
  
* **Methods** 

1.  [Benchmark Maps](http://rkala.in/papers/AIRE-2010.pdf)  
      different map size , different numbers and kinds of obstacle : Maze, scattered
2.  [BENCHMARKING ROBOT PATH PLANNING](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.106.2600&rep=rep1&type=pdf)  
      formulate a metric for search space in gridmap and classify/rating search space with complexity index value.
THE BENCHMARK EQUATION: CI = A(%Obstacle) + B(#Obstacles)　+ C(Distribution) + D(TurnFactor) + E(Orientation) 
3. [Benchmarking sampling-based planners](https://www.cs.rice.edu/~mmoll/publications/moll2015benchmarking-motion-planning-algorithms.pdf)
  [Visualization Tools](http://plannerarena.org/)
4. [RosPackage](http://ieeexplore.ieee.org/document/6386228/?part=1)
5. [kinodynamic planners Benchmarking](https://link.springer.com/chapter/10.1007/978-3-319-27146-0_4)
6. ......  
  http://ieeexplore.ieee.org/document/7995802/   
  http://authors.library.caltech.edu/39299/1/report-tr_spooner.pdf