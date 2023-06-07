# Dataset_generator_v4.ipynb

This script is used to generate datasets using a Genetic Algorithm (GA) scheduler combined with an application and platform model. It consists of two parts: the first part defines several functions and the platform model, and the second part implements the GA scheduler to generate datasets.

## Function Definitions:

### comm_cost(route, message_size): This function calculates the communication cost based on the route and message size.

### Extract_Highest_Priority(jobs, Ready_Jobs): This function extracts the job with the highest priority from the ready job list.

### traffic_control_reserve(Injection, path, message_size, path_cost, overwrite): This function calculates the delta cost (additional time) caused by traffic control and reserves the communication channels.

### check_collision(Current_Router, Current_Router_start, Current_Router_end, overwrite): This function checks for collisions in communication channel allocation and resolves them.

### find_path(connections, start_node, end_node):
This function uses Breadth-First Search to find the shortest path between two nodes in the platform model.

### generate_chromosome(jobs, end_systems):
This function generates a chromosome (schedule) by assigning priorities and processors to the jobs.

### fitness_function(chromo):
This function evaluates the fitness of a chromosome by using the Schedule function to generate a schedule and computing its makespan.

### generate_population(POPULATION_SIZE):
This function generates an initial population of chromosomes.

### selection(fitness_values, population):
This function performs selection on the population to select the fittest individuals.

### mutation(chromosome, mutation_rate):
This function applies mutation to a chromosome by randomly changing the assigned processor or swapping priorities between two jobs.

### dict_to_dataframe(dictionary):
This function converts a dictionary to a Pandas DataFrame.

### Schedule(jobs, routes, end_systems, messages, links):
This function generates a schedule for the jobs using the platform model and calculates the makespan.

## Part 1: Platform Model and Job Generation:

This part initializes the platform model and generates random acyclic Directed Graphs for the jobs. It includes the following steps:

Import the required libraries: random, networkx, matplotlib.pyplot, pandas, numpy, copy, multiprocessing, concurrent.futures, and pickle.
Define the platform model parameters such as the number of processors, number of routers, and links.
Create the routes dictionary using the find_path function to find the shortest routes between processors.
Generate random acyclic Directed Graphs for the jobs using the nx.gnp_random_graph function from the networkx library.
Randomize the job attributes such as Worst Case Execution Time (WCET) and message sizes.
Create the jobs dictionary and messages dictionary using the generated job attributes and graph precedence information.
Define the GA scheduler parameters such as population size, elite size, mutation rate, maximum generations, and number of threads.
Generate an initial population of chromosomes using the generate_population function.

## Part 2: Genetic Algorithm Scheduler:

This part implements the GA scheduler to generate datasets. It includes the following steps:

Define variables for the maximum fitness value, break counter, and sample number.
Initialize an executor with the specified number of threads.
Run the GA scheduler for the specified maximum number of generations.
Evaluate the fitness of each chromosome in the population using parallel processing.
Select the fittest individuals for reproduction through selection.
Create offspring by applying mutation to the selected individuals.
Add the elite individuals from the previous generation to the new population.
Update the population for the next generation.
Store the best gene (chromosome) and its fitness value if it surpasses the current maximum fitness value.
Repeat the above steps until the break counter reaches the maximum value or the desired number of samples is generated.
Save each best gene as a pickle file to generate the datasets.
This script can be used to generate datasets for various applications by adjusting the platform model parameters, number of jobs, and GA scheduler parameters.

Please note that the descriptions provided here are based on the understanding of the code provided. It's important to review and validate the code logic and functionality for specific use cases.
