# LSTM

Long Short Term Memory networks – usually just called “LSTMs” – are a special kind of RNN, capable of learning long-term dependencies.

LSTMs are explicitly designed to avoid the long-term dependency problem.  **Remembering information for long periods of time is practically their default behavior, not something they struggle to learn!**

## Standard structure 

All recurrent neural networks have the form of a chain of repeating modules of neural network. In standard RNNs, this repeating module will have a very simple structure, such as a single tanh layer.

![The repeating module in a standard RNN contains a single layer.](.gitbook/assets/image%20%281%29.png)

## LSTM Structure

LSTMs also have this chain like structure, but the repeating module has a different structure. **Instead of having a single neural network layer, there are four, interacting in a very special way.**

![The repeating module in an LSTM contains four interacting layers.](.gitbook/assets/image%20%287%29.png)

![](.gitbook/assets/image%20%284%29.png)

### The Core Idea Behind LSTMs <a id="the-core-idea-behind-lstms"></a>

**The key to LSTMs is the cell state**, the horizontal line running through the top of the diagram.

**The cell state is kind of like a conveyor belt. It runs straight down the entire chain, with only some minor linear interactions. It’s very easy for information to just flow along it unchanged.**

![](.gitbook/assets/image%20%288%29.png)

The LSTM does have the ability to remove or add information to the cell state, carefully regulated by structures called gates.

**Gates are a way to optionally let information through.** They are composed out of a sigmoid neural net layer and a point-wise multiplication operation.

![](.gitbook/assets/image%20%285%29.png)

**The sigmoid layer outputs numbers between zero and one, describing how much of each component should be let through.** A value of zero means “let nothing through,” while a value of one means “let everything through!”

An LSTM has three of these gates, to protect and control the cell state.

