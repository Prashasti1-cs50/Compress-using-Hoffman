# HuffmanCompressor by PrashastiGarg
A  program that can losslessly compress and decompress files using Huffman Encoding


## Working


### Compression
1. Find frequencies of characters and generate a Huffman Tree
2. Traverse, and assign bitcodes to each character, and store in map
3. Using this info, create a bitstring of the input file
4. Read this bitstring in chunks of 8, using OR and SHIFT operations to get the byte
5. Write these bytes to file

### Decompression

1. Generate bitstring of compressed file
2. Go through each bit, comparing with the huffman codes, and appending characters to a vector on match
3. Write this vector to the file, which would be our uncompressed version



## Efficiency

Since we're now storing the table in the compressed file to decouple the compression and decompression phases, the size of our compressed file has increased. So for smaller files, it is actually worse to compress them, since we have to store the table information too. But as file size increases, so does our efficiency, to some extent.

Case in point:

  1. Uncompressed: 4 bytes
  2. Compressed: 128 bytes
  
  1. Uncompressed: 1100KB
  2. Compressed: 550KB
  
 
 As we can see, with a higher file size, we have a higher probability of better compression.





