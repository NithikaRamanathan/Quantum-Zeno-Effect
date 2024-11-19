# Quantum-Zeno-Effect

## Introduction
The Zeno paradox was created by the ancient Greek philosopher Zeno of Elea, who said that if you shoot an arrow at the target, then at any given moment in time, the arrow is motionless, and therefore the arrow should not be able to move at all. This principle was eventually applied to quantum mechanics in what has been called the Quantum Zeno Effect. This effect says that when you continuously observe a quantum system, you can stop it from evolving and “freeze” it in its original state. 

![Arrow Frozen in Time](https://images.ctfassets.net/i1dyhzbyi8ad/2F5yvi7fCCVMrGvmWBrTK3/ead58830a6088ec736490f93fba3fc33/zeno_arrow.svg) 

This is because in quantum mechanics, measuring a quantum system destroys the superposition of the system, which means it forces the system to collapse into one state (0 or 1), instead of allowing it to remain a combination of both states. If you repeatedly force a quantum system to collapse into one particular state, you can reduce the probability that it will evolve into a different state. This probability decreases as the period of time between the measurements decreases.

## Our Code
The paper discusses a quantum circuit designed to demonstrate the Quantum Zeno Effect, where repeated measurements prevent the evolution of a qubit's state. The circuit consists of 10 steps involving a combination of U-gates and CNOT gates, controlled by the qubit in position q0. The U-gates rotate the qubit’s state by a phase of π/10 on the Bloch sphere, preserving the state through unitary operations, while the CNOT gates entangle q0 with target qubits (q1 to q0). At each step, the CNOT gate acts like a measurement, preventing the evolution of q0 by collapsing it into a single state. The final measurement after all steps shows that most qubits remain in the 0 state, consistent with the Quantum Zeno Effect. If you look through our code, you can see the visualization of the circuit, created using the q_evolve.draw("mpl") function, which highlights how the repeated application of CNOT gates stabilizes the qubit’s state.

## Credits
Modified code from: https://medium.com/qiskit/the-quantum-zeno-effect-from-motionless-arrows-to-entangled-freezers-e93beb7d52ae#:~:text=Here%20is%20an%20intuitive%20explanation,even%20multi%2Dqubit%20entangled%20states by Maria Violaris
