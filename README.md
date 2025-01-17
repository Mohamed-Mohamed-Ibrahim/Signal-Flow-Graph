# Signal Flow Graph & Routh Stability Criterion

<p align="center">
  <a href="#key-features">Key Features</a> •
  <a href="#how-to-use">How To Use</a> •
  <a href="#dependencies">Dependencies</a> •
  <a href="#app-design">App Design</a> •
  <a href="#future-features">Future Features</a> •
  <a href="#documentation">Documentation</a> •
  <a href="#contact">Contact</a> •
  <a href="#license">License</a> •
  <a href="#acknowledgements">Acknowledgements</a>
</p>

---

## Key Features

- **Signal Flow Graph**
  1. Draw the signal flow graph 

  2. Assignment of values to the branches 

  3. Assignment of input and output node 

  4. Solve the signal flow graph to get the transfer function

  5. Listing all forward paths, individual loops, all combination of n non-touching loops. 
- **Routh Stability Criterion**
  - Parses the characteristic equation to extract coefficients.
  - Constructs the Routh array based on the extracted coefficients.
  - Determines system stability using the Routh-Hurwitz criterion.
  - Finds the roots of the characteristic equation and identifies poles in the RHP.
  - Displays the Routh array, system stability status, and roots of the equation.

---

## Dependencies

- **Frontend**
  - [Vue.js](https://vuejs.org/)
- **Backend**
  - [Spring Boot](https://spring.io/projects/spring-boot)

---

## How To Use

```bash
# Clone this repository
$ git clone https://github.com/Mohamed-Mohamed-Ibrahim/Signal-Flow-Graph.git

# Go into the repository
$ cd Signal-Flow-Graph

# Open 2 command lines

# First cli
$ cd frontend
$ npm install
$ npm start

# second cli
$ cd backend
$ mvn spring-boot:run

```

# Signal Flow Graph

#### Problem Statement 

Signal flow graph representation of the system. Assume that total number of nodes and numeric 

branches gains are given. 

Required: 

1. Graphical interface.

2. Draw the signal flow graph showing nodes, branches,gains, … 

3. Listing all forward paths, individual loops, all combination of n non-touching loops. 

4. The values of Δ , Δ1 , …, Δm where m is number of forward paths. 

5. Overall system transfer function.

#### Data Structure 

▪ Lists (ArrayList): Used for representing the graph, paths, loops, non-touching loops, gains, and other data structures. 

▪ Stacks: Utilized for backtracking and maintaining state during loop detection and combination processes. 

▪ Custom data structure (MyPair): Represents pairs of integers used to describe edges in the graph. 

#### Main Modules

### backend -&gt;

▪ Initialization (init()): Initializes data structures and prepares the graph for analysis. 

▪ Finding Paths (findAllPaths()): Finds all paths from the source to the destination node in the graph. 

▪ Finding Loops (findLoopsGains()): Detects all loops within the graph and calculates their gains. 

▪ Combining Loops (combine()): Combines non-touching loops to analyze higher-order loop interactions. 

▪ Computing Transfer Function (overAllTransferFunction()): Computes the overall transfer function of the signal flow system.

Front end-&gt; This is the GUI of the program. Through it, we can draw the graph and send data to the backend. 

### 5) Algorithms Used 

▪ Depth-First Search (DFS): Used for finding all paths in the graph and detecting loops. 

▪ Backtracking: Utilized in combination with DFS for loop detection and non-touching loop combination. 

▪ Combinatorial Techniques: Employed to combine non-touching loops efficiently. 

### 6) Sample Runs 

<!-- 四  -->
![](https://web-api.textin.com/ocr_image/external/dfc5bfce0cb46e4d.jpg)





<!-- c  -->
![](https://web-api.textin.com/ocr_image/external/7c7652f1df37ec07.jpg)

Enter the gain

<!-- Eer  -->
![](https://web-api.textin.com/ocr_image/external/32781cd007296fa2.jpg)

<!-- 2 2 4 3  -->
![](https://web-api.textin.com/ocr_image/external/26d01e2e7d08e1a9.jpg)

<!-- Paths: Loops: path 1=0,1,2,3,4,5 100p1=1 Non Touching Loops: 100p2=2,3,4 2=1,2,3,4 3=N/A Δ: Δ=99 Transfer Function: Δ1=1 0.6464646464646465  -->
![](https://web-api.textin.com/ocr_image/external/5f5e543f6601bc51.jpg)


![](https://web-api.textin.com/ocr_image/external/1efac808400bbe23.jpg)

<!-- Closs  -->
![](https://web-api.textin.com/ocr_image/external/890af072c9a9c34a.jpg)


|  | Enter the gain: 6  |
| -- | -- |
| <img src="https://web-api.textin.com/ocr_image/external/b99a403115b54133.jpg"> |  |


0

Paths:

path1=0,1,2,3,4

path2=0.1,3,4

Loops:

Non Touching Loops:

2=N/A

Δ:

Δ=1

Δ1=1

Δ2=1


|  |  |  |  |
| -- | -- | -- | -- |
|  |  |  |  |
|  |  |  |  |


Transfer Function:


![](https://web-api.textin.com/ocr_image/external/bb616025cec0a487.jpg)

20

<!-- Enter the goin: C] Paths: Loops: path 1=0,1,2,3,4,5 100p1=1 100p2=2 100p3=3 Non Touching Loops: 100p4=4 2=1,2,1,3,1,4,2,3,2,4,3,4 1,2,1,3,1,4,2,3,2,4,3,4 1.2,1,3,1.4,2,3,2,4,3,4 1.2,1,3,1.4,2,3,2,4,3,4 1,2,1,3,1,4,2,3,2,4,3,4 1,2,1,3,1,4,2,3,2,4,3,4 3 =1.2,3,1,2,4.1,3,4,2,3,4 1,2,3,1,2,4,1,3,4,2,3,4 1,2,3,1,2,4,1,3,4,2,3,4 1,2,3,1,2,4,1,3,4,2,3,4 Δ: 4=1,2,3,4 Δ=1 Transfer Function: Δ1=-79 -5056  -->
![](https://web-api.textin.com/ocr_image/external/65f1d54e1166ada8.jpg)

Enter the gois:


![](https://web-api.textin.com/ocr_image/external/646cde6a1836d649.jpg)

Paths:


|  | path$1 = 0 , 1 , 4 , 5$$p a t h 2 = 0 , 1 , 2 , 3 , 4 , 5$ |
| -- | -- |
| Loops:Non Touching Loops: | $2 = N / A$ |
| Δ: | $\Delta = 1$$\Delta 1 = 1$$\Delta 2 = 1$ |
| Transfer Function: | 1088  |



![](https://web-api.textin.com/ocr_image/external/46d4640fe4b0a997.jpg)


![](https://web-api.textin.com/ocr_image/external/92d7e0fbb8eddd13.jpg)

### 7) Simple User Guide: 

- you have to download frontend code and backend code.

- Verify the presence of Node.js on your system.

- Utilize the command "npm i serve" to install the requisite modules. 

- Launch the front end using the command "npm run serve."

- after this you click on the link in the terminal and this window will appear: 


![](https://web-api.textin.com/ocr_image/external/fbb71a3339a6757a.jpg)

### - you can choose add nodes using this button:

<!-- Enter the gain:  -->
![](https://web-api.textin.com/ocr_image/external/e0e9c6ee5a29e2f3.jpg)

-You can link node using this button:

<!-- Enter the goin  -->
![](https://web-api.textin.com/ocr_image/external/8d4111563201542e.jpg)

- You can determine the input node using this button: 

<!-- - -  -->
![](https://web-api.textin.com/ocr_image/external/3de530fc0aab11d2.jpg)

### - You can determine the output node using this button: 


![](https://web-api.textin.com/ocr_image/external/d7fee6d54aacdbef.jpg)

- You can enter the gain by clicking on this button and finally enter the gain in this text box and click on the link then enter:

- Finally, you can click on this button to show all information like transfer function, paths, loop, and self loops. 


![](https://web-api.textin.com/ocr_image/external/31b8944d1f0b0dee.jpg)


![](https://web-api.textin.com/ocr_image/external/546f88b5c35e66b3.jpg)

1) Problem Statement 

Given the characteristic equation of a system, implement the Routh-Hurwitz stability criterion to determine if the system is stable or not. If the system is unstable, list the number and values of poles in the right-half plane (RHP) of the s-plane. 

### 2) Main Features of the Program and Additional Options

• Parses the characteristic equation to extract coefficients. 

• Constructs the Routh array based on the extracted coefficients. 

• Determines system stability using the Routh-Hurwitz criterion. 

• Finds the roots of the characteristic equation and identifies poles in the RHP. 

• Displays the Routh array, system stability status, and roots of the equation. 

### 3) Data Structure 

• Map: Used to store coefficients for each power of 's' in the characteristic equation. 

• Double Array: Represents the Routh array, initialized with null values for ease of calculation. 

### 4) Main Modules

• constructRouthArray: Constructs the Routh array based on the coefficients of the characteristic equation. 

• countSignChanges: Counts the number of sign changes in the first column of the Routh array. 

• findRoots: Finds the roots of the characteristic equation using the LaguerreSolver. 

### 5) Algorithms Used 

• Routh-Hurwitz Criterion: Determines system stability based on the number of sign changes in the first column of the Routh array. 

• Laguerre's Method: Finds the roots of the characteristic equation using the LaguerreSolver. 

### 6) Sample Runs 

Enter the characteristic equation:$5 ^ { \wedge } 4 + 2 5 ^ { \wedge } 3 + 3 5 ^ { \wedge } 2 + 4 5 + 5$

Routh Array:

[1.0,3.0,5.0]

[2.0,4.0,null]

[1.0,5.0,null]

[-6.0,0.0,null]

[5.0,0.0,null]

The system is unstable with 2 poles in RHS

Roots:

Root: 0.29 - 1.421

Root: 0.29 +1.421

Root: -1.29+0.861

Root: -1.29 - 0.861

Enter the characteristic equation:$S ^ { \wedge } 3 + 2 S ^ { \wedge } 2 + 1 S + 2$

Routh Array:

[1.0,1.0]

[2.0, 2.0]

[1.0E-9,null]

[2.0, null]

The system is stable

Roots:

Root:0.00 - 1.00i

Root:0.00+1.00i

Root: -2.00

Enter the characteristic equation:$S ^ { \wedge } 5 + 2 S ^ { \wedge } 4 + 2 5 ^ { \wedge } 3 + 4 S ^ { \wedge } 2 + 1 1 S + 1 0$

Routh Array:

[1.0,2.0,11.0]

[2.0,4.0,10.0]

[1.0E-9,6.0,null]

[-1.1999999995999998E10, 10.0, nulL]

[6.0,0.0,nulL]

[10.0,0.0,null]

The system is unstable with 2 poles in RHS

Roots:

Root: -1.31

Root: -1.24 - 1.041

Root: -1.24+1.041

Root: 0.90 - 1.461

Root: 0.90 + 1.461

Enter the characteristic equation: $5 ^ { \wedge } 5 + 2 5 ^ { \wedge } 4 + 2 4 5 ^ { \wedge } 3 + 4 8 5 ^ { \wedge } 2 - 2 5 5 - 5 0$

Routh Array:

[1.0,24.0,-25.0]

[2.0,48.0,-50.0]

[8.0,96.0,0.0]

[24.0,-50.0,null]

[112.66666666666667,0.0,nuLl]

[-50.0,0.0,null]

The system is unstable with 1 poles in RHS

Roots:

Root:-1.00

Root:1.00

Root:-2.00

Root:-0.00-5.001

Root: -0.00+5.001

### 7) Simple User Guide

1)Input the characteristic equation of the system as shown in sample runs enter all coefficients even if they are 1 and don't use spaces. 

2)The program will display the Routh array, system stability status, and roots of the characteristic equation. 

3)If the system is unstable, the program will also list the number and values of poles in the right-half plane. 



