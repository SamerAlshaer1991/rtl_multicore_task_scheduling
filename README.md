# Task Scheduling in Distributed Memory Multi-core Real-Time Embedded Systems Simulator

This project contains a genetic algorithm (GA) scheduler, and a brute force scheduler implementation designed to optimize task scheduling in embedded real-time systems. The program generates a directed acyclic graph of jobs, with each job having unique attributes, and aims to find an optimal sequence of jobs that minimizes total execution time and prioritizes crucial tasks. This system is built using Python and extensively uses the NetworkX library to model the task graph.

## Table of Contents

### 1. [Installation](#Installation)

### 2. [Usage](#Usage)

### 3. [Code Overview](#Code-Overview)

### 4. [Job and Platform Models](#Job-and-Platform-Models)

### 5. [Genetic Algorithm Scheduler](#Genetic-Algorithm-Scheduler)

### 6. [Parallelized Version](#Parallelized-Version)

### 7. [Discord Community](#Discord-Community)

### 8. [License](#License)


## Installation

TODO: Instructions on how to install and setup your software

## Usage

TODO: Instructions on how to use your software

## Code Overview

### Job and Platform Models

The code generates a random directed acyclic graph (DAG) representing tasks or jobs to be executed. Each job has various attributes such as worst-case execution time (WCET), message size for data transfer, precedence relations, and more. The platform model is also defined in the code, with parameters including the number of processors, routers, and their connections. The platform model is designed to tackle distributed memory multi-core architectures aswell. 

### Genetic Algorithm Scheduler

The genetic algorithm scheduler is the main component of the code. It starts by generating an initial population of sequences (also known as chromosomes), each representing a unique scheduling of jobs. The fitness of each chromosome is evaluated based on a fitness function, which gives higher scores to sequences that lead to shorter total execution times and honor priority constraints. The genetic algorithm then uses selection, crossover, and mutation operations to evolve the population over generations and find an optimal solution.

### Parallelized Version

A parallelized version of the genetic algorithm scheduler is also included in the code. It uses Python's concurrent.futures library to evaluate the fitness of chromosomes in parallel, leading to a significant speedup in execution time on multi-core systems.

## Discord Community

Join our [Discord Server](https://discord.gg/S9xYegQw) to discuss this project, ask questions, and collaborate with other community members

## License
This project is licensed under [Copyrights eu](https://www.copyright.info/copyright/IPSO20230606004845DPQ/).
This project is licensed under MIT license.
The License is a permissive open-source license that allows you to freely use, modify, and distribute this software for any purpose. It comes without any warranty or guarantee of fitness for any particular purpose. You are responsible for checking and complying with any additional licensing or attribution requirements based on the dependencies or libraries used in this project.

