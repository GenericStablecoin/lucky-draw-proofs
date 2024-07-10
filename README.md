# lucky-draw-proofs

#### We ensure the fairness of the lucky draw through the following steps:

1. We call the generateSeedOf method of the LuckyDrawProofs contract to generate a fair random seed. This seed is the hash value of a block from the 128 blocks before the current transaction.

2. Using the soliditySha3 method from web3.js, we calculate the user’s ticket based on the user and the generated seed.

3. We arrange all the tickets in ascending order. The top N users (as specified by the event) are considered winners.

4. Finally, we use the sorted ticket array to create a Merkle tree, then call the setRoot method of the LuckyDrawProofs contract to store the root of the tree on the blockchain. Anyone can access the proof files in this repository and verify the data on-chain.

---

LuckyDrawProofs contract:

Arbitrum: [0x53B578C6480df494f8F7f6b1f80257aC87f9c202](https://arbiscan.io/address/0x53B578C6480df494f8F7f6b1f80257aC87f9c202)
