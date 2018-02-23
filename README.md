# Ethereum VM (EVM) Opcodes and Instruction Reference

This page consolidates EVM opcode information from various places including the [yellow paper](http://gavwood.com/paper.pdf), [stack exchange](https://ethereum.stackexchange.com/questions/119/what-opcodes-are-available-for-the-ethereum-evm), [solidity source](https://github.com/ethereum/solidity/blob/c61610302aa2bfa029715b534719d25fe3949059/libevmasm/Instruction.h#L40), [parity source](https://github.com/paritytech/parity/blob/d365281cce919edc42340c97ce212f49d9447d2d/ethcore/evm/src/instructions.rs#L311), and [Manticore](https://github.com/trailofbits/manticore/blob/c6f457d72e1164c4c8c6d0256fe9b8b765d2cb24/manticore/platforms/evm.py#L590). Please file an issue or PR for any improvements.

| Opcode | Name | Description | Extra Info |
| --- | --- | --- | --- |
| `0x00` | STOP | Halts execution | - |
| `0x01` | ADD | Addition operation | - |
| `0x02` | MUL | Multiplication operation | - |
| `0x03` | SUB | Subtraction operation | - |
| `0x04` | DIV | Integer division operation | - |
| `0x05` | SDIV | Signed integer division operation (truncated) | - |
| `0x06` | MOD | Modulo remainder operation | - |
| `0x07` | SMOD | Signed modulo remainder operation | - |
| `0x08` | ADDMOD | Modulo addition operation | - |
| `0x09` | MULMOD | Modulo multiplication operation | - |
| `0x0a` | EXP | Exponential operation | - |
| `0x0b` | SIGNEXTEND | Extend length of two's complement signed integer | - |
| `0x0c` - `0x0f` | Unused | Unused | - |
| `0x10` | LT | Less-than comparision | - |
| `0x11` | GT | Greater-than comparision | - |
| `0x12` | SLT | Signed less-than comparision | - |
| `0x13` | SGT | Signed greater-than comparision | - |
| `0x14` | EQ | Equality comparision | - |
| `0x15` | ISZERO | Simple not operator | - |
| `0x16` | AND | Bitwise AND operation | - |
| `0x17` | OR | Bitwise OR operation | - |
| `0x18` | XOR | Bitwise XOR operation | - |
| `0x19` | NOT | Bitwise NOT operation | - |
| `0x1a` | BYTE | Retrieve single byte from word | - |
| `0x20` | SHA3 | Compute Keccak-256 hash | - |
| `0x21` - `0x2f`| Unused | Unused |
| `0x30` | ADDRESS | Get address of currently executing account      | - |
| `0x31` | BALANCE | Get balance of the given account | - |
| `0x32` | ORIGIN | Get execution origination address | - |
| `0x33` | CALLER | Get caller address | - |
| `0x34` | CALLVALUE | Get deposited value by the instruction/transaction responsible for this execution | - |
| `0x35` | CALLDATALOAD | Get input data of current environment | - |
| `0x36` | CALLDATASIZE | Get size of input data in current environment | - |
| `0x37` | CALLDATACOPY | Copy input data in current environment to memory | - |
| `0x38` | CODESIZE | Get size of code running in current environment | - |
| `0x39` | CODECOPY | Copy code running in current environment to memory | - |
| `0x3a` | GASPRICE | Get price of gas in current environment | - |
| `0x3b` | EXTCODESIZE | Get size of an account's code | - |
| `0x3c` | EXTCODECOPY | Copy an account's code to memory | - |
| `0x3d` | RETURNDATASIZE | Pushes the size of the return data buffer onto the stack | [EIP 211](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-211.md) |
| `0x3e` | RETURNDATACOPY | Copies data from the return data buffer to memory | [EIP 211](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-211.md) |
| `0x3f` | Unused | - |
| `0x40` | BLOCKHASH | Get the hash of one of the 256 most recent complete blocks | - |
| `0x41` | COINBASE | Get the block's beneficiary address | - |
| `0x42` | TIMESTAMP | Get the block's timestamp | - |
| `0x43` | NUMBER | Get the block's number | - |
| `0x44` | DIFFICULTY | Get the block's difficulty | - |
| `0x45` | GASLIMIT | Get the block's gas limit | - |
| `0x46` - `0x4f` | Unused | - |
| `0x50` | POP | Remove item from stack | - |
| `0x51` | MLOAD | Load word from memory | - |
| `0x52` | MSTORE | Save word to memory | - |
| `0x53` | MSTORE8 | Save byte to memory | - |
| `0x54` | SLOAD | Load word from storage | - |
| `0x55` | SSTORE | Save word to storage | - |
| `0x56` | JUMP | Alter the program counter | - |
| `0x57` | JUMPI | Conditionally alter the program counter | - |
| `0x58` | GETPC | Get the value of the program counter prior to the increment | - |
| `0x59` | MSIZE | Get the size of active memory in bytes | - |
| `0x5a` | GAS | Get the amount of available gas, including the corresponding reduction the amount of available gas | - |
| `0x5b` | JUMPDEST | Mark a valid destination for jumps | - |
| `0x5c` - `0x5f` | Unused | - |
| `0x60` | PUSH1 | Place 1 byte item on stack | - |
| `0x61` | PUSH2 | Place 2-byte item on stack | - |
| `0x62` | PUSH3 | Place 3-byte item on stack | - |
| `0x63` | PUSH4 | Place 4-byte item on stack | - |
| `0x64` | PUSH5 | Place 5-byte item on stack | - |
| `0x65` | PUSH6 | Place 6-byte item on stack | - |
| `0x66` | PUSH7 | Place 7-byte item on stack | - |
| `0x67` | PUSH8 | Place 8-byte item on stack | - |
| `0x68` | PUSH9 | Place 9-byte item on stack | - |
| `0x69` | PUSH10 | Place 10-byte item on stack | - |
| `0x6a` | PUSH11 | Place 11-byte item on stack | - |
| `0x6b` | PUSH12 | Place 12-byte item on stack | - |
| `0x6c` | PUSH13 | Place 13-byte item on stack | - |
| `0x6d` | PUSH14 | Place 14-byte item on stack | - |
| `0x6e` | PUSH15 | Place 15-byte item on stack | - |
| `0x6f` | PUSH16 | Place 16-byte item on stack | - |
| `0x70` | PUSH17 | Place 17-byte item on stack | - |
| `0x71` | PUSH18 | Place 18-byte item on stack | - |
| `0x72` | PUSH19 | Place 19-byte item on stack | - |
| `0x73` | PUSH20 | Place 20-byte item on stack | - |
| `0x74` | PUSH21 | Place 21-byte item on stack | - |
| `0x75` | PUSH22 | Place 22-byte item on stack | - |
| `0x76` | PUSH23 | Place 23-byte item on stack | - |
| `0x77` | PUSH24 | Place 24-byte item on stack | - |
| `0x78` | PUSH25 | Place 25-byte item on stack | - |
| `0x79` | PUSH26 | Place 26-byte item on stack | - |
| `0x7a` | PUSH27 | Place 27-byte item on stack | - |
| `0x7b` | PUSH28 | Place 28-byte item on stack | - |
| `0x7c` | PUSH29 | Place 29-byte item on stack | - |
| `0x7d` | PUSH30 | Place 30-byte item on stack | - |
| `0x7e` | PUSH31 | Place 31-byte item on stack | - |
| `0x7f` | PUSH32 | Place 32-byte (full word) item on stack | - |
| `0x80` | DUP1 | Duplicate 1st stack item | - |
| `0x81` | DUP2 | Duplicate 2nd stack item | - |
| `0x82` | DUP3 | Duplicate 3rd stack item | - |
| `0x83` | DUP4 | Duplicate 4th stack item | - |
| `0x84` | DUP5 | Duplicate 5th stack item | - |
| `0x85` | DUP6 | Duplicate 6th stack item | - |
| `0x86` | DUP7 | Duplicate 7th stack item | - |
| `0x87` | DUP8 | Duplicate 8th stack item | - |
| `0x88` | DUP9 | Duplicate 9th stack item | - |
| `0x89` | DUP10 | Duplicate 10th stack item | - |
| `0x8a` | DUP11 | Duplicate 11th stack item | - |
| `0x8b` | DUP12 | Duplicate 12th stack item | - |
| `0x8c` | DUP13 | Duplicate 13th stack item | - |
| `0x8d` | DUP14 | Duplicate 14th stack item | - |
| `0x8e` | DUP15 | Duplicate 15th stack item | - |
| `0x8f` | DUP16 | Duplicate 16th stack item | - |
| `0x90` | SWAP1 | Exchange 1st and 2nd stack items | - |
| `0x91` | SWAP2 | Exchange 1st and 3rd stack items | - |
| `0x92` | SWAP3 | Exchange 1st and 4th stack items | - |
| `0x93` | SWAP4 | Exchange 1st and 5th stack items | - |
| `0x94` | SWAP5 | Exchange 1st and 6th stack items | - |
| `0x95` | SWAP6 | Exchange 1st and 7th stack items | - |
| `0x96` | SWAP7 | Exchange 1st and 8th stack items | - |
| `0x97` | SWAP8 | Exchange 1st and 9th stack items | - |
| `0x98` | SWAP9 | Exchange 1st and 10th stack items | - |
| `0x99` | SWAP10 | Exchange 1st and 11th stack items | - |
| `0x9a` | SWAP11 | Exchange 1st and 12th stack items | - |
| `0x9b` | SWAP12 | Exchange 1st and 13th stack items | - |
| `0x9c` | SWAP13 | Exchange 1st and 14th stack items | - |
| `0x9d` | SWAP14 | Exchange 1st and 15th stack items | - |
| `0x9e` | SWAP15 | Exchange 1st and 16th stack items | - |
| `0x9f` | SWAP16 | Exchange 1st and 17th stack items | - |
| `0xa0` | LOG0 | Append log record with no topics | - |
| `0xa1` | LOG1 | Append log record with one topic | - |
| `0xa2` | LOG2 | Append log record with two topics | - |
| `0xa3` | LOG3 | Append log record with three topics | - |
| `0xa4` | LOG4 | Append log record with four topics | - |
| `0xa5` - `0xaf` | Unused | - |
| `0xb0` | JUMPTO | Tentitive [libevmasm has different numbers](https://github.com/ethereum/solidity/blob/c61610302aa2bfa029715b534719d25fe3949059/libevmasm/Instruction.h#L176)| [EIP 615](https://github.com/ethereum/EIPs/blob/606405b5ab7aa28d8191958504e8aad4649666c9/EIPS/eip-615.md) |
| `0xb1` | JUMPIF | Tentitive | [EIP 615](https://github.com/ethereum/EIPs/blob/606405b5ab7aa28d8191958504e8aad4649666c9/EIPS/eip-615.md) |
| `0xb2` | JUMPSUB | Tentitive | [EIP 615](https://github.com/ethereum/EIPs/blob/606405b5ab7aa28d8191958504e8aad4649666c9/EIPS/eip-615.md) |
| `0xb4` | JUMPSUBV | Tentitive | [EIP 615](https://github.com/ethereum/EIPs/blob/606405b5ab7aa28d8191958504e8aad4649666c9/EIPS/eip-615.md) |
| `0xb5` | BEGINSUB | Tentitive | [EIP 615](https://github.com/ethereum/EIPs/blob/606405b5ab7aa28d8191958504e8aad4649666c9/EIPS/eip-615.md) |
| `0xb6` | BEGINDATA | Tentitive | [EIP 615](https://github.com/ethereum/EIPs/blob/606405b5ab7aa28d8191958504e8aad4649666c9/EIPS/eip-615.md) |
| `0xb8` | RETURNSUB | Tentitive | [EIP 615](https://github.com/ethereum/EIPs/blob/606405b5ab7aa28d8191958504e8aad4649666c9/EIPS/eip-615.md) |
| `0xb9` | PUTLOCAL | Tentitive | [EIP 615](https://github.com/ethereum/EIPs/blob/606405b5ab7aa28d8191958504e8aad4649666c9/EIPS/eip-615.md) |
| `0xba` | GETLOCAL | Tentitive | [EIP 615](https://github.com/ethereum/EIPs/blob/606405b5ab7aa28d8191958504e8aad4649666c9/EIPS/eip-615.md) |
| `0xbb` - `0xef` | Unused | - |
| `0xf0` | CREATE | Create a new account with associated code | - |
| `0xf1` | CALL | Message-call into an account | - |
| `0xf2` | CALLCODE | Message-call into this account with alternative account's code | - |
| `0xf3` | RETURN | Halt execution returning output data | - |
| `0xf4` | DELEGATECALL | Message-call into this account with an alternative account's code, but persisting into this account with an alternative account's code | - |
| `0xf5` - `0xf9` | Unused | - | - |
| `0xfa` | STATICCALL | Similar to CALL, but does not modify state | - |
| `0xfb` | CREATE2 | Create a new account and set creation address to `sha3(sender + sha3(init code)) % 2\*\*160` | - |
| `0xfc` | TXEXECGAS | Not in yellow paper FIXME | - |
| `0xfd` | REVERT | Stop execution and revert state changes, without consuming all provided gas and providing a reason | - |
| `0xfe` | INVALID | Designated invalid instruction | - |
| `0xff` | SELFDESTRUCT | Halt execution and register account for later deletion | - | 
