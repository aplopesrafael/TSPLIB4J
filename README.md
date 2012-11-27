A Java library for TSPLIB
===

### About TSPLIB4J:

[TSPLIB](http://comopt.ifi.uni-heidelberg.de/software/TSPLIB95/) is a collection of [traveling salesman](http://en.wikipedia.org/wiki/Travelling_salesman_problem), [vehicle routing](http://en.wikipedia.org/wiki/Vehicle_routing_problem), and [Hamiltonian cycle](http://en.wikipedia.org/wiki/Hamiltonian_path_problem) problem instances and a file format for storing instance data.  TSPLIB4J is a Java library for reading and processing TSPLIB instance data.  TSPLIB4J is licensed under the MIT license.

Prerequisites:

  - Java 1.5 or later
  - [JUnit 4](http://www.junit.org/) to run test cases
  
### Setup

First, create a data/ directory and the subfolders listed below.  Next, download any or all of the [TSPLIB problem instances](http://comopt.ifi.uni-heidelberg.de/software/TSPLIB95/) problem instances.  Finally, extract the problem instances into the appropriate folder.

    data/atsp
    data/hcp
    data/sop
    data/tsp
    data/vrp

### Traveling Salesman Problem:

    TSPProblem problem = new TSPProblem(new File("./data/tsp/pcb442.tsp"));
    problem.addTour(new File("./data/tsp/pcb442.opt.tour"));
    		
    for (Tour tour : problem.getTours()) {
    	System.out.println(tour.distance(problem));
    }
    
### Hamiltonian Cycle Problem:

    TSPProblem problem = new TSPProblem(new File("./data/hcp/alb1000.hcp"));
    problem.addTour(new File("./data/hcp/alb1000.opt.tour"));
    
    for (Tour tour : problem.getTours()) {
    	System.out.println(tour.isHamiltonianCycle(problem));
    }
    
### Displaying Solutions

    TSPProblem problem = new TSPProblem(new File("./data/tsp/gr120.tsp"));
    problem.addTour(new File("./data/tsp/gr120.opt.tour"));
    
    TSPPanel panel = new TSPPanel(problem);
    panel.displayTour(problem.getTours().get(0), Color.RED);
		
    JFrame frame = new JFrame(problem.getName());
    frame.getContentPane().setLayout(new BorderLayout());
    frame.getContentPane().add(panel, BorderLayout.CENTER);
    frame.setDefaultCloseOperation(JFrame.DISPOSE_ON_CLOSE);
    frame.setSize(500, 400);
    frame.setLocationRelativeTo(null);
    frame.setVisible(true);


Other Open Source Libraries
---
  - [MOEA Framework](http://www.moeaframework.org)
  - [DGantt](http://sourceforge.net/projects/dgantt/)
