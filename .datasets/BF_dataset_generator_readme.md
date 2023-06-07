# Dataset Generator
This code generates a dataset by simulating the scheduling of jobs on a platform model. It consists of several functions and steps to create and schedule jobs on a platform. Let's break down each part of the code and describe its functionality.

# Function Definitions
The code begins by defining several functions that are used throughout the simulation. These functions include:

### comm_cost(route, message_size): Calculates the communication cost based on the route and message size.
### Extract_Highest_Priority(jobs, Ready_Jobs): Extracts the job with the highest priority from the list of ready jobs.
### traffic_control_reserve(Injection, path, message_size, path_cost, overwrite): Simulates traffic control and reserves time slots for message transmission.
### check_collision(Current_Router, Current_Router_start, Current_Router_end, overwrite): Checks for collisions and resolves them by adjusting start and end times.
### find_path(connections, start_node, end_node): Finds a path between two nodes in a platform model using Breadth-First Search (BFS).
### dict_to_dataframe(dictionary): Converts a dictionary into a Pandas DataFrame.
### Schedule(jobs, routes, end_systems, messages, links): Performs the scheduling of jobs on the platform model.
### calculate_makespan(args): Calculates the makespan for a given set of priority and processor assignments.
### These functions are utilized during the simulation to calculate costs, assign priorities, allocate time slots, find paths, and schedule jobs.

## Platform Model and Job Generation
The code proceeds to define the parameters for the platform model. This includes the number of processors, routers, and the connections between them. The routes between end systems are computed using the find_path function and stored in a dictionary called routes.

Next, the code generates a random acyclic Directed graph to represent the jobs. The number of jobs is specified, and the connectivity between jobs is determined randomly. The worst-case execution time (wcet) and message sizes for the jobs are randomized within given ranges. The precedence relationships between jobs are determined based on the graph.

The job and message dictionaries are created to store the attributes and information about each job and the messages exchanged between jobs.

## Scheduling and Solution Generation
The main part of the code involves generating solutions for a specified number of samples. The process includes the following steps:

Initialize the sample number and a flag variable (generate_solution) to control the generation of solutions.

Inside a loop, the code uses a ThreadPoolExecutor to parallelize the calculation of makespan for different combinations of priority and processor assignments. This is done to find the best solution in terms of makespan.

The best solution found so far is stored in a list (best_solution), which includes the makespan and the corresponding job assignments.

Once the best solution is found, it is saved as a pickle file with a unique name based on the sample number.

The generate_solution flag is set to 1 to indicate that a solution has been generated.

The sample number is incremented, and the loop continues until the desired number of samples is generated.

## Summary
This code provides a flexible framework for generating datasets by simulating the scheduling of jobs on a platform model. It allows for customization of various parameters such as the number of jobs, platform topology, job attributes, and solution generation techniques. The generated datasets can be used for various purposes, such as evaluating scheduling algorithms, analyzing performance, and benchmarking optimization methods.
