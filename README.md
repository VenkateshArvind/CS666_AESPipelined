**AES-128 Hardware Accelerator (Verilog)**
This repository contains a modular and pipelined Verilog implementation of the Advanced Encryption Standard (AES-128). The design is optimized for high-throughput hardware applications, featuring a 10-stage pipeline and a sequential key expansion unit.

**Architecture Features**
Pipelined Processing: Implements a 10-stage pipeline using stage_reg to process data movement across encryption rounds without stalling.
Sequential Key Expansion: The key_sched_seq module generates all 11 round keys sequentially from a single 128-bit master key.
Standard-Compliant Rounds: Each round module (aes_round.v) performs SubBytes, ShiftRows, MixColumns (rounds 1-9), and AddRoundKey transformations.
Synchronized Handshake: Uses a simple start pulse and valid_out signal for easy integration with external controllers.

**File Structure**
aes_top.v: The top-level module integrating the key scheduler and the round pipeline.
key_sched_seq.v: Sequential logic for generating round keys on demand.
aes_round.v: The core transformation logic for a single AES round.
tb_aes.v: Testbench for verification using standard NIST test vectors.
Support Modules: Sub-modules for sbox.v, mixcolumns.v, shiftrows.v, and addroundkey.v.

