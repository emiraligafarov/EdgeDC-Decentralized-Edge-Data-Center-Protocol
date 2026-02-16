# EdgeDC

Decentralized Edge Data Center Protocol.

EdgeDC transforms distributed devices into a virtual data center using peer-to-peer architecture.

## Vision

Instead of relying on centralized hyperscale facilities, EdgeDC enables:

- Distributed storage
- Edge-based compute
- Autonomous node participation
- Self-healing network topology

## Architecture

Each node:
- Stores chunks of data
- Replicates across peers
- Uses consistent hashing for ownership
- Communicates via REST P2P

No central server.

## Quick Start

### 1. Install

python -m venv venv
source venv/bin/activate
pip install -r requirements.txt

### 2. Run first node

HOST=127.0.0.1 PORT=8000 DATA_DIR=./n1 uvicorn node:app --host 127.0.0.1 --port 8000

### 3. Run second node

HOST=127.0.0.1 PORT=8001 DATA_DIR=./n2 BOOTSTRAP=http://127.0.0.1:8000 uvicorn node:app --host 127.0.0.1 --port 8001

### 4. Upload file

NODE=http://127.0.0.1:8000 python client.py upload ./file.zip

## API

GET /health
PUT /chunk/{id}
GET /chunk/{id}
POST /peers

## Roadmap

- Cryptographic identity
- Proof-of-storage
- WASM compute sandbox
- Token-based incentive layer
- Sybil resistance
- AI distributed training layer

## Warning

This is a research MVP.
Not production ready.
No security guarantees.
