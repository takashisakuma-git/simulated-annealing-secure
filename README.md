# Simulated Annealing Secure: Fully Private SA Protocol for Multi-Issue Negotiation

This repository contains the source code for the secure multi-party computation (MPC) 
programs used in the following paper:

> Takashi Sakuma, Shun Okuhara, and Akinori Kawachi,  
> "Scalability Evaluation of Secure Computations for Multi-Issue Negotiation,"  
> IEICE Transactions on Information and Systems, Vol.E109-D, No.9, 2026.  
> DOI: 10.1587/transinf.2025DKP0013

## Overview

This repository implements fully private negotiation protocols based on 
secure multi-party computation (MPC), in which all intermediate states 
generated during the negotiation process are concealed.
The protocols are implemented using the [MP-SPDZ framework](https://github.com/data61/MP-SPDZ).

## Files

| File | Description |
|------|-------------|
| `knapsack_simulated_annealing_our_general.mpc` | Proposed fully private SA protocol |
| `knapsack_simulated_annealing_our_general_timed.mpc` | Proposed fully private SA protocol with timer-based breakdown |
| `knapsack_simulated_annealing_pre_general.mpc` | FIK-based SA protocol (baseline) |

## Experimental Environment

All experiments were conducted on the following environment:

- **Machine**: MacBook Pro (14-inch)
- **Processor**: Apple M3 Pro (11-core CPU, 14-core GPU, 16-core Neural Engine)
- **Memory**: 18 GB unified memory
- **Storage**: 512 GB SSD
- **OS**: macOS
- **MPC Framework**: [MP-SPDZ](https://github.com/data61/MP-SPDZ) v0.4.1
- **Protocol**: MASCOT, Semi, Shamir

## Usage

1. Install MP-SPDZ following the [official instructions](https://github.com/data61/MP-SPDZ#readme).

2. Copy the `.mpc` files to the `Programs/Source/` directory of MP-SPDZ.

3. Compile the program:
```bash
python compile.py knapsack_simulated_annealing_our_general
```

4. Run the protocol (example with MASCOT, 17 parties):
```bash
./mascot.sh -N 17 -p 0 knapsack_simulated_annealing_our_general
```

## Related Repository

The source code for the fully private hill-climbing protocol (FPHC) is available at:  
https://github.com/takashisakuma-git/hill-climbing-secure

## License

MIT License

## Contact

Takashi Sakuma  
Graduate School of Engineering, Mie University
