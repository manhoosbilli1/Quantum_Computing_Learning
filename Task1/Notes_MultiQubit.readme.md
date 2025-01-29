# Multi-Qubit System

- Compound system: taking multiple systems and seeing it as a single system.

## Measurements of Probabilistic States (Partial)
- Measuring some systems instead of all, leaving the rest of the state changed. It would be as though we have measured both or all systems.
- By condition pr(x = a) = sum over b that belongs to gamma set ((x, y) = (a, b))

- What happens to Y or remaining systems after measuring a single or partial measurement? Because of some uncertainty, the rest of the system now needs to be normalized, given by
- pr(y = b | x = a) = pr((x, y) = (a, b)) / (pr(x = a))
- For multiple states in a system, it needs to be summed over the possibilities.
- Composite vector applies to respective positions.
- Tensor product shows independence.
- Suppose the operation is performed on a bit X and a NOT operation is independently performed on a second bit Y, then it's just a tensor of the two matrices. So this shows how when we have two gates in parallel acts, it's a tensor, and in series, it's a matrix multiplication.

- All gates and things that evolve a state are unitary matrices, they have the following properties, they are hermition, follow U(conjugate & transpose) x U = Identity and also can be seen that the matrix is unitary if all of it's unit vectors are basis vectors that follow Vi.Vi = 1 for all i and Vi . Vj = 0 except i != j 

- Unitary matrices rows and columns should correspond to the cartesian product set of the states of the the system. say we have sigma and gamma with {0, 1, 2} and {0, 1} respectively. then a cartesian product is 3x2 = 6. all the columns and rows in our matrix should contains 6 elements in each row and each column as if it corresponds to the cartesian product set then it will be considered unitary. 

- or in case of single qubit the rows and columns should correspond to the classical set. 
- deterministic measurement is that for same input you get same output. wihtout any randomness in it. 
- Unitary multiplied with another unitary matrix is also unitary because it's hermitian. 
- But a tensor product between two unitary is not identity.. it's a larger matrix. 
- say we have a system of 2 qubits each having dimension of 2x1. and their operators being 2x2 matrices. now these matrices are unitary but the state contains 2 states. and the matrix contains 4. how are they equal? 

- For a single qubit, the quantum state is represented as a vector in a 2-dimensional Hilbert space, \( \mathbb{C}^2 \). The basis states \( |0\rangle \) and \( |1\rangle \), often referred to as the computational basis, correspond to the classical binary states \( 0 \) and \( 1 \). When dealing with quantum gates (which are represented as \( 2 \times 2 \) unitary matrices), the rows and columns of these matrices represent transitions or transformations within this computational basis. Specifically, the \( i \)-th column of the matrix indicates how the \( i \)-th basis state transforms under the operation. Thus, the rows and columns are directly related to the classical basis states \( |0\rangle \) and \( |1\rangle \), ensuring that the quantum operations preserve the underlying structure of the classical set.


- A deterministic measurement in quantum mechanics implies that the outcome of the measurement is predictable and consistent for the same input state. Mathematically, if the quantum state \( |\psi\rangle \) is an eigenstate of the measurement operator \( \hat{M} \), the measurement outcome will always yield the corresponding eigenvalue without randomness. For example, if \( \hat{M}|\psi\rangle = \lambda |\psi\rangle \), where \( \lambda \) is the eigenvalue, measuring the state \( |\psi\rangle \) repeatedly under \( \hat{M} \) will always yield \( \lambda \). In contrast, non-deterministic (probabilistic) measurements yield varying outcomes based on the probability distribution derived from the state's overlap with the eigenstates of the operator.


- If \( U_1 \) and \( U_2 \) are unitary matrices, their product \( U_1 U_2 \) is also unitary. This follows from the property that \( U^\dagger U = I \) (where \( U^\dagger \) is the conjugate transpose). For the product:
  \[
  (U_1 U_2)^\dagger (U_1 U_


- Say we have two qubits. to operate on the combined state one has to have two 2x2 matrices tensor with each other that corresponds to the space of the combined system. so X and Y qubit and applying X operator on x and nothing on Y is X (tensor) Y. instead of just X.

- Not all operators can be written as a tensor of unitary operators. just as not every state is a product state. examples are swap gate and controlled not gate. cx gate. 
- swap gate is basically sum over combined space tuples bra(a)bra(b) tensor bra(b)bra(a) 
- controlled unitary operation is written as CU = '0' tensor identity (of dimensions R) + '1' tensor U 
- In the case of qubit and two qubits the R is 4 dimensions. so we will have 4x4 matrix on each side of sum. this expression means that the 0th bit will have nothing done on it. and the first bit will have the operation tensored with it so that when applied to some state it isolate the 2nd bit of the combined state and applies only the X gate on the target qubit or in this case the second qubit hence the position being on the most right. 
- If we wanted to have a three qubit CCX gate we would want to apply the X gate to the 3rd bit and leave the rest two untouched. it would be like this. ('0bit' + '1bit') tensor idensity of dimensions (4) + ('2bit') tensor with X 
or (|0><0|+ |01><01|) Tensor Isub(4) + |11><11| tensor X = CCX (toffoli gate)


- most of the circuits can be simulated through ibms service. and shown in qsphere 

- see for single qubits how does it look like in bloch sphere (bear in mind it is a 3D space and one of the amplitudes will always be zero)

- Qiskit Uses Little Endian whereas some books use Big Endian. to convert use qc.reverse_bits();


## Quantum Circuits 
- AER simulator is a simulator to simulate quantum computer on your device
- Create bell states by creating a program on your own. 


### Phase Gate 
- Phase gate adds a phase to the state. This is different than Rotation which also adds a phase but that is relative. 
- Z gate is a special case of phase gate with pi as the phase. this add a local phase to the state |11> . 
- Phase does not change the probabilities of state
- Inverse of P is just phi => -phi as the change in iots due to inverse 
- P gate rotates about z axis counter clockwise but inverse of p rotates clockwise. 
- Global phase make no difference to a set because when we find probabilities it turns out to be the same. 
- Phases where the minus sign or some angle is being multiplied with only a single or few components is relative phase. 
- Local phases matter or not? 
- No Cloning theorem: it's not possible. because in order to know a state one has to observe it. that collapses the state to 
  a reduced state in process destroying the state. hence if it is destroyed it can't be copied? No cloning is not possible because of violation of linearity of quantum mechanics As well
  as because mathematically | psi > ten |psi > does not equate to a cloned state without having cross terms within it. 
- An arbitrary state cannot be perfectly cloned but it could be cloned to some extent with inaccuracy 
- Basis states can be cloned for example using a CNOT gate but only states or states that are in some sort of superposition impposible to clone perfectly. 




#### Phase Gate and bloch sphere
- The P gate performs a rotation about the Z axis given by angle in radians. in the counter 
# Questions
- What does doing a norm do for a vector and what does it mean in complex space?

- Why is there uncertainty in the remaining state when a system is measured for a certain state?

- Find the main postulates of QM governing quantum information. 

- Find the main problems related to quantum information and limitations.

- What is a phase in such a context and how does it differ for all gates?
 



