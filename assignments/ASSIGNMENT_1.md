# Assignment 1 - Quantum Computing

***
&emsp;

## 1. Differentiate between Digital Computer and Quantum Computer

| Aspect | Digital Computer | Quantum Computer |
|--------|------------------|------------------|
| **Basic Unit** | Bit (0 or 1) | Qubit (superposition of 0 and 1) |
| **Information Storage** | Classical bits store definite values | Qubits can exist in superposition states |
| **Processing** | Sequential/parallel classical logic | Quantum parallelism using superposition |
| **Operations** | Boolean logic gates (AND, OR, NOT) | Quantum gates (Hadamard, CNOT, Pauli) |
| **Entanglement** | No concept of entanglement | Qubits can be quantum entangled |
| **Error Handling** | Classical error correction codes | Quantum error correction required |
| **Measurement** | Direct readout of bit values | Probabilistic measurement collapses state |
| **Scalability** | Exponential resource growth | Exponential computational advantage for specific problems |
| **Applications** | General-purpose computing | Specialized for cryptography, optimization, simulation |


***
&emsp;

## 2. How quantum information is used in quantum computing?

Quantum information leverages fundamental quantum mechanical principles to process and store data in ways impossible with classical systems:

**Key Principles:**
- **Superposition**: Qubits can exist in multiple states simultaneously, enabling parallel computation paths
- **Entanglement**: Quantum correlations between qubits create computational dependencies that classical systems cannot replicate
- **Interference**: Quantum amplitudes can interfere constructively or destructively to enhance correct solutions

**Applications in Quantum Computing:**

- **Quantum Algorithms**: Algorithms like Shor's (factoring) and Grover's (search) use quantum properties for exponential speedups
- **Quantum Communication**: Secure communication using quantum key distribution  
- **Quantum Simulation**: Modeling complex quantum systems that classical computers can't handle
- **Quantum Machine Learning**: Using superposition and entanglement to enhance pattern recognition


***
&emsp;

## 3. What is Shannon Entropy?

Shannon Entropy quantifies the uncertainty or information content in a probability distribution. For a discrete random variable X with possible outcomes $x_i$ and probabilities $p(x_i)$:

$$H(X) = -\sum_{i} p(x_i) \log_2 p(x_i)$$

**Properties:**
- Measured in bits when using base-2 logarithm
- $H(X) \geq 0$ with equality when X is deterministic
- Maximum entropy occurs for uniform distribution
- Represents average number of bits needed to encode information

**Examples:**
- **Fair coin flip**: $p(H) = p(T) = 0.5$ → $H(X) = 1$ bit (maximum uncertainty)
- **Biased coin**: $p(H) = 0.9, p(T) = 0.1$ → $H(X) ≈ 0.47$ bits (less uncertainty)
- **Certain outcome**: $p(H) = 1, p(T) = 0$ → $H(X) = 0$ bits (no uncertainty)

***
&emsp;

## 4. What is a qubit and how does it differ from a classical bit?

A **qubit** (quantum bit) is the fundamental unit of quantum information. Unlike classical bits, qubits can exist in a quantum superposition of both 0 and 1 states simultaneously, represented mathematically as:

$$|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$$

where α and β are complex probability amplitudes that determine the likelihood of measuring the qubit in state |0⟩ or |1⟩.

## Difference from classical bit

| Aspect | Classical Bit | Qubit |
|--------|---------------|-------|
| **State** | Binary: either 0 or 1 | Superposition: α\|0⟩ + β\|1⟩ |
| **State Space** | 2 possible states | Infinite states on Bloch sphere |
| **Measurement** | Deterministic | Probabilistic (\|α\|² and \|β\|²) |
| **Information Capacity** | 1 bit | Theoretically infinite (continuous α, β) |
| **Operations** | Can be irreversible | Must be unitary (reversible) |
| **Copying** | Can be copied perfectly | Cannot be cloned (No-cloning theorem) |
| **Processing** | Sequential logic gates | Parallel quantum operations |

## Key Quantum Properties

- **Superposition**: Qubits can be in multiple states simultaneously
- **Entanglement**: Qubits can be correlated in ways impossible classically
- **Interference**: Quantum states can interfere constructively or destructively
- **Measurement Collapse**: Observation forces the qubit into a definite state

***
&emsp;
 
## 5. Write the general mathematical form of a qubit

The general mathematical form of a qubit state is:

$$|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$$

Where:
- $\alpha, \beta \in \mathbb{C}$ are complex probability amplitudes
- $|0\rangle$ and $|1\rangle$ are computational basis states
- Normalization constraint: $|\alpha|^2 + |\beta|^2 = 1$

**Alternative representations:**

**Polar Form:**
$$|\psi\rangle = \cos\left(\frac{\theta}{2}\right)|0\rangle + e^{i\phi}\sin\left(\frac{\theta}{2}\right)|1\rangle$$

Where $\theta \in [0, \pi]$ is the polar angle and $\phi \in [0, 2\pi)$ is the azimuthal angle.

**Matrix Form:**
$$|\psi\rangle = \begin{pmatrix} \alpha \\ \beta \end{pmatrix}$$

Where $\theta \in [0, \pi]$ and $\phi \in [0, 2\pi)$ are spherical coordinates on the Bloch sphere.
 
***
&emsp;
 
## 6. Explain the concept of measurement in qubits. What happens after a measurement?

### The Concept of Measurement in Qubits

#### Qubit Fundamentals
A **qubit** exists in a **superposition state**: $|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$, where $\alpha$ and $\beta$ are complex probability amplitudes satisfying $|\alpha|^2 + |\beta|^2 = 1$.

#### How Measurement Works
Unlike classical bits, measuring a qubit is **probabilistic**. The **Born rule** governs this process:

- **Probability of measuring** $|0\rangle$: $P(0) = |\alpha|^2$
- **Probability of measuring** $|1\rangle$: $P(1) = |\beta|^2$

**Example:** For $|\psi\rangle = \frac{1}{\sqrt{3}}|0\rangle + \frac{\sqrt{2}}{3}|1\rangle$:
- $P(0) = \frac{1}{3}$, $P(1) = \frac{2}{3}$

#### Mathematical Framework
Measurement is described by **measurement operators** $M_m$:
- **Measurement probability**: $Pr(m) = \text{Tr}(M_m^\dagger M_m \rho)$
- **Post-measurement state**: $\rho' = \frac{M_m \rho M_m^\dagger}{\text{Tr}(M_m^\dagger M_m \rho)}$

#### Types of Measurements
1. **Projective Measurements**: Use projection operators $P$ where $P = P^\dagger$ and $P^2 = P$
2. **POVMs**: Use positive operators $E_m$ where $\sum_m E_m = I$, allowing for more general measurements including weak measurements

### What Happens After Measurement?

#### Wavefunction Collapse
Measurement causes **irreversible collapse** of the quantum state:

1. **Before**: Qubit in superposition $|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$
2. **After**: Qubit becomes exactly the measured state ($|0\rangle$ or $|1\rangle$)

#### Key Consequences
- **Information Loss**: Original amplitudes $\alpha$ and $\beta$ are **lost forever**
- **State Alteration**: The measurement fundamentally changes the quantum system
- **Irreversibility**: Cannot recover the pre-measurement superposition state

#### Practical Implications
- **Single measurement limitation**: Cannot determine original $\alpha$ and $\beta$ from one measurement
- **Quantum information destruction**: The act of measurement destroys quantum information
- **Classical outcome**: Always get a definite classical result (0 or 1)

### Example:

Think of a spinning coin in the air - it's neither heads nor tails but a superposition of both. The moment you catch it (measure), it becomes definitively heads or tails. The "spinning state" is gone forever, and you can't tell how fast it was spinning or its exact orientation before you caught it.

**Summary**: Qubit measurement is a probabilistic process governed by quantum amplitudes that irreversibly collapses superposition states into classical outcomes, destroying the original quantum information in the process.
 
***
&emsp;
 
## 7. What is the Bloch sphere and how does it represent a qubit?

![Bloch Sphere](https://cdn.mathpix.com/snip/images/npBLHRCyBL-OGDKyk9mLKxP4pV9wPqq9yWMBHLTwGHs.original.fullsize.png)



The Bloch sphere is a geometric representation of qubit states as points on a unit sphere in 3D space.

**Mathematical Representation:**
Any qubit state can be written as:
$$|\psi\rangle = \cos\left(\frac{\theta}{2}\right)|0\rangle + e^{i\phi}\sin\left(\frac{\theta}{2}\right)|1\rangle$$

**Sphere Coordinates:**
- **θ**: Polar angle (0 ≤ θ ≤ π)
- **φ**: Azimuthal angle (0 ≤ φ < 2π)

**Key Points:**
- **North Pole** (θ=0): |0⟩ state (classical "0")
- **South Pole** (θ=π): |1⟩ state (classical "1")  
- **Equator**: Equal superposition states like |+⟩ and |-⟩
- **Any point on surface**: Valid qubit state
- **Interior**: Invalid (non-normalized states)

**Properties:**
- Pure states lie on the surface
- Mixed states lie inside the sphere
- Antipodal points represent orthogonal states
- Great circles represent continuous quantum operations
 
***
&emsp;
 
## 8. What is the Hilbert space dimension of a system of n qubits?

The Hilbert space dimension of an n-qubit system is:

$$\text{Dimension} = 2^n$$

**Explanation:**
- Each qubit contributes a 2-dimensional complex vector space
- n qubits form a tensor product space: $(\mathbb{C}^2)^{\otimes n}$
- Total dimension: $\underbrace{2 \times 2 \times \cdots \times 2}_{n \text{ times}} = 2^n$

**Examples:**
- 1 qubit: $2^1 = 2$ dimensions
- 2 qubits: $2^2 = 4$ dimensions  
- 3 qubits: $2^3 = 8$ dimensions
- n qubits: $2^n$ dimensions

**Computational Basis:**
For n qubits, the computational basis consists of $2^n$ basis states:
$$\{|00...0\rangle, |00...1\rangle, |00...10\rangle, \ldots, |11...1\rangle\}$$
 
***
&emsp;
 
## 9. Explain the tensor product and how it applies to multiple qubits

**Tensor Product Definition:**
The tensor product (⊗) mathematically combines separate quantum systems into a single composite system. It preserves all information about individual subsystems while creating new possibilities for entanglement and correlation.

**For Vectors:**
Given two single-qubit states represented as column vectors:
$$|a\rangle = \begin{pmatrix} a_1 \\ a_2 \end{pmatrix} \text{ and } |b\rangle = \begin{pmatrix} b_1 \\ b_2 \end{pmatrix}$$

Their tensor product creates a four-dimensional vector:
$$|a\rangle \otimes |b\rangle = \begin{pmatrix} a_1 b_1 \\ a_1 b_2 \\ a_2 b_1 \\ a_2 b_2 \end{pmatrix}$$

This expansion follows the Kronecker product rule, where each element of the first vector multiplies the entire second vector.

**Multiple Qubit Systems:**
For two arbitrary qubits in superposition:
- $|\psi_1\rangle = \alpha_1|0\rangle + \beta_1|1\rangle$ (first qubit)
- $|\psi_2\rangle = \alpha_2|0\rangle + \beta_2|1\rangle$ (second qubit)

Their tensor product expands to:
$$|\psi_1\rangle \otimes |\psi_2\rangle = \alpha_1\alpha_2|00\rangle + \alpha_1\beta_2|01\rangle + \beta_1\alpha_2|10\rangle + \beta_1\beta_2|11\rangle$$

This creates a four-dimensional Hilbert space where each computational basis state corresponds to a specific combination of individual qubit states.

**Essential Properties:**
1. **Bilinearity**: The tensor product is linear in each argument:
   $$(a|u\rangle + b|v\rangle) \otimes |w\rangle = a(|u\rangle \otimes |w\rangle) + b(|v\rangle \otimes |w\rangle)$$

2. **Associativity**: Grouping doesn't matter for multiple systems:
   $$(|a\rangle \otimes |b\rangle) \otimes |c\rangle = |a\rangle \otimes (|b\rangle \otimes |c\rangle) = |a\rangle \otimes |b\rangle \otimes |c\rangle$$

3. **Non-commutativity**: Order matters in quantum systems:
   $$|a\rangle \otimes |b\rangle \neq |b\rangle \otimes |a\rangle$$ (in general)

4. **Dimension scaling**: n qubits create a $2^n$-dimensional Hilbert space

**Notation Shortcuts:**
The tensor product symbol is often omitted for brevity:
- $|a\rangle \otimes |b\rangle = |a\rangle|b\rangle = |ab\rangle$
- $|0\rangle \otimes |1\rangle = |01\rangle$
- Three qubits: $|0\rangle \otimes |1\rangle \otimes |0\rangle = |010\rangle$

**Practical Applications:**
The tensor product enables quantum algorithms by allowing operations on multiple qubits simultaneously, creating entangled states impossible to describe as simple products of individual qubits, and providing the mathematical framework for quantum parallelism where n qubits can represent $2^n$ classical states simultaneously in superposition.
 
***
&emsp;
 
## 10. Define a vector space in the context of quantum computing

In quantum computing, a **vector space** is the mathematical framework that describes the set of all possible states a quantum system can occupy. It's a stage where the drama of quantum mechanics unfolds.

Specifically, it's a **complex vector space**, as quantum states are represented by vectors with complex number entries.

***

### The Core Components

For a set $V$ to be a vector space used in quantum computing, it must be defined over the field of complex numbers $\mathbb{C}$ and support two fundamental operations:

1.  **Vector Addition:** You can add any two quantum states (vectors, or **kets** like $|\psi\rangle$ and $|\phi\rangle$) to get another valid quantum state within the same space: $|\chi\rangle = |\psi\rangle + |\phi\rangle$. This is the mathematical basis for the **superposition principle**.
2.  **Scalar Multiplication:** You can multiply any quantum state $|\psi\rangle$ by a complex number $\alpha \in \mathbb{C}$ to get a new valid state: $|\phi\rangle = \alpha|\psi\rangle$. The scalar $\alpha$ acts as a "weight" or probability amplitude for that state in a superposition.

These operations must satisfy a list of axioms (like commutativity and associativity) that ensure the space is mathematically consistent.

***

### Key Examples

* **A Single Qubit ($\mathbb{C}^2$):** The state of a single qubit is described by a vector in the two-dimensional complex vector space, $\mathbb{C}^2$. This space is spanned by two basis vectors, the **computational basis states**:
    $$
    |0\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix} \quad \text{and} \quad |1\rangle = \begin{pmatrix} 0 \\ 1 \end{pmatrix}
    $$
    Any state of the qubit is a linear combination (superposition) of these basis states: $|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$.

* **An n-Qubit System ($\mathbb{C}^{2^n}$):** The state of an n-qubit system lives in a much larger, $2^n$-dimensional complex vector space. This space is formed by the tensor product of the individual qubit spaces. For example, a 2-qubit system is described by a vector in $\mathbb{C}^4$, spanned by the four basis states: $\{|00\rangle, |01\rangle, |10\rangle, |11\rangle\}$.

***

### Physical Interpretation and Significance

The vector space structure is not just mathematical formalism; it's deeply tied to the physics of quantum systems.

* **State Representation:** Vectors (kets) directly represent the possible states of a quantum system.
* **Superposition:** The ability to add vectors (linear combinations) mathematically represents the physical phenomenon of superposition.
* **Measurement:** An **inner product** is defined on the space, allowing us to calculate the probability of one state collapsing to another upon measurement. The probability of measuring state $|\phi\rangle$ from a system in state $|\psi\rangle$ is given by $|\langle\phi|\psi\rangle|^2$.
* **Quantum Evolution:** Quantum operations (gates) are **unitary transformations** on this vector space. These are essentially rotations of the state vector, evolving it to a new state while preserving its length (i.e., conserving probability).
 
***
&emsp;
 
## 11. What are the axioms of a vector space?

A vector space V over field F must satisfy eight axioms:

**Addition Axioms:**
1. **Closure**: $\forall u, v \in V: u + v \in V$
2. **Associativity**: $\forall u, v, w \in V: (u + v) + w = u + (v + w)$
3. **Commutativity**: $\forall u, v \in V: u + v = v + u$
4. **Identity Element**: $\exists 0 \in V$ such that $\forall v \in V: v + 0 = v$
5. **Inverse Element**: $\forall v \in V, \exists (-v) \in V$ such that $v + (-v) = 0$

**Scalar Multiplication Axioms:**
1. **Closure**: $\forall a \in F, v \in V: av \in V$
2. **Associativity**: $\forall a, b \in F, v \in V: a(bv) = (ab)v$
3. **Distributivity**: 
   - $\forall a \in F, u, v \in V: a(u + v) = au + av$
   - $\forall a, b \in F, v \in V: (a + b)v = av + bv$

**Additional Property:**
- **Multiplicative Identity**: $\forall v \in V: 1v = v$ where 1 is the multiplicative identity in F
 
***
&emsp;
 
## 12. What is meant by a linear combination of quantum states?

A **linear combination** of quantum states is an expression of the form:

$$|\psi\rangle = c_1|\psi_1\rangle + c_2|\psi_2\rangle + \cdots + c_n|\psi_n\rangle$$

Where:
- $c_i \in \mathbb{C}$ are complex coefficients (probability amplitudes)
- $|\psi_i\rangle$ are quantum states (vectors in Hilbert space)
- Result $|\psi\rangle$ is also a valid quantum state

**Properties:**
1. **Superposition Principle**: Any linear combination of valid states is a valid state
2. **Normalization**: For physical states, $\sum_i |c_i|^2 = 1$
3. **Interference**: Coefficients can interfere constructively or destructively

**Examples:**

**Bell State:**
$$|\Phi^+\rangle = \frac{1}{\sqrt{2}}(|00\rangle + |11\rangle)$$

**General Single Qubit:**
$$|\psi\rangle = \alpha|0\rangle + \beta|1\rangle \text{ where } |\alpha|^2 + |\beta|^2 = 1$$

**Physical Interpretation:**
Linear combinations represent quantum superposition, enabling quantum parallelism and interference effects crucial for quantum algorithms.
 
***
&emsp;
 
## 13. Define a Hilbert space. What are its essential properties?

A **Hilbert space** H is a complete inner product space - a vector space equipped with an inner product that is complete with respect to the norm induced by the inner product.

**Formal Definition:**
H is a vector space over $\mathbb{C}$ with inner product $\langle \cdot, \cdot \rangle: H \times H \rightarrow \mathbb{C}$ that is complete.

**Essential Properties:**

**1. Inner Product Properties:**
- **Conjugate Symmetry**: $\langle u, v \rangle = \overline{\langle v, u \rangle}$
- **Linearity in First Argument**: $\langle au + bv, w \rangle = a\langle u, w \rangle + b\langle v, w \rangle$
- **Positive Definiteness**: $\langle v, v \rangle \geq 0$ with equality iff $v = 0$

**2. Norm Properties:**
- **Induced Norm**: $||v|| = \sqrt{\langle v, v \rangle}$
- **Cauchy-Schwarz Inequality**: $|\langle u, v \rangle| \leq ||u|| \cdot ||v||$
- **Triangle Inequality**: $||u + v|| \leq ||u|| + ||v||$

**3. Completeness:**
- Every Cauchy sequence converges to an element in H
- No "gaps" in the space

**4. Additional Properties:**
- **Parallelogram Law**: $||u + v||^2 + ||u - v||^2 = 2(||u||^2 + ||v||^2)$
- **Polarization Identity**: Recovers inner product from norm
- **Orthogonal Projection**: Unique closest point in subspaces

**Quantum Computing Context:**
- Quantum states are unit vectors in Hilbert space
- Observable measurements correspond to orthogonal projections
- Time evolution is unitary (preserves inner products)
 
***
&emsp;
 
## 14. What is a spanning set in a vector space?

A **spanning set** S of a vector space V is a subset of V such that every vector in V can be expressed as a linear combination of vectors in S.

**Mathematical Definition:**
S spans V if $V = \text{span}(S)$, where:
$$\text{span}(S) = \left\{\sum_{i=1}^n c_i v_i : n \in \mathbb{N}, c_i \in \mathbb{C}, v_i \in S\right\}$$

**Properties:**
1. **Completeness**: span(S) includes all possible linear combinations of S
2. **Minimality**: A spanning set may contain redundant vectors
3. **Finite Generation**: Finite-dimensional spaces have finite spanning sets

**Examples:**

**Single Qubit Space** $\mathbb{C}^2$:
- Standard spanning set: $\{|0\rangle, |1\rangle\}$
- Alternative spanning set: $\{|+\rangle, |-\rangle\}$ where $|+\rangle = \frac{1}{\sqrt{2}}(|0\rangle + |1\rangle)$

**Two Qubit Space** $\mathbb{C}^4$:
- Computational basis: $\{|00\rangle, |01\rangle, |10\rangle, |11\rangle\}$

**Key Insight:**
Any quantum state in the space can be written as a linear combination of spanning set vectors with appropriate coefficients.
 
***
&emsp;
 
## 15. Explain why the spanning set of a vector space is not unique

The spanning set is **not unique** because multiple different sets of vectors can generate the same vector space through linear combinations.

**Reasons for Non-Uniqueness:**

**1. Redundant Vectors:**
Adding linearly dependent vectors to a spanning set doesn't change the span:
- If S spans V, then $S \cup \{v\}$ also spans V for any $v \in V$

**2. Basis Transformations:**
Different bases span the same space:
- Standard basis: $\{|0\rangle, |1\rangle\}$ spans $\mathbb{C}^2$
- Hadamard basis: $\{|+\rangle, |-\rangle\}$ also spans $\mathbb{C}^2$

**3. Over-Complete Sets:**
More vectors than necessary can still span the space:
- $\{|0\rangle, |1\rangle, |+\rangle\}$ spans $\mathbb{C}^2$ (overcomplete)

**Examples:**

**For** $\mathbb{C}^2$:
- $S_1 = \{|0\rangle, |1\rangle\}$
- $S_2 = \{|+\rangle, |-\rangle\}$ where $|±\rangle = \frac{1}{\sqrt{2}}(|0\rangle ± |1\rangle)$
- $S_3 = \{|0\rangle, |1\rangle, |+\rangle\}$

All three sets span $\mathbb{C}^2$ but are different sets.

**Practical Implications:**
- Choice of spanning set affects computational efficiency
- Some bases (like computational basis) are more natural for certain problems
- Quantum algorithms may prefer specific basis representations
 
***
&emsp;
 
## 16. Define the inner product between two quantum states

The **inner product** is a fundamental mathematical operation in quantum mechanics that quantifies the "overlap" or similarity between two quantum states, such as $|\psi\rangle$ and $|\phi\rangle$. It's a generalization of the vector dot product to complex vector spaces and is denoted using bra-ket notation as $\langle\psi|\phi\rangle$.

The calculation involves multiplying the Hermitian conjugate of the first state (the "bra" $\langle\psi|$) with the second state (the "ket" $|\phi\rangle$):

$$\langle\psi|\phi\rangle = \sum_i \psi_i^* \phi_i$$

Where $\psi_i^*$ is the complex conjugate of the $i$-th component of the state vector $|\psi\rangle$. The result is a single complex number.

**Key Properties:**

1.  **Conjugate Symmetry**: Swapping the order of the states results in the complex conjugate of the original inner product: $\langle\psi|\phi\rangle = \langle\phi|\psi\rangle^*$.
2.  **Linearity**: The inner product is linear in its second argument (the ket) and anti-linear in its first argument (the bra).
3.  **Positive Definiteness**: The inner product of any state with itself yields a non-negative real number, which is the square of its norm: $\langle\psi|\psi\rangle = \|\psi\|^2 \geq 0$. For any **normalized** quantum state, which is a requirement for physical states, this value is exactly 1.

**Physical Significance:**

- **Probability Amplitude**: The complex number $\langle\phi|\psi\rangle$ is the **probability amplitude**. It represents the likelihood that a system prepared in state $|\psi\rangle$ will be measured to be in state $|\phi\rangle$.
- **Measurement Probability**: According to the Born rule, the actual probability of this measurement outcome is the squared magnitude of the amplitude: $P(\psi \rightarrow \phi) = |\langle\phi|\psi\rangle|^2$.
- **Orthogonality**: If the inner product is zero, $\langle\psi|\phi\rangle = 0$, the states are **orthogonal**. This signifies that they are perfectly distinguishable; if a system is in state $|\psi\rangle$, there is a zero probability of ever measuring it to be in state $|\phi\rangle$.

**Examples:**

- **Computational Basis States:**
The standard computational basis states, $|0\rangle$ and $|1\rangle$, are defined to be **orthonormal** (orthogonal and normalized).

$$\langle 0|0\rangle = 1, \quad \langle 1|1\rangle = 1, \quad \langle 0|1\rangle = 0$$

- **General Qubit States:**
For two arbitrary single-qubit states, $|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$ and $|\phi\rangle = \gamma|0\rangle + \delta|1\rangle$, their inner product is calculated as:

$$\langle\psi|\phi\rangle = \alpha^*\gamma + \beta^*\delta$$
 
***
&emsp;
 
## 17. Define orthonormality in a vector space

**Orthonormality** combines two concepts:

**Orthogonality:** Two vectors $|u\rangle$ and $|v\rangle$ are orthogonal if:
$$\langle u|v\rangle = 0$$

**Normalization:** A vector $|v\rangle$ is normalized if:
$$\langle v|v\rangle = ||v||^2 = 1$$

**Orthonormal Set:** A set $\{|v_1\rangle, |v_2\rangle, \ldots, |v_n\rangle\}$ is orthonormal if:
$$\langle v_i|v_j\rangle = \delta_{ij} = \begin{cases}
1 & \text{if } i = j \\
0 & \text{if } i \neq j
\end{cases}$$

**Properties:**
1. **Linear Independence**: Orthonormal vectors are automatically linearly independent
2. **Basis Property**: Orthonormal spanning sets form orthonormal bases
3. **Expansion Coefficients**: For orthonormal basis $\{|e_i\rangle\}$:
   $$|v\rangle = \sum_i \langle e_i|v\rangle |e_i\rangle$$

**Examples:**

**Computational Basis:**
$$\{|0\rangle, |1\rangle\} \text{ with } \langle 0|1\rangle = 0, \langle 0|0\rangle = \langle 1|1\rangle = 1$$

**Hadamard Basis:**
$$\{|+\rangle, |-\rangle\} \text{ where } |±\rangle = \frac{1}{\sqrt{2}}(|0\rangle ± |1\rangle)$$

**Advantages:**
- Simplifies calculations (orthogonal projection formulas)
- Numerically stable
- Physical interpretation (mutually exclusive measurement outcomes)
 
***
&emsp;
 
## 18. What is the purpose of the Gram-Schmidt process?

> Yaar, Santosh Sir ne bola tha, "Nahi lena panga,"
> "Yeh topic laana exam mein nahi hai changa."
> Lekin agar yeh sawaal exam mein aaya, toh main kya karunga?
> Ruk, main hi batata hoon... Sir ko hi Uthake phek dunga!

&emsp;

The **Gram-Schmidt process** converts any linearly independent set of vectors into an orthonormal set that spans the same subspace.

**Purpose:**
1. **Orthogonalization**: Create mutually orthogonal vectors
2. **Normalization**: Ensure all vectors have unit length
3. **Basis Construction**: Generate orthonormal bases from arbitrary spanning sets
4. **Numerical Stability**: Improve computational accuracy in quantum algorithms

**Algorithm:**
Given linearly independent vectors $\{|v_1\rangle, |v_2\rangle, \ldots, |v_n\rangle\}$:

**Step 1:** $|u_1\rangle = |v_1\rangle$
**Step 2:** For $k = 2, 3, \ldots, n$:
$$|u_k\rangle = |v_k\rangle - \sum_{j=1}^{k-1} \frac{\langle u_j|v_k\rangle}{\langle u_j|u_j\rangle} |u_j\rangle$$

**Step 3:** Normalize:
$$|e_k\rangle = \frac{|u_k\rangle}{||u_k||}$$

**Applications in Quantum Computing:**
- **State Preparation**: Converting arbitrary states to computational basis
- **Quantum Error Correction**: Constructing orthogonal code spaces  
- **Variational Algorithms**: Optimizing parameterized quantum circuits
- **Quantum Machine Learning**: Feature mapping and kernel methods

**Key Benefits:**
- Preserves span of original vectors
- Produces numerically stable orthonormal basis
- Enables efficient quantum state manipulation
 
***
&emsp;
 
## 19. Apply Gram-Schmidt to the vectors (1, 1) and (1, 0)

### **Given Vectors**
We are given two vectors, $|v_1\rangle$ and $|v_2\rangle$, in a 2-dimensional space.
$$|v_1\rangle = \begin{pmatrix} 1 \\ 1 \end{pmatrix}, \quad |v_2\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$$
The goal is to transform this set of vectors into an **orthonormal set**, $\{|e_1\rangle, |e_2\rangle\}$.

### **Step 1: Find the First Orthogonal Vector**
The first vector in our new orthogonal set, $|u_1\rangle$, is simply the first vector from our original set, $|v_1\rangle$.
$$|u_1\rangle = |v_1\rangle = \begin{pmatrix} 1 \\ 1 \end{pmatrix}$$

### **Step 2: Find the Second Orthogonal Vector**
The second orthogonal vector, $|u_2\rangle$, is found by subtracting the projection of $|v_2\rangle$ onto $|u_1\rangle$ from $|v_2\rangle$. This removes any component of $|v_2\rangle$ that is parallel to $|u_1\rangle$, leaving only the orthogonal part.

The formula is:
$$|u_2\rangle = |v_2\rangle - \text{proj}_{u_1}|v_2\rangle$$
First, we must compute the projection of $|v_2\rangle$ onto $|u_1\rangle$:
$$\langle\text{proj}_{u_1}|v_2\rangle = \frac{\langle u_1|v_2\rangle}{\langle u_1|u_1\rangle} |u_1\rangle$$
Let's calculate the required inner products (dot products):

1.  **Numerator:** $\langle u_1|v_2\rangle$
    $$
    \langle u_1|v_2\rangle = (1)(1) + (1)(0) = 1 + 0 = 1
    $$
2.  **Denominator:** $\langle u_1|u_1\rangle$
    $$
    \langle u_1|u_1\rangle = (1)(1) + (1)(1) = 1 + 1 = 2
    $$

Now, substitute these values back into the projection formula:
$$\langle\text{proj}_{u_1}|v_2\rangle = \frac{1}{2} |u_1\rangle = \frac{1}{2} \begin{pmatrix} 1 \\ 1 \end{pmatrix} = \begin{pmatrix} 1/2 \\ 1/2 \end{pmatrix}$$
Finally, calculate $|u_2\rangle$ by subtracting this projection from $|v_2\rangle$:
$$|u_2\rangle = |v_2\rangle - \langle\text{proj}_{u_1}|v_2\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix} - \begin{pmatrix} 1/2 \\ 1/2 \end{pmatrix} = \begin{pmatrix} 1 - 1/2 \\ 0 - 1/2 \end{pmatrix} = \begin{pmatrix} 1/2 \\ -1/2 \end{pmatrix}$$
Our set of **orthogonal vectors** is $\{|u_1\rangle, |u_2\rangle\}$:
$$|u_1\rangle = \begin{pmatrix} 1 \\ 1 \end{pmatrix}, \quad |u_2\rangle = \begin{pmatrix} 1/2 \\ -1/2 \end{pmatrix}$$


### **Step 3: Normalize the Orthogonal Vectors**
To get an orthonormal basis, we must normalize each orthogonal vector by dividing it by its magnitude (norm). An orthonormal vector $|e_i\rangle$ is given by $|e_i\rangle = \frac{|u_i\rangle}{||u_i||}$.

1.  **Normalize $|u_1\rangle$ to get $|e_1\rangle$**:
    First, find the norm of $|u_1\rangle$:
    $$
    ||u_1|| = \sqrt{\langle u_1|u_1\rangle} = \sqrt{1^2 + 1^2} = \sqrt{2}
    $$
    Now, create the unit vector $|e_1\rangle$:
    $$
    |e_1\rangle = \frac{|u_1\rangle}{||u_1||} = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ 1 \end{pmatrix} = \begin{pmatrix} 1/\sqrt{2} \\ 1/\sqrt{2} \end{pmatrix}
    $$
2.  **Normalize $|u_2\rangle$ to get $|e_2\rangle$**:
    First, find the norm of $|u_2\rangle$:
    $$
    ||u_2|| = \sqrt{\langle u_2|u_2\rangle} = \sqrt{\left(\frac{1}{2}\right)^2 + \left(-\frac{1}{2}\right)^2} = \sqrt{\frac{1}{4} + \frac{1}{4}} = \sqrt{\frac{2}{4}} = \sqrt{\frac{1}{2}} = \frac{1}{\sqrt{2}}
    $$
    Now, create the unit vector $|e_2\rangle$:
    $$
    |e_2\rangle = \frac{|u_2\rangle}{||u_2||} = \frac{1}{1/\sqrt{2}} \begin{pmatrix} 1/2 \\ -1/2 \end{pmatrix} = \sqrt{2} \begin{pmatrix} 1/2 \\ -1/2 \end{pmatrix} = \begin{pmatrix} \sqrt{2}/2 \\ -\sqrt{2}/2 \end{pmatrix} = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ -1 \end{pmatrix}
    $$


### **Final Orthonormal Vectors**
The resulting orthonormal basis vectors are:
$$|e_1\rangle = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ 1 \end{pmatrix}, \quad |e_2\rangle = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ -1 \end{pmatrix}$$


### **Verification**
To verify that the vectors are orthonormal, we check that their inner product is zero.
$$\langle e_1|e_2\rangle = \left(\frac{1}{\sqrt{2}}\right)\left(\frac{1}{\sqrt{2}}\right) + \left(\frac{1}{\sqrt{2}}\right)\left(-\frac{1}{\sqrt{2}}\right) = \frac{1}{2} - \frac{1}{2} = 0$$
Since their inner product is 0, the vectors are orthogonal. Since they are also unit vectors, the set is **orthonormal**.
 
***
&emsp;
 
## 20. What is the difference between orthogonalization and normalization?

| Aspect | Orthogonalization | Normalization |
|--------|-------------------|---------------|
| **Purpose** | Make vectors mutually perpendicular | Make vectors have unit length |
| **Mathematical Condition** | $\langle u_i\|u_j\rangle = 0$ for $i \neq j$ | $\langle v\|v\rangle = 1$ |
| **Process** | Remove components along other vectors | Scale vector by its norm |
| **Formula** | $\|u_k\rangle = \|v_k\rangle - \sum_{j<k} \text{proj}_{u_j}\|v_k\rangle$ | $\|e\rangle = \frac{\|v\rangle}{\|\|v\|\|}$ |
| **Effect on Direction** | Changes direction (except first vector) | Preserves direction |
| **Effect on Length** | Generally changes length | Always results in unit length |
| **Independence** | Can be done without normalization | Independent of orthogonalization |
| **Geometric Meaning** | Eliminates angular correlations | Standardizes magnitude |
 
***
&emsp;
 
## 21. What is the ket notation |ψ⟩ and bra notation ⟨ψ|?

**Dirac Notation** (Bra-Ket notation) is a standard notation for describing quantum states and operations, introduced by Paul Dirac.

**Ket Notation |ψ⟩:**
- Represents a quantum state vector in Hilbert space
- Column vector in matrix representation
- Contains complete information about quantum system

$$|\psi\rangle = \begin{pmatrix} \alpha \\ \beta \end{pmatrix} = \alpha|0\rangle + \beta|1\rangle$$

**Bra Notation ⟨ψ|:**
- Complex conjugate transpose of corresponding ket
- Row vector in matrix representation  
- Used for inner products and expectation values

$$\langle\psi| = (\alpha^* \quad \beta^*) = \alpha^*\langle 0| + \beta^*\langle 1|$$

**Combined Operations:**

- **Inner Product (Bracket):**
$$\langle\phi|\psi\rangle = \text{complex number (probability amplitude)}$$

- **Outer Product (Ket-Bra):**
$$|\psi\rangle\langle\phi| = \text{operator/matrix}$$

**Key Properties:**

1. **Conjugate Relationship**:
$$\langle\psi| = (|\psi\rangle)^\dagger$$
&emsp; &emsp; &emsp; Where $\dagger$ denotes Hermitian conjugate (complex conjugate transpose)

2. **Normalization:**
$$\langle\psi|\psi\rangle = |\alpha|^2 + |\beta|^2 = 1$$

3. **Linearity:**
$$\langle\psi|(a|\phi_1\rangle + b|\phi_2\rangle) = a\langle\psi|\phi_1\rangle + b\langle\psi|\phi_2\rangle$$

**Examples:**

**Computational Basis:**
- $|0\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$, $\langle 0| = (1 \quad 0)$
&emsp;
- $|1\rangle = \begin{pmatrix} 0 \\ 1 \end{pmatrix}$, $\langle 1| = (0 \quad 1)$

**Superposition State:**
- $|+\rangle = \frac{1}{\sqrt{2}}(|0\rangle + |1\rangle)$
- $\langle +| = \frac{1}{\sqrt{2}}(\langle 0| + \langle 1|)$

**Physical Interpretation:**
- **Ket**: State of quantum system
- **Bra**: Measurement basis or observable
- **Bracket**: Probability amplitude for measurement outcome
- **Ket-Bra**: Quantum operation or projection operator

**Advantages:**
1. **Coordinate-free**: Independent of specific basis choice
2. **Intuitive**: Separates states from their representations
3. **Compact**: Simplifies complex quantum mechanical expressions
4. **Universal**: Standard notation across quantum physics and computing

---

*This assignment covers the fundamental concepts of quantum computing, providing the mathematical foundation needed for understanding quantum algorithms and quantum information theory. Each concept builds upon previous ones, creating a comprehensive framework for quantum computational thinking.*
