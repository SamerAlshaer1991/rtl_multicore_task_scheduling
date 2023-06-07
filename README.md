This project contains a genetic algorithm (GA) scheduler, and a brute force scheduler implementation designed to optimize task scheduling in embedded real-time systems. The program generates a directed acyclic graph of jobs, with each job having unique attributes, and aims to find an optimal sequence of jobs that minimizes total execution time and prioritizes crucial tasks. This system is built using Python and extensively uses the NetworkX library to model the task graph.

**Table of Contents**
Installation
Usage
Code Overview
Job and Platform Models
Genetic Algorithm Scheduler
Parallelized Version
Discord Community
License


**Installation**
TODO: Instructions on how to install and setup your software

**Usage**
TODO: Instructions on how to use your software

**Code Overview**
Job and Platform Models
The code generates a random directed acyclic graph (DAG) representing tasks or jobs to be executed. Each job has various attributes such as worst-case execution time (WCET), message size for data transfer, precedence relations, and more. The platform model is also defined in the code, with parameters including the number of processors, routers, and their connections. The platform model is designed to tackle distributed memory multi-core architectures aswell. 

**Genetic Algorithm Scheduler**
The genetic algorithm scheduler is the main component of the code. It starts by generating an initial population of sequences (also known as chromosomes), each representing a unique scheduling of jobs. The fitness of each chromosome is evaluated based on a fitness function, which gives higher scores to sequences that lead to shorter total execution times and honor priority constraints. The genetic algorithm then uses selection, crossover, and mutation operations to evolve the population over generations and find an optimal solution.

**Parallelized Version**
A parallelized version of the genetic algorithm scheduler is also included in the code. It uses Python's concurrent.futures library to evaluate the fitness of chromosomes in parallel, leading to a significant speedup in execution time on multi-core systems.

**Discord Community**
Join our Discord server to discuss this project, ask questions, and collaborate with other community members.

**License**
TODO: Your license details here

Please replace the "TODO" parts with information specific to your project. For instance, under the Installation and Usage sections, you would provide step-by-step instructions on how to get your project up and running.

The Discord link provided is a pseudo link, please replace it with your actual Discord invite link.

In the License section, you would include information about the type of license that governs the use and distribution of your project. Common licenses for open-source projects include MIT, Apache 2.0, and GPL.
