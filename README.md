# cs6250-assignment-7-distance-vector-solved



**<span style='color:red'>TO GET THIS SOLUTION VISIT:</span>** https://www.ankitcodinghub.com/product/distance-vector-cs6250-solved/

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;112320&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;1&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (1 vote)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CS6250 Assignment 7-Distance Vector  Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">
            
<div class="kksr-stars">
    
<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
    
<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>
                

<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (1 vote)    </div>
    </div>
<h1><a name="_Toc12421"></a>PROJECT GOAL</h1>
In the lectures, you learned about Distance Vector (DV) routing <strong>protocols,</strong> one of the two classes of routing protocols. DV protocols, such as RIP, use a fully distributed algorithm to find shortest paths by solving the Bellman-Ford equation at each node. In this project, you will develop a distributed Bellman-Ford algorithm and use it to calculate routing paths in a network. This project is similar to the Spanning Tree project, except that we are solving a routing problem, not a switching problem.

In “pure” distance vector routing protocols, the hop count (the number of links to be traversed) determines the distance between nodes. Some distance vector routing protocols, that operate at higher levels (like BGP), must make routing decisions based on business valuations. These protocols are sometimes referred to as Path Vector protocols. We will explore this by using weighted links (including negatively weighted links) in our network topologies.

We can think of Nodes in this simulation as individual Autonomous Systems (ASes), and the weights on the links as a reflection of the business relationships between ASes. Links are directed, originating at one Node, and terminating at another.

<h2><a name="_Toc12422"></a>Part 0: Getting Started</h2>
You should review some materials on Bellman-Ford. Some resources include:

<ul>
<li>Wikipedia (<a href="https://en.wikipedia.org/wiki/Bellman%E2%80%93Ford_algorithm">https://en.wikipedia.org/wiki/Bellman%E2%80%93Ford_algorithm</a><a href="https://en.wikipedia.org/wiki/Bellman%E2%80%93Ford_algorithm">)</a></li>
<li>“Computer Networking: A Top-Down Approach” by Kurose and Ross o 7<sup>th</sup> edition discusses the algorithm on pages 384-385 in Chapter 5 (“The Network Layer: Control Plane”)</li>
</ul>
Download and unzip the Project Files for Distance Vector from Canvas in the Assignments section. This project can be completed in the class VM or on your local machine using Python

3.10.x. You must be sure that your submission runs properly in Gradescope.

<h2><a name="_Toc12423"></a>Part 1: Files Layout</h2>
The DistanceVector directory contains the following files:

<ul>
<li>py – This is the only file you will modify. It is a specialization (subclass) of the Node class that represents a network node (i.e., router) running the Distance Vector algorithm, which you will implement.</li>
<li>py – Represents a network node, i.e., a router.</li>
<li>py – Represents a network topology. It is a container class for a collection of DistanceVector Nodes and the network links between them.</li>
<li>py – A simple “driver” that loads a topology file (see *Topo.txt below), uses that data to create a Topology object containing the network Nodes, and starts the simulation.</li>
<li>*Topo.txt – These are valid topology files that you will pass as input to the run.sh script (see below). Topologies should end with “.txt”.</li>
<li>txt – This is an invalid topology file, provided as an example of what not to do, and so you can see what the program says if you pass it a bad topology.</li>
<li>py – This script can be run on the log output from the simulation to verify that the output file is <strong>formatted</strong> correctly. It does not verify that the contents are correct, only the format.</li>
<li>sh – A helper script that runs some basic system checks, the topology, and the validator, a wrapper for run_topo.py and output_validator.py .</li>
</ul>
<h2><a name="_Toc12424"></a>Part 2: TODOs</h2>
There are a few TODOs in DistanceVector.py:

<ol>
<li><strong><em>Review the methods already implemented in Node.py</em></strong>.
<ol>
<li>Because DistanceVector is a subclass of Node, consider how you might use the existing methods to complete the TODOs in this list.</li>
<li><strong>Do NOT modify Node.py</strong>.</li>
</ol>
</li>
<li><strong><em>Decide on how each node will represent its distance vector</em></strong>.
<ol>
<li>Consider what might be the simplest data structure to keep track of path weights (i.e., the distance vector).</li>
<li>The distance vector variable should be local to the Node, i.e., defined in the init function as a variable accessible via the `self` object (i.e. self.mylist). C. <strong><em>Implement the Bellman-Ford algorithm</em></strong>.</li>
<li>Each Node will:
<ol>
<li>send out an initial message to its neighbors</li>
<li>process messages received from other nodes</li>
</ol>
</li>
</ol>
</li>
</ol>
<ul>
<li>send updates to other nodes as needed</li>
</ul>
<ol>
<li>Initially, a node only knows of:</li>
<li>itself and that it is reachable at cost 0,</li>
<li>its neighbors and the weights on its links to its neighbors</li>
</ol>
<ol>
<li>NOTE: a node’s links are <strong>unidirectional</strong>.</li>
<li>NOTE: The Bellman-Ford algorithm implementation should terminate naturally without external intervention.</li>
<li><strong><em>Write a logging function</em></strong> that is specific to your distance vector structure.</li>
</ol>
<ol>
<li>You should use the <em>add_entry</em> function to help with logging.</li>
<li>You should assume that the logging function only knows itself.</li>
<li><strong>Do NOT access the topology for logging</strong>; logging should happen at the Node level.</li>
</ol>
<h2><a name="_Toc12425"></a>Part 3: Testing and Debugging</h2>
To run your algorithm on a specific topology, execute the run.sh bash script:

<h3>./run.sh *Topo</h3>
Substitute the correct, desired filename for *Topo. Don’t use the .txt suffix on the command line. This will execute your implementation of the algorithm in DistanceVector.py on the topology defined in *Topo.txt and log the results (per your logging function) to *Topo.log .

<strong>NOTE</strong>: You should <em>not</em> include the full filename of the topology when executing the run.sh script. For example, to run the algorithm on topo1.txt you should only specify topo1 as the argument to run.sh.

For this project, you may create as many topologies as you wish and share them on Ed Discussion. We encourage sharing new topologies with log outputs. Topologies with format errors will get an error back when you try to run them.

We’ve included four good topologies for you to use in testing and one bad topology to demonstrate invalid topology. <strong>The provided topologies do not cover all the edge cases; your code will be graded against more complex topologies</strong>.

<h2><a name="_Toc12426"></a>Part 4: Assumptions and Clarifications</h2>
<ol>
<li><strong>Node behavior: </strong>
<ol>
<li>The direction of a link indicates how <strong>traffic</strong> will flow; two nodes connected with a link <strong><em>may pass messages regardless of traffic direction</em></strong>.
<ol>
<li>Example: Node B has an incoming link from Node A, but has no outgoing link to Node A, Node B will send its distance vector to node A to</li>
</ol>
</li>
</ol>
</li>
</ol>
“advertise” &nbsp;&nbsp;&nbsp; other &nbsp;&nbsp;&nbsp; nodes &nbsp;&nbsp;&nbsp; it &nbsp;&nbsp;&nbsp; can &nbsp;&nbsp;&nbsp; reach &nbsp;&nbsp;&nbsp; (Nodes &nbsp;&nbsp; C &nbsp;&nbsp;&nbsp; and &nbsp;&nbsp;&nbsp; D).

&nbsp;

<ol>
<li>A Node’s distance vector is comprised of the nodes it can reach via its outgoing links (<strong><em>including</em></strong> to itself at distance = 0).
<ol>
<li>A Node will never advertise a negative distance to itself. (Important for negative cycles.)</li>
</ol>
</li>
<li>A Node advertises its distance vector to its <strong><em>upstream</em></strong></li>
<li>Nodes do <strong>not</strong> implement poison-reverse.</li>
</ol>
<ol>
<li><strong>Edge and Path weights: </strong>
<ol>
<li>Edge weight values may be between <strong>-50 and 50, inclusive.</strong></li>
<li>The edge weight value type is an <strong>integer</strong>.</li>
<li>There is no upper limit for path weights.</li>
<li>The lower limit for path weights is “-99”, which is equivalent to “negative infinity” for this project. <strong> Negative cycles: </strong></li>
<li>A Node can forward traffic through a negative cycle.</li>
<li>Negative cycles are a series of directed links that originate and terminate at a single node, where the sum of the link weights is less than 0.
<ol>
<li>This can lead to a negative “count-to-infinity” problem. Therefore, your implementation must be able to detect negative cycles to <strong>terminate on its own</strong>.</li>
<li>Any node that can reach a destination node and infinitely traverse a negative cycle enroute will set the distance to that node to -99.
<ol>
<li>Your implementation only needs to detect and record these traversals appropriately; it does not need to mitigate them.</li>
<li>Extra resource: Professor Vigoda explains Negative Weight Cycles and how to detect them, which is Lecture 4, Parts 2-7 of GATech’s “Introduction to Graduate Algorithms” course on Udacity.<a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a> (Parts</li>
</ol>
</li>
</ol>
</li>
</ol>
</li>
</ol>
6 &amp; 7 are Bellman-Ford specific.)

<ul>
<li>A Node can advertise a negative distance for other nodes (but not for itself).</li>
</ul>
<ol>
<li>A Node that receives an advertisement with a distance of -99 from a downstream neighbor should also assume that it can reach the same destination at infinitely low cost (-99).</li>
<li><em>Example</em>: Traffic from Node F to Node D can route through A-&gt;B-&gt;C-&gt;A indefinitely to &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; reach &nbsp; an &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; extremely &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; low &nbsp;&nbsp;&nbsp;&nbsp; (very &nbsp;&nbsp; negative)</li>
</ol>
&nbsp;

<ol>
<li>A Node will <strong><em>not</em> </strong>forward traffic destined to itself.</li>
<li>Example: The below topology will <strong><em>not</em></strong> result in a count-to-infinity problem, as there are no possible pairs of source and destination nodes</li>
</ol>
&nbsp;

where traffic could indefinitely traverse a negative cycle. Node A will not forward traffic for Node A, and similarly for Nodes B and C.

&nbsp;

&nbsp;

<ol>
<li>Topologies used in grading:</li>
</ol>
<ol>
<li>We will be using many topologies to test your project. This includes but is not limited to:
<ul>
<li>topologies with and without cycles (loops), including odd length cycles o topologies of varying sizes, including topologies with more than 26 nodes&nbsp; o topologies with nodes with names longer than one character o topologies with multiple paths to different nodes</li>
<li>topologies that include any combination of positive weights, zero weight, and negative weight</li>
<li>topologies with negative cycles, meaning a node may reach another at infinitely low cost</li>
<li>topologies with Nodes that do not have incoming or outgoing links ▪ All nodes will be connected but:
<ul>
<li>some may have both incoming and outgoing links</li>
<li>some may only have incoming links some may only have outgoing links</li>
</ul>
</li>
</ul>
</li>
</ol>
<ol>
<li>We will NOT test your submission against the following topologies (which means your algorithm does not need to account for them):
<ul>
<li>topologies with more than one link from <em><u>the same origin to the same</u> <u>destination</u></em> (multi-graphs)</li>
<li>topologies with portions of the network disconnected from each other</li>
</ul>
</li>
</ol>
(partitioned networks) o topologies that do not require intermediate steps (such as a topology with a single node)

<ul>
<li>topologies with a valid path between two indirectly linked nodes with no cycle with an actual total cost of ≤ -99 (topologies will respect that -99 is “negative infinity” for this project)</li>
</ul>
<h2><a name="_Toc12427"></a>Part 5: Correct Logs for Provided Topologies</h2>
Below are the correct final logs for the provided topologies. We are providing them to help you identify correct behavior with respect to negative cycles and the assumptions in the instructions. <strong><em>We are only providing the final round; each topology should produce at least 2 rounds of output. </em></strong>

SimpleTopo:

A:A0,C3,B1,D3 B:A1,C2,B0,D2 C:A3,C0,B2,D0 D:A3,C0,B2,D0 E:A2,C-1,B1,E0,D-1

&nbsp;

SingleLoopTopo:

A:A0,C16,B6,E6,D5 B:A2,C10,B0,E0,D7 C:C0 D:A3,C11,B1,E1,D0 E:A2,C10,B0,E0,D7

&nbsp;

SimpleNegativeCycle:

AA:AA0,CC-99,AB0,AE-1,AD-2 AB:AA-1,CC-99,AB0,AE-2,AD-3 AD:AA1,CC-99,AB2,AE1,AD0 AE:AA0,CC-99,AB1,AE0,AD-2 CC:CC0,AA-1,AB0,AE-2,AD-3

&nbsp;

ComplexTopo:

ATT:TWC-99,GSAT-8,UGA-99,ATT0,VZ-3,CMCT-99,VONA-11 CMCT:TWC-99,GSAT-7,UGA-99,ATT1,VZ-2,CMCT0,VONA-10 DRPA:TWC-99,GT-1,GSAT5,UGA-99,PTGN1,OSU1,ATT13,VONA2,EGLN1,VZ10,DRPA0,CMCT-99,UC-1 EGLN:TWC-99,GT-2,GSAT5,UGA-99,PTGN0,OSU2,ATT13,VONA3,EGLN0,VZ11,DRPA1,CMCT-99,UC-2 GSAT:TWC-99,GSAT0,UGA-99,ATT7,VZ5,CMCT-99,VONA-3 GT:TWC-99,GT0,GSAT7,UGA99,PTGN2,OSU0,ATT15,VONA5,EGLN2,VZ13,DRPA3,CMCT-99,UC0 OSU:TWC-99,GT0,GSAT7,UGA99,PTGN2,OSU0,ATT15,VONA5,EGLN2,VZ13,DRPA3,CMCT-99,UC0 PTGN:TWC-99,GT-1,GSAT5,UGA-99,PTGN0,OSU1,ATT13,VONA3,EGLN1,VZ11,DRPA2,CMCT-99,UC-1 TWC:TWC0,GSAT-7,UGA-99,ATT1,VZ-2,CMCT-99,VONA-10 UC:TWC-99,GT0,GSAT7,UGA99,PTGN2,OSU0,ATT15,VONA5,EGLN2,VZ13,DRPA3,CMCT-99,UC0 UGA:TWC-99,GSAT42,UGA0,ATT50,VZ47,CMCT-99,VONA39 VONA:TWC-99,GSAT2,UGA-99,ATT10,VZ8,CMCT-99,VONA0 VZ:TWC-99,GSAT-6,UGA-99,ATT2,VZ0,CMCT-99,VONA-9

<h2><a name="_Toc12428"></a>Part 6: Spirit of the Project</h2>
The goal of this project is to implement a simplified version of a network protocol using a distributed algorithm. This means that your algorithm should be implemented at the network node level. Each network node only knows its internal state, and the information passed to it by its direct neighbors. Declaring global variables will be a violation of the spirit of the project.

The skeleton code we provide you runs a simulation of the larger network topology. For simplicity, the Node class defines a link to the overall topology. This means it is possible using the provided code for one Node to access another Node’s internal state. <strong>This goes against the spirit of the project and is not permitted. </strong>If you have questions about whether your code is accessing data it should not, please ask on Ed Discussion or during office hours!

You should not use any global variables for managing any data relating to the Nodes. However, you may use a global variable as a setting. I.E.: NEGATIVE_INFINITY = -99

&nbsp;
