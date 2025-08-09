# Quantum-walks-and-monte-carlo
The simulation of the quantum galton box, [Universal statistical simulator](https://arxiv.org/pdf/2202.01735) for **Womanium and wiser project 2025**, Designed by **naval nuclear laboratory**


Project Name: Quantum walks and Monte carlo 

Team Name : Sneha Sharma 

Wiser enrollment : gst-YiEthrSCOPBdFzi

**Summary:** 

The  following project is designed by the naval nuclear laboratory as a Womanium and Wiser quantum projects 2025. 

In this project we build a circuit for Quantum galton board which is a type of monte carlo problem. This project explores how quantum circuits can stimulate complex systems via a galton box style monte carlo problem.  This is highly relevant to high dimensional challenges like particle transport and quantum systems. 
In this project we replicate the approach of [Universal statistical simulator](https://arxiv.org/pdf/2202.01735) to build a quantum circuit for the N layer Quantum galton board such that it yields the binomial distribution, exponential distribution, and hadamard walks.


The circuit is built by using the set of controlled swap and controlled not gates, these represent the peg. The 0th qubit acts as a controlled qubit, from which all the swaps are controlled, we apply hadamard gate or the rotation gates on the basis of the distribution we want to acquire on this qubit. 


The not gate is applied to the middle qubit of remaining qubits. This will act as a ball, swapping in the quantum galton board 


The other reset is applied at the end of each layer to prevent the biasing. Instead for biased quantum circuits or to get desired distribution we can replace the hadamard with rotation gates. 



Challenge deliverables:


**Review the paper, and any related resources to learn how to implement quantum Galton boards. Prepare a summary of your understanding in a well structured 2-pager document.**  

The two page review of Universal Statistical Simulator is submitted [here](https://github.com/snehafzd/Quantum-walks-and-monte-carlo/blob/main/Qunatum%20galton%20board/Summary%20of%20quantum%20Simulator.pdf). 

**Using the 1- and 2-layer Galton Box code as a starting point, write a general algorithm that generates a circuit for any number of layers. Run and verify that the output is a Gaussian distribution. You may use any quantum SDK and platform for your implementation.**

In [code](https://github.com/snehafzd/Quantum-walks-and-monte-carlo/blob/main/Qunatum%20galton%20board/Quantum%20galton%20board.ipynb), we first follow the universal gate simulator to build a 1 layer and 2 layer circuit. For n Layers, we generate a for loop over controlled  swap and control not  gate such that it will follow triangle number. We use 

$no. of qubits =one ball qubit +one control qubit+qubit above ball +qubit below ball$

$no. of qubit = 2+ 2*layers$

We run a circuit for 18 qubits, we are getting a gaussian curve. Except an anomaly at |0>

**Modify the function so that it obtains a different target distribution. Use a noiseless all-to-all sampler:**

**Exponential distribution**

For this we replace the hadamard applied on the 0th qubit with the Rotation gate on x-axis with angle pi/4.This yields a perfect exponential distribution with minor anomaly at |0>

**Hadamard quantum walk**

To achieve a Hadamard walk, I removed all the Controlled swaps and change the controlled qubits of Cnot gate such that it will create superposition.

 we get desirable hadamard walk with some abnormality. The hadamard walk distribution we get is a more spread out distribution and shows a lower bound around origin. It shows asymmetry.
