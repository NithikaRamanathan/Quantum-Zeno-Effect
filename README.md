# Quantum-Zeno-Effect

## Introduction

#### Background
The Zeno paradox was created by the ancient Greek philosopher Zeno of Elea, who said that if you shoot an arrow at the target, then at any given moment in time, the arrow is motionless, and therefore the arrow should not be able to move at all. This principle was eventually applied to quantum mechanics in what has been called the Quantum Zeno Effect. This effect says that when you continuously observe a quantum system, you can stop it from evolving and “freeze” it in its original state. 

![Arrow Frozen in Time](https://images.ctfassets.net/i1dyhzbyi8ad/2F5yvi7fCCVMrGvmWBrTK3/ead58830a6088ec736490f93fba3fc33/zeno_arrow.svg) 

This is because in quantum mechanics, measuring a quantum system destroys the superposition of the system, which means it forces the system to collapse into one state (0 or 1), instead of allowing it to remain a combination of both states. If you repeatedly force a quantum system to collapse into one particular state, you can reduce the probability that it will evolve into a different state. This probability decreases as the period of time between the measurements decreases.

#### Project Purpose
The purpose of our project is to be able to simulate the Quantum Zeno Effect on a quantum computer by leveraging strong coupling between qubits instead of traditional, non-unitary measurements that result in wave function collapse. The QZE typically relies on frequent projective measurements that "freeze" the quantum state by repeatedly collapsing it, but in quantum computing, unitary operations are standard, and measurements usually occur only at the end of a computation, which makes simulating the QZE simulation hard on a quantum computer. To work around this limitation, we use a strongly coupled external system to mimic the effect of measurements. The approach relies on a mathematical framework in which frequent interactions with an external system simulate the measurement process. If a unitary operator repeatedly interacts with a Hamiltonian, the system behaves as though it is subject to a "Zeno Hamiltonian" HZ. It represents the Hamiltonian projected onto the invariant subspaces of U.


## Methods 
We use the IBM software kit Qiskit to simulate the behavior of a qubit and model the Quantum Zeno Effect. All quantum circuits are executed using a classical simulation backend in Google Colab. For our quantum algorithm and circuit, we begin by defining a quantum register (qr) and a classical register (cr). At each time step, the qubit’s state is rotated by a unitary gate (UGate). In the case of the Zeno effect simulation, frequent measurements are applied to simulate the collapse of the wave function. The key modification to simulate the Zeno effect is the strong coupling between the qubit and an external system, which interacts with the qubit at each time step. The system behaves as if it is subject to a "Zeno Hamiltonian" under these frequent interactions.

![Circuit Diagram](https://github.com/user-attachments/assets/9d141d76-b6f9-4b11-8571-65b44b0038c9)


## Dataset and Preprocessing
The data is the state of the qubits and the results of the measurements over time. No preprocessing techniques are applied, but instead some of the processing steps include evolving the qubit’s state using unitary gates, measuring the probability of certain states at each time step, and repeating this process for multiple time steps to determine the average probability. 


## Our Code
The paper discusses a quantum circuit designed to demonstrate the Quantum Zeno Effect, where repeated measurements prevent the evolution of a qubit's state. The circuit consists of 10 steps involving a combination of U-gates and CNOT gates, controlled by the qubit in position q0. The U-gates rotate the qubit’s state by a phase of π/10 on the Bloch sphere, preserving the state through unitary operations, while the CNOT gates entangle q0 with target qubits (q1 to q0). At each step, the CNOT gate acts like a measurement, preventing the evolution of q0 by collapsing it into a single state. The final measurement after all steps shows that most qubits remain in the 0 state, consistent with the Quantum Zeno Effect. If you look through our code, you can see the visualization of the circuit, created using the q_evolve.draw("mpl") function, which highlights how the repeated application of CNOT gates stabilizes the qubit’s state.


## Results
The results depicted in the bar graph show that the majority of qubits remained in the 0 state. This is representative of the the Quantum Zeno Effect because as more measurements are taken, the state of the qubit should be collapsed into one state.

![Bar Graph of Qubit States](https://github.com/user-attachments/assets/7da9de81-9299-40c7-814f-997ca10c020c)

The graph of the evolution of the state of the qubit with and without the Zeno Effect demonstrates that without repeated measurements, the qubit's state evolves from 0 to 1 with each rotation gate. With the measurements, the qubit is essentially frozen at 0, even with the rotation gates being applied. The freezing of the qubit's state with repeated measurements indicates that the Quantum Zeno Effect is being applied here.

![Graph of Evolution of State With and Without Zeno Effect](https://github.com/user-attachments/assets/b38894c3-c7ad-4f1a-a6b0-c3939ef43bbd)


## Conclusion
We were able to recreate the results of the paper to show that you can create a Zeno-like effect in a quantum system by continuous coupling to external qubits using the CNOT gate. Studying the quantum Zeno effect is important because it could help solve the problem of quantum decoherence, which is when quantum systems lose coherence by interacting with their environment. It is possible that the quantum zeno effect could be utilized to reduce decoherence and keep qubits in the state we want them in for as long as possilbe Potential future research could include looking at whcich other gates have similar effects as the CNOT gate did in our experiment, and finding how effective each one is. It could also include using the QZE on a system with more than one qubit.


## Credits
Modified code from: https://medium.com/qiskit/the-quantum-zeno-effect-from-motionless-arrows-to-entangled-freezers-e93beb7d52ae#:~:text=Here%20is%20an%20intuitive%20explanation,even%20multi%2Dqubit%20entangled%20states by Maria Violaris
