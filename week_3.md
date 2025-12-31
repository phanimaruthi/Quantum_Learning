# Week 03 – Quantum Algorithms and Structured Speedups

This week focused on understanding **why and when quantum algorithms outperform classical ones**. The emphasis was not on memorizing algorithms, but on identifying the *common mechanisms* behind quantum speedups such as interference, hidden symmetry, and Hamiltonian evolution.

---

**Simon’s Problem and Hidden Symmetry**

- Simon’s problem introduces a black-box function with a hidden XOR symmetry.
- Classically, finding this hidden string requires an exponential number of queries.
- Quantumly, the algorithm:
  - Prepares a superposition of all inputs
  - Queries the oracle once per run
  - Measures outcomes that satisfy linear constraints orthogonal to the hidden string
- Repeating the process gives enough linear equations to recover the secret efficiently.

Key insight:
- The speedup comes from **quantum interference encoding global structure**, not from parallel brute force.

---

**Hidden Subgroup Problem (HSP)**

- HSP generalizes Simon’s problem to arbitrary groups.
- The oracle is constant on cosets of an unknown subgroup.
- Quantum algorithms:
  - Prepare coset states
  - Measure them in appropriate bases to reveal subgroup structure
- Many major algorithms (Simon’s, Shor’s) are special cases of HSP.

Why this matters:
- Quantum advantage often comes from **extracting hidden algebraic structure**, not raw computation.

---

**Discrete-Time Quantum Walks**

- A naive quantum version of a random walk is not unitary and breaks reversibility.
- The solution is to introduce a **coin register**:
  - Stores direction or memory
  - Ensures unitary evolution
- Quantum walks exploit interference to bias movement toward useful regions of the state space.

---

**Szegedy Quantum Walk Construction**

- Szegedy’s method converts a classical Markov chain into a quantum walk.
- It uses:
  - Reflections about a subspace defined by the transition matrix
  - A swap operator to enforce reversibility
- The resulting unitary mirrors the structure of the classical walk.

Key advantage:
- Faster mixing and detection of marked states due to interference.

---

**Quantum Walk Search and Complexity**

- The goal is to detect whether a marked set exists in a graph.
- Classically, complexity depends on the hitting time and spectral gap.
- Quantumly:
  - Phase estimation is used to detect nontrivial eigenphases
  - This yields a **quadratic speedup** over classical search

Important limitation:
- If the spectral gap is very small, both classical and quantum methods slow down.

---

**Quantum Walk Applications**

- Unstructured search:
  - Reduces to Grover’s algorithm
  - Achieves optimal quadratic speedup
- Element distinctness:
  - Exploits structure using a quantum walk on a Hamming graph
  - Achieves better-than-Grover performance
- Core lesson:
  - Structure enables speedups beyond generic search.

---

**Putting Week 3 Together**

- Quantum speedups are not universal.
- They arise when problems have:
  - Hidden symmetry
  - Graph structure
  - Favorable spectral properties
- Algorithms are engines built from:
  - Interference
  - Measurement
  - Structured state preparation

---

**Summary**

Week 3 clarified that quantum algorithms succeed by **encoding global problem structure into quantum states**, allowing interference and measurement to extract information that is inaccessible classically.
