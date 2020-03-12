# Proposal: Local private key protection

Author(s): gjj

Last updated: 2020-03-12

Discussion at https://github.com/xuperchain/xuperchain/pull/NNN.

## Abstract

Solve private key protection by locking and unlocking account

## Background

at present the private key of local account is plaintext on disk. it is not safe for production environments.

## Proposal

[A precise statement of the proposed change.]

## Rationale

[A discussion of alternate approaches and the trade offs, advantages, and disadvantages of the specified approach.]

## Compatibility

[A discussion of the change with regard to the compatibility guidelines]

## Implementation

1.this "./xchain-cli account newkeys" command adds a flag called "encryptkey". when "./xchain-cli account newkeys ... --encryptkey true" is used, a passcode(this passcode is a 16 bit string obtained through the private key and timestamp hash) will be used for AES encryption of the private key.

2.return to passcode for users to save

3.Three RPC interfaces are developed,which are unlocking、locking and obtaining plaintext private key from memory

4.（1）The unlocking interface has three parameters: keypath、 passcode and expiredtime. 

（2）Read the address corresponding to the keypath from the local disk. 

（3）The address and passcode obtained are spliced with a salt value to get a string. 

（4）Hash the string to get the final string. 

（5）The final string is the key value corresponding to the plaintext private key stored in memory.

（6）Read the ciphertext private key in keypath, use passcode for AES decryption to get the plaintext private key, and save it in memory together with the key obtained above

（7）At the same time, set the sliding window for the kV saved in the memory, and delete the kV in case of timeout

（8）When the unlocking method is called again, if the clear text private key of the keypath still exists in memory, the time window will be reset


5. Only keypath and passcode are needed to lock the interface. The purpose is to clear the plaintext private key saved in the memory of the account


6. Only keypath and passcode are needed to obtain the plaintext private key interface. The purpose is to obtain the plaintext private key saved in the memory of the account


7. Two commands are provided: lock command "./xchain-cli account lock" and unlock command "./xchain-cli account unlock"
"./xchain-cli account lock --keyPath data/keys --passcode fjd9c8bj3kvidj3n" --> call the lock interface
"./xchain-cli account unlock --keyPath data/keys --passcode fjd9c8bj3kvidj3n --expiredTime 5" --> call the unlock interface


8.When a transaction is initiated, such as a transfer, the privatekey of keypath is obtained in the readprivatekey method in the source code for JSON parsing of ecdsaprivatekey. If the parsing error indicates that the privatekey is encrypted by AES, the RPC interface that obtains the plaintext private key of the account needs to be called to obtain the private key for transaction signature

9.If the plaintext private key of the account in memory does not exist, use point 7 to unlock the account


## Open issues (if applicable)

[A discussion of issues relating to this proposal for which the author does not
know the solution. This section may be omitted if there are none.]