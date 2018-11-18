
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
        # set hashes to be the reversed hashes of everything in self.hashes
        # initialize the merkle tree with self.total
        # populate_tree with flag_bits and hashes
        # check if the computed root [::-1] is the same as the merkle root
        pass
```
