**Title**: Separable Reversible Data Hiding in Encrypted JPEG Bitstreams

Tags: Steganography, Jpeg, Reversible Data Hiding in Encrypted Images(RDH-EI)

**Problem**

This paper focuses on RDH in encrypted JPEG bitstream, with separable extraction capability, high embedding capacity, and secure encrypotion.

**Procedure**

1. enciphering JPEG bitstreams
2. embed additional bits
3. recover the original image

## Related Work 

**Three Delegate in RDH**

content owner: encrypt image with a key

data hider: embed additional messages into the encrypted image

recipient: losslessly recover the original image using the key

A. Separable RDH-EI

messages can be extracted without revealing the image content

# Proposed Framwork

1. Content Owner generates a ciphertext bitstream after syntax parsing and encryption. 文件大小没变
2. server parses the bitstream and hides additional messages using a **embedding key**. Marked encrypted bitstream is constucted. 文件大小和格式都没变. Server can extract bitstream using the embedding key.
3. Recipient只有同时拥有encryption key和embedding key才能extract messages和images

* Encryption and Decryption

  **Target**: keep size, avoid leakage

  JPEG Format consists of Start-of-image maker, JPEG Header, Entropy Encoded Data, End-of-image
  
  Entropy Encoded Data(segments): DC coefficient, AC coefficient, End-of-block. 
  
  DCC: Huffman code(DCH) + Appended bits(DCA)
  
  ACC: ACH + ACA
  
  **Procedure**
  
  A private encryption key K<sub>enc</sub>, pseudo-randomly selects entropy-coded segments corresponding to L blocks from the entropy encoded data, where 1<L<N. Reconstruct a new bitstream including an **SOI** marker, a new JPEG header, entropy-coded segment of the selected L blocks, an **EOI** marker and padding bits. Remaining N-L blocks are used to construct the padding bits. 
  
  ![](https://tva1.sinaimg.cn/large/007S8ZIlgy1gguanlprhtj30rz085q3y.jpg)
  
  **Note** that no Huffman codes are destroyed. Further, the enryption key stream K=[k<sub>1</sub>, k<sub>2</sub>, ..., k<sub>M</sub>] using stream cipher **algs** such as **RC4** and **SEAL**. The padding bits are then encypted to p<sub>i</sub><sup>'</sup>=p<sub>i</sub> $\oplus$ 
  
  
  
  
  
  
  
  





