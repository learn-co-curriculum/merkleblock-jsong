
# Merkleblock

## Test Driven Exercise


```python
# Exercise 3.1

from merkleblock import MerkleBlock, MerkleTree
from io import BytesIO
from helper import bytes_to_bit_field

class MerkleBlock(MerkleBlock):

    def is_valid(self):
        '''Verifies whether the merkle tree information validates to the merkle root'''
        # use bytes_to_bit_field on self.flags to get the flag_bits
        flag_bits = bytes_to_bit_field(self.flags)
        # set hashes to be the reversed hashes of everything in self.hashes
        hashes = [h[::-1] for h in self.hashes]
        # initialize the merkle tree with self.total
        merkle_tree = MerkleTree(self.total)
        # populate_tree with flag_bits and hashes
        merkle_tree.populate_tree(flag_bits, hashes)
        # check if the computed root [::-1] is the same as the merkle root
        return merkle_tree.root()[::-1] == self.merkle_root
```
