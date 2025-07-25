# Assignment 1 - Quantum Computing

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

## 4. What is a qubit and how does it differ from a classical bit?

**Classical Bit:**
- Binary state: either 0 or 1
- Deterministic measurement
- Information capacity: 1 bit

**Qubit (Quantum Bit):**
- Quantum superposition: can be in state $\alpha|0\rangle + \beta|1\rangle$
- Probabilistic measurement with outcomes governed by $|\alpha|^2$ and $|\beta|^2$
- Information capacity: theoretically infinite (continuous parameters α and β)

**Key Differences:**

1. **State Space**: Classical bit has 2 states; qubit has infinite states on Bloch sphere
2. **Measurement**: Classical measurement is deterministic; quantum measurement is probabilistic  
3. **Reversibility**: Classical operations can be irreversible; quantum operations must be unitary (reversible)
4. **Copying**: Classical bits can be copied; qubits cannot be cloned (No-cloning theorem)

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

## 6. Explain the concept of measurement in qubits. What happens after a measurement?

**Quantum Measurement Process:**

For a qubit in state $|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$:

**Before Measurement:**
- Qubit exists in superposition
- Contains both |0⟩ and |1⟩ components simultaneously

**During Measurement:**
- The measurement "forces" the qubit to "choose" either |0⟩ or |1⟩
- Probability of measuring |0⟩: $P(0) = |\alpha|^2$ (square of amplitude)
- Probability of measuring |1⟩: $P(1) = |\beta|^2$ (square of amplitude)
- These probabilities always sum to 1: $|\alpha|^2 + |\beta|^2 = 1$

**After Measurement:**
1. **State Collapse**: The superposition collapses to the measured eigenstate
   - If result is 0: $|\psi\rangle \rightarrow |0\rangle$
   - If result is 1: $|\psi\rangle \rightarrow |1\rangle$

2. **Information Loss**: Original superposition information is irretrievably lost
3. **Subsequent Measurements**: Repeated measurements yield the same result with probability 1

**Mathematical Formalism:**
$$\text{Measurement outcome } m \text{ with probability } p_m = \langle\psi|M_m^\dagger M_m|\psi\rangle$$
$$\text{Post-measurement state: } \frac{M_m|\psi\rangle}{\sqrt{p_m}}$$

## 7. What is the Bloch sphere and how does it represent a qubit?

<img width="238" height="252" alt="Bloch Sphere" src="https://github.com/user-attachments/assets/2c7547f9-f8e4-4a8d-80de-e009cf70254d" />


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

## 9. Explain the tensor product and how it applies to multiple qubits

**Tensor Product Definition:**
The tensor product (⊗) combines separate quantum systems into a composite system.

**For Vectors:**
If $|a\rangle = \begin{pmatrix} a_1 \\ a_2 \end{pmatrix}$ and $|b\rangle = \begin{pmatrix} b_1 \\ b_2 \end{pmatrix}$, then:

$$|a\rangle \otimes |b\rangle = \begin{pmatrix} a_1 b_1 \\ a_1 b_2 \\ a_2 b_1 \\ a_2 b_2 \end{pmatrix}$$

**Multiple Qubit Systems:**
For qubits $|\psi_1\rangle = \alpha_1|0\rangle + \beta_1|1\rangle$ and $|\psi_2\rangle = \alpha_2|0\rangle + \beta_2|1\rangle$:

$$|\psi_1\rangle \otimes |\psi_2\rangle = \alpha_1\alpha_2|00\rangle + \alpha_1\beta_2|01\rangle + \beta_1\alpha_2|10\rangle + \beta_1\beta_2|11\rangle$$

**Properties:**
1. **Bilinearity**: $(a|u\rangle + b|v\rangle) \otimes |w\rangle = a|u\rangle \otimes |w\rangle + b|v\rangle \otimes |w\rangle$
2. **Associativity**: $(|a\rangle \otimes |b\rangle) \otimes |c\rangle = |a\rangle \otimes (|b\rangle \otimes |c\rangle)$
3. **Distributivity**: Distributes over addition

**Notation Shortcuts:**
- $|a\rangle \otimes |b\rangle = |a\rangle|b\rangle = |ab\rangle$
- $|0\rangle \otimes |1\rangle = |01\rangle$

## 10. Define a vector space in the context of quantum computing

A **vector space** (or linear space) V over a field F is a set equipped with two operations that satisfy specific axioms:

**Operations:**
1. **Vector Addition**: $+: V \times V \rightarrow V$
2. **Scalar Multiplication**: $\cdot: F \times V \rightarrow V$

**In Quantum Computing Context:**
- **Vectors**: Quantum states represented as complex vectors
- **Field**: Complex numbers $\mathbb{C}$
- **Vector Space**: Space of all possible quantum states

**Examples:**
- Single qubit space: $\mathbb{C}^2$ spanned by $\{|0\rangle, |1\rangle\}$
- n-qubit space: $\mathbb{C}^{2^n}$ spanned by computational basis states

**Physical Interpretation:**
- Vectors represent quantum states
- Linear combinations represent superposition
- Inner products define probability amplitudes
- Unitary transformations preserve vector space structure

## 11. What are the axioms of a vector space?

A vector space V over field F must satisfy eight axioms:

**Addition Axioms:**
1. **Closure**: $\forall u, v \in V: u + v \in V$
2. **Associativity**: $\forall u, v, w \in V: (u + v) + w = u + (v + w)$
3. **Commutativity**: $\forall u, v \in V: u + v = v + u$
4. **Identity Element**: $\exists 0 \in V$ such that $\forall v \in V: v + 0 = v$
5. **Inverse Element**: $\forall v \in V, \exists (-v) \in V$ such that $v + (-v) = 0$

**Scalar Multiplication Axioms:**
6. **Closure**: $\forall a \in F, v \in V: av \in V$
7. **Associativity**: $\forall a, b \in F, v \in V: a(bv) = (ab)v$
8. **Distributivity**: 
   - $\forall a \in F, u, v \in V: a(u + v) = au + av$
   - $\forall a, b \in F, v \in V: (a + b)v = av + bv$

**Additional Property:**
- **Multiplicative Identity**: $\forall v \in V: 1v = v$ where 1 is the multiplicative identity in F

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

## 16. Define the inner product between two quantum states

The **inner product** between two quantum states $|\psi\rangle$ and $|\phi\rangle$ is:

$$\langle\psi|\phi\rangle = \sum_i \psi_i^* \phi_i$$

Where $\psi_i^*$ is the complex conjugate of the i-th component of $|\psi\rangle$.

**Properties:**
1. **Conjugate Symmetry**: $\langle\psi|\phi\rangle = \langle\phi|\psi\rangle^*$
2. **Linearity in Second Argument**: $\langle\psi|a\phi_1 + b\phi_2\rangle = a\langle\psi|\phi_1\rangle + b\langle\psi|\phi_2\rangle$
3. **Positive Definiteness**: $\langle\psi|\psi\rangle \geq 0$ with equality iff $|\psi\rangle = 0$

**Physical Interpretations:**
- **Probability Amplitude**: $\langle\phi|\psi\rangle$ gives amplitude for measuring $|\psi\rangle$ in state $|\phi\rangle$
- **Transition Probability**: $|\langle\phi|\psi\rangle|^2$ is probability of transition
- **Orthogonality**: $\langle\psi|\phi\rangle = 0$ means states are orthogonal (distinguishable)

**Examples:**

**Computational Basis:**
$$\langle 0|0\rangle = 1, \quad \langle 1|1\rangle = 1, \quad \langle 0|1\rangle = 0$$

**General States:**
For $|\psi\rangle = \alpha|0\rangle + \beta|1\rangle$ and $|\phi\rangle = \gamma|0\rangle + \delta|1\rangle$:
$$\langle\psi|\phi\rangle = \alpha^*\gamma + \beta^*\delta$$

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

## 18. What is the purpose of the Gram-Schmidt process?

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

## 19. Apply Gram-Schmidt to the vectors (1, 1) and (1, 0)

**Given vectors:**
$$|v_1\rangle = \begin{pmatrix} 1 \\ 1 \end{pmatrix}, \quad |v_2\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$$

**Step 1: First orthogonal vector**
$$|u_1\rangle = |v_1\rangle = \begin{pmatrix} 1 \\ 1 \end{pmatrix}$$

**Step 2: Second orthogonal vector**
Compute projection of $|v_2\rangle$ onto $|u_1\rangle$:
$$\text{proj}_{u_1}|v_2\rangle = \frac{\langle u_1|v_2\rangle}{\langle u_1|u_1\rangle} |u_1\rangle$$

Calculate inner products:
$$\langle u_1|v_2\rangle = 1 \cdot 1 + 1 \cdot 0 = 1$$
$$\langle u_1|u_1\rangle = 1^2 + 1^2 = 2$$

Therefore:
$$\text{proj}_{u_1}|v_2\rangle = \frac{1}{2} \begin{pmatrix} 1 \\ 1 \end{pmatrix} = \begin{pmatrix} 1/2 \\ 1/2 \end{pmatrix}$$

$$|u_2\rangle = |v_2\rangle - \text{proj}_{u_1}|v_2\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix} - \begin{pmatrix} 1/2 \\ 1/2 \end{pmatrix} = \begin{pmatrix} 1/2 \\ -1/2 \end{pmatrix}$$

**Step 3: Normalize vectors**
$$||u_1|| = \sqrt{1^2 + 1^2} = \sqrt{2}$$
$$||u_2|| = \sqrt{(1/2)^2 + (-1/2)^2} = \sqrt{1/2} = \frac{1}{\sqrt{2}}$$

**Final orthonormal vectors:**
$$|e_1\rangle = \frac{|u_1\rangle}{||u_1||} = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ 1 \end{pmatrix}$$

$$|e_2\rangle = \frac{|u_2\rangle}{||u_2||} = \sqrt{2} \begin{pmatrix} 1/2 \\ -1/2 \end{pmatrix} = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ -1 \end{pmatrix}$$

**Verification:**
$\langle e_1|e_2\rangle = \frac{1}{\sqrt{2}} \cdot \frac{1}{\sqrt{2}} + \frac{1}{\sqrt{2}} \cdot \frac{-1}{\sqrt{2}} = \frac{1}{2} - \frac{1}{2} = 0$

✓ Vectors are orthonormal

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

**Example Illustration:**
Starting with $|v\rangle = \begin{pmatrix} 3 \\ 4 \end{pmatrix}$:

**Normalization only:**
$$||v|| = \sqrt{3^2 + 4^2} = 5$$
$$|v_{\text{norm}}\rangle = \frac{1}{5}\begin{pmatrix} 3 \\ 4 \end{pmatrix}$$
Direction preserved, length = 1

**Combined Process in Gram-Schmidt:**
1. **Orthogonalization**: Adjust direction to be perpendicular to previous vectors
2. **Normalization**: Scale resulting vector to unit length

**Physical Significance:**
- **Orthogonalization**: Ensures quantum states are distinguishable
- **Normalization**: Ensures probability conservation ($\sum |c_i|^2 = 1$)

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

**Inner Product (Bracket):**
$$\langle\phi|\psi\rangle = \text{complex number (probability amplitude)}$$

**Outer Product (Ket-Bra):**
$|\psi\rangle\langle\phi| = \text{operator/matrix}$

**Key Properties:**

**1. Conjugate Relationship:**
$\langle\psi| = (|\psi\rangle)^\dagger$
Where $\dagger$ denotes Hermitian conjugate (complex conjugate transpose)

**2. Normalization:**
$\langle\psi|\psi\rangle = |\alpha|^2 + |\beta|^2 = 1$

**3. Linearity:**
$\langle\psi|(a|\phi_1\rangle + b|\phi_2\rangle) = a\langle\psi|\phi_1\rangle + b\langle\psi|\phi_2\rangle$

**Examples:**

**Computational Basis:**
- $|0\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$, $\langle 0| = (1 \quad 0)$
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
