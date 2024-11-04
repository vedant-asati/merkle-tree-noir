# Merkle Tree Transaction Simulator

This project simulates a single transaction on a Merkle tree. The transaction involves a sender represented by the Merkle tree leaf at index 2 and a receiver at leaf index 10. It showcases how to use Pedersen hashing in Noir circuits to construct a Merkle tree and validate a transaction using zero-knowledge proofs.

## Project Overview

The code generates a Merkle tree with 16 leaves, where each leaf is a Pedersen hash of the integers 1 through 16. Noir's Pedersen hashing functions are used to compute the hashes and construct the Merkle tree, enabling a proof of transaction that adheres to zk-SNARK principles.

### Key Components

- **Merkle Tree Construction**: Located in the `merkletreerust` directory, this component builds the Merkle tree from the hashed values of each leaf.
- **Pedersen Hash Functions**:
  - `pedersen1noir`: Generates a Pedersen hash of a single field element.
  - `pedersen2noir`: Generates a Pedersen hash of two field elements, used for hashing internal nodes.
- **Proof Circuit**: The circuit for proving the transaction is defined in the `merkletreenoir` directory.

## Prerequisites

Ensure the following tools are installed on your system:

- [Noir](https://noir-lang.org/)
- [Rust](https://www.rust-lang.org/)
- `bb` tools

## Running the Simulation

1. **Navigate to the `merkletreerust` directory**:

   ```bash
   cd merkletreerust
   ```

2. **Run the simulation**:

   ```bash
   cargo run
   ```

   This command will:
   - Build the Merkle tree with 16 leaves.
   - Use Noir's Pedersen hash functions to hash each leaf.
   - Generate the witness in `merkletreenoir/Prover.toml`.
   - Generate the proof file in `merkletreenoir/target/proof`.

## Output

The simulation will produce the following files:

- **Witness File**: Located at `merkletreenoir/Prover.toml`.
- **Proof File**: Located at `merkletreenoir/target/proof`.

## File Structure

- **merkletreerust**: Contains the main Rust code to build and simulate the Merkle tree transaction.
- **merkletreenoir**: Contains the Noir circuit files for proving the transaction using zero-knowledge proofs.
- **pedersen1noir**: Noir function for hashing a single field element.
- **pedersen2noir**: Noir function for hashing two field elements.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

