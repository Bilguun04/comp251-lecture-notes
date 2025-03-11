**Greedy - Huffman encoding**
Huffman encoding is a lossless data compression algorithm that uses a variable-length prefix code to represent character in a dataset. It is based on the idea of assigning shorter codes to more frequent characters and longer codes to less frequent characters, thereby reducing the overall size of the encoded data. Huffman encoding is widely used in compression formats like ZIP, JPEG, MP3.

---
**Key Concepts**
1. **Prefix Code:**
	- A node where no codeword is a prefix of another codeword.
	- This ensures that the encoded data can be uniquely decoded without ambiguity.
2. **Frequency-Based Encoding:**
	- Characters with higher frequencies are assigned shorter codewords.
	- Characters with lower frequencies are assigned longer codewords.
3. **Binary Tree Representation:**
	- Huffman encoding uses a binary tree (called Huffman tree) to represent the prefix codes.
	- The leaves of the tree represent the characters, and the path from the root to a leaf defines the codeword for that character.
---
**Steps to Build a Huffman Tree:**
1. **Calculate Frequencies:**
	- Determine the frequency of each character in the input data.
2. **Create Priority Queue:**
	- Create min-heap where each node represents a character and its frequency.
3. **Build the Huffman Tree:**
	- While there is more than once node in the heap:
		- Extract the two nodes with the smallest frequencies.
		- Create a new internal node with these two nodes as children and a frequency equal to the sum of their frequencies.
		- Insert the new node back into the heap.
	- The remaining node is the root of the Huffman tree.
4. **Assign Codewords:**
	- Traverse the Huffman tree from the root to each lead, assigning 0 for left branches and 1 for right branches.
	- The path from the root to a leaf defines the codeword for that character.
5. **Encode the Data:**
	- Replace each character in the input data with its corresponding codeword.
---
**Advantages of Huffman Encoding:**
1. **Optimal Prefix Code:**
	- Huffman encoding produces an optimal prefix code for a given frequency distribution.
2. **Efficient Compression:**
	- It achieves compression by assigning shorter codes to more frequent characters.
3. **Lossless:**
	- The original data can be perfectly reconstructed from the encoded data.