## Roadmap

- [ ] Micrograd
- [ ] Backpropagation
- [ ] MLP
- [ ] Makemore Part 1
- [ ] Makemore Part 2
- [ ] Makemore Part 3
- [ ] GPT

# DAY 1 (29-05-2026)

Started with micrograd, Understood basic derivatives,slope and what do they represent intuitively. Started working with micrograd and writing my own code for it. 

Initialized the main data structure i.e. Value class and added children,op and basic operator overloading to it.

## Key Learnings

- Derivatives measure how sensitive an output is to changes in an input.
- Slope represents the local rate of change at a point.
- Neural networks can be represented as computational graphs made of simple mathematical operations.
- Every node must keep track of how it was created to enable backpropagation later.

# DAY 2 (30-05-2026)

Understood backpropogation and how gradients are calculated and passed backward. Also implemented it on a simple neuron. Experimented and played with the Value class members and visualized how gradients affect the forward pass.

## Key Learnings

- Chain rule:- dx/dz= dx/dy * dy/dz i.e. if x and y are dependent directly and y and z are dependent then we can find how x changes with z through chain rule
- Basic structure of a neuron, the input is multiplied by some weight and then a bias is added to it and further it is passed through an activation function

- A single neuron structure:- 
    <p align="center">
        <img src= "assets\Screenshots\Neuron.webp" width="600">
    </p>

# DAY 3 (1-06-2026)

Understood the implemention part of backpropogation,topological sort and handled two bugs. Also started to learn the neuron and layer class and started implementing it. Also compared out micrograd with pytorch inbuilt MLP.

## Key Learnings

- Implemented backpropogation and cross checked the gradients manually, also made grad and backward memberes in the Value class
- Also fixed the code as it was not considering multivariate chain rule case i.e. if there are multiple variables for the calculation of a single gradient, the gradients accumulate
- Learnt about topological sort and how it is used to automate backpropogation instead of redundantly calling the _backward() function again and again
    <p>
    <a href="https://www.geeksforgeeks.org/dsa/topological-sorting/">
        Topological Sort Reference
    </a>
</p>

- Added many other arithmetic functions to our Value calss like __rmul__, __neg__, __pow__, __exp__ and defined the gradients for each of them also handled the case when our value class element is being multiplied by a constant
- Made the neuron class which defines a nsingle neuron with weights and bias initially randomized bw -1 and 1 and then using __call__ member the activation function is defined and returned thereafter.

