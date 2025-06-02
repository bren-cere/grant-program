# Built-in encryption for Secure Data Storage 🔑
This document outlines the details of the program, including its objectives, challenges, proposed solutions, deliverables, and resources. Below is the index for easy navigation:

---

## 📚 Index

1. [Introduction 🌟](#introduction-)
2. [Objective 🎯](#objective-)
3. [Key Concepts/Keywords 📝](#key-conceptkeywords-)
4. [Existing System ⚙️](#existing-system-)
5. [Deliverables 📦](#deliverables-)
6. [Quick Start Guide 🚀](#quick-start-guide-)
7. [Resources 📚](#resources-)

---

## Introduction 🌟

Cere’s Decentralized Data Cluster (DDC) SDK currently lets developers store and retrieve raw bytes across an untrusted, peer‑to‑peer network. Today, any encryption must be hand‑rolled by each developer, which is error‑prone and non‑uniform. This grant task will embed **client‑side encryption** directly into:

- The **DDC SDK** core

- The **Playground** (for live testing during development)

- The **DDC CLI**

so that **“privacy by default”** becomes a seamless part of every upload/download flow.

---

## Objective 🎯

Enhance the DDC SDK by introducing built-in optional encryption capabilities, enabling automatic encryption during uploads and decryption during downloads. Update DDC SDK Playground and DDC CLI to showcase the optional encryption feature. 

---

## Key Concepts/Keywords 📝

- **DDC (Decentralized Data Cluster):** Blockchain-based storage solution.
- **DDC SDK:** A development kit used by developers to create applications that interact with the CERE infrastructure. It provides a set of modules and methods that allow seamless integration with the Cerebellum Network's decentralized data cloud (DDC).
- **Storage Node:** A fundamental component of the DDC that enables storing, reading, and searching data, like objects, files, and documents within the Cere Network.
- **CID:** Content Identifier, based on the content’s cryptographic hash label used to point to material. It doesn't indicate where the content is stored, but it forms an address based on the content itself. CIDs are short, regardless of the size of their underlying content.
- **Piece:** An abstraction that signifies a unit of data stored in the DDC. It doesn't have a fixed size and can represent fully logically complete data or a part of it.
- **CNS:** Content Name System to associate CIDs with human-readable names.
- **DAG:** Directed Acyclic Graph stored on DDC is used to establish data relationships between different pieces of data.

---

## Encryption ⚙️

### Symmetric

![symmetric_encryption](./symmetric_encryption.png)


---

## Deliverables 📦

This RFP seeks to implement client-side encryption capabilities directly into the DDC SDK, allowing developers to encrypt data before it reaches DDC storage nodes and decrypt it upon retrieval.

## **Phase 1: Core Implementation (Required Demonstration)**

**Duration**: 2 days maximum  
**Objective**: Demonstrate technical competency and understanding of the core encryption challenge

**Design**
  - Define a `Cipher` interface:
    ```ts
    export interface Cipher {
      encrypt(data: Uint8Array): Promise<Uint8Array>;
      decrypt(data: Uint8Array): Promise<Uint8Array>;
    }
    ```  
  - Extend `DdcClientOptions` with an optional `cipher?: Cipher` field.

**Implementation**
  - Store the provided `cipher` in `DdcClient`’s constructor.
  - In `upload()`, wrap outgoing bytes with `cipher.encrypt()`.
  - In `download()`, apply `cipher.decrypt()` before returning the payload.

**Verification**
  - Unit tests using a mock XOR cipher to validate both `encrypt` and `decrypt`.
  - Integration test: round‑trip a small sample file and assert byte‑for‑byte equality.

### **Specific Requirements**

You must implement a working encryption/decryption module that integrates with the existing DDC SDK structure and demonstrates the following:

1. **Encryption Algorithm**: Implement **AES-256-GCM** encryption (this is mandatory, not developer's choice)
2. **Key Management**: Basic key derivation using a user-provided passphrase or key
3. **Integration Points**: Hook into the DDC Client's `store()` and `read()` methods
4. **Demonstration**: Working code that encrypts data before storage and decrypts after retrieval

### **Technical Specifications**

- **Language**: TypeScript/JavaScript
- **Target Package**: `@cere-ddc-sdk/ddc-client`
- **Encryption Standard**: AES-256-GCM with proper nonce handling
- **Key Derivation**: PBKDF2 with minimum 100,000 iterations
- **Data Format**: Encrypted payload must remain valid for DDC storage

### **Deliverables for Phase 1**

1. **Working Code**: Functional encryption/decryption module
2. **Integration**: Modified DDC Client with encryption hooks
3. **Demo Script**: Simple demonstration showing end-to-end encryption workflow
4. **Documentation**: Clear explanation of your implementation approach

### **Success Criteria**

- Code demonstrates direct developer involvement (not outsourced work)
- Encryption/decryption works correctly with test data
- Integration doesn't break existing DDC Client functionality
- Clear understanding of the technical challenges involved

### Phase 2: Playground Encryption Controls
**Duration**: 2 days maximum  
**Objective**: Integrate the new functionality into the DDC Playground

**Design**
  - Build a demo AES‑GCM `Cipher` that accepts a user‑supplied key string.
  - UI requirements:
    - **Enable Encryption** checkbox
    - **Encryption Key** text input
    - **Download & Decrypt** button

**Implementation**
  - Add the above controls into the React + Vite playground app.
  - When toggled on, instantiate the AES‑GCM cipher and pass it to all SDK calls.

**Verification**
  - Manual test: upload a “Hello world!” file with encryption enabled; confirm that the direct download is unintelligible.
  - Click “Download & Decrypt” to retrieve and verify the original plaintext.

---

### Phase 3: CLI Encryption Flags
**Duration**: 2 days maximum  
**Objective**: Integrate the new functionality into the CLI

**Design**
  - Introduce two new flags for `upload` and `download` commands:
    - `--encrypt` (boolean)
    - `--key <hex>` (string)

**Implementation**
  - Parse `--encrypt` and `--key` in the CLI entrypoint (e.g. via `commander` or `yargs`).
  - When flags are provided, build the AES‑GCM cipher and pass it into the SDK’s `upload()`/`download()`.

**Verification**
  - Run `ddc upload ./file.txt --encrypt --key abc123 --network testnet` and ensure the object on the network is encrypted.
  - Run `ddc download <CID> --encrypt --key abc123 --network testnet` and verify the decrypted output matches the original file.

---

## Quick Start Guide 🚀

### 1. Setup environment

1. Clone GitHub repository: [`cere-ddc-sdk-js`](#)
2. Download and install Node.js **v18.17.1** [Node.js – Download Node.js](https://nodejs.org/)

### 2. Run DDC SDK Playground

1. Install dependencies:
    ```bash
    npm i
    ```
2. Build packages and playground application
    ```bash
    npm run build
    ```
3. Run playground application
    ```bash
    npm run playground
    ```
4. Open [http://localhost:5174/](http://localhost:5174/)
5. Upload and download file to ensure it’s working
   1. Keep default Seed phrase as is and click `Continue` button
   2. Select `Testnet` and click `Continue` button
   3. Click `Skip`
   4. Keep default Cluster (`0x825...`) and use existing bucket `573062`
   5. Click `Skip`
   6. Select file on your local file system you would like to upload and click `Continue`
   7. Click a blue link to download a file

### 3. Run DDC CLI

1. Install `ddc-cli` package
    ```jsx
    npm install -g @cere-ddc-sdk/cli
    ```
2. Install `npx`

    ```jsx
    npm install -g npx
    ```

3. Put any file you would like to upload to the same directory from where you execute commands
4. Upload file

    ```jsx
    npx @cere-ddc-sdk/cli upload ./hello-world.txt network=testnet --signer="hybrid label reunion only dawn maze asset draft cousin height flock nation" --bucketId=573062
    ```

5. More details and examples you can find here: https://github.com/Cerebellum-Network/cere-ddc-sdk-js/blob/main/packages/cli/README.md
---

## Resources 📚
- DDC SDK (Monorepo): [GitHub Link](https://github.com/Cerebellum-Network/cere-ddc-sdk-js)
- CLI Package: [GitHub Link](https://github.com/Cerebellum-Network/cere-ddc-sdk-js/tree/main/packages/cli)
- Playground App: [GitHub Link](https://github.com/Cerebellum-Network/cere-ddc-sdk-js/tree/main/playground)
