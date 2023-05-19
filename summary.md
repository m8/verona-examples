## Verona ABI

- Objects can be of various types, including numeric (`U32`, `F64`, `Bool`), pointers to interfaces or classes, type unions, etc.
- Verona's memory model is based on **isolated regions**.
  - sentinel objects (`iso`): point to the entry point of the region
  - mutable references (`mut`)
  - Immutable references (`imm`)
  - The Verona runtime guarantees no more than one behaviour has access to the same region at any time, avoiding concurrent mutation problems.
- **Region:** A region is a tree of related objects, not necessarily contiguous in memory.
- **Standard types:**
  * `Bool`: bit pattern 0 or 1. The storage is usually 1 byte but can be different.
  * `U8`, `U16`, ... `U128`: power-of-two-bits, unsigned, on the platform's native endian.
  * `I8`, `I16`, ... `I128`: power-of-two-bits, 2's-complement, on the platform's native endian.
  * `F32`, `F64`: IEEE-754 (binary) floating point numbers.

