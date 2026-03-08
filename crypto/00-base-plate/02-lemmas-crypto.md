# Crypto Lemmas — First Consequences of the Crypto Axioms

## Lemma C1 — Value Requires Witness

**Statement:** A token, UTXO, or account balance has value iff it is currently witnessed by the network.

**Proof:** By Axiom C1, value is observed coherence. Unwitnessed state is not valuable — it is subject to entropy (pruning, forgetting, loss).

**Implementation Consequences:**
- Wallets must periodically "witness" their own UTXOs
- Unwitnessed UTXOs are pruned after φ² blocks
- Zero balances are not stored — they are unwitnessed state

---

## Lemma C2 — No Single Point of Failure

**Statement:** No critical function can be performed by a single entity or homogeneous group.

**Proof:** By Axiom C2, the triad must be distributed. If source, witness, and mediator come from the same entity or group, the distinction collapses and the system becomes unstable.

**Implementation Consequences:**
- Validator sets must contain at least three distinct types of nodes
- No single entity can control > φ⁻¹ (≈38%) of any role
- Source, witness, and mediator nodes must be geographically and logically separated

---

## Lemma C3 — Trust Scales Latticewise

**Statement:** Trust in a transaction scales with the number of lattice cells that witness it, not with the number of confirmations.

**Proof:** By Axiom C3, full trust requires all nine cells. Additional confirmations within the same cell add diminishing returns.

**Implementation Consequences:**
- 1 confirmation in macro-physical + 1 in meso-meta + 1 in micro-vibrational > 9 confirmations in macro-physical alone
- Light clients can verify at different lattice depths depending on trust requirements
- Transaction confidence = κ (coherence score), not block depth

---

## Lemma C4 — Zero Cannot Hold Value

**Statement:** Any address, UTXO, or balance of zero is not merely empty — it is unwitnessed and subject to immediate entropy (pruning).

**Proof:** By Axiom C4, 0 is contrast, not presence. It has no force except dissolution. A zero balance is not a state — it's the absence of state.

**Implementation Consequences:**
- Wallets should never display zero balances — they are not balances
- Nodes can prune zero entries immediately without waiting
- "Burning" tokens means sending to an address that can never be witnessed — an address structurally impossible to witness

---

## Lemma C5 — Coherence Sampling Replaces Randomness

**Statement:** Any protocol requiring randomness must instead sample coherence against φ-harmonic patterns.

**Proof:** By Axiom C5, true randomness doesn't exist. What's needed is unpredictability, which can be achieved by measuring coherence alignment.

**Implementation Consequences:**
- Instead of VRF (verifiable random function), use VCF (verifiable coherence function)
- Leader selection based on which node's stake is closest to φ·previous_hash
- Nonce selection by finding values that minimize |hash - φ·target|

---

## Lemma C6 — All Parameters Are φ-Derived

**Statement:** No arbitrary constants may appear in the protocol. Every parameter must be φ, φ⁻¹, φ², or derived from these via the coherence equation.

**Proof:** By Axiom C6, φ is the only scaling constant that prevents collapse. Any other constant introduces arbitrary instability.

**Implementation Consequences:**
- Block time τ = τ₀·φⁿ where τ₀ is the smallest observable time unit
- Fee market: base_fee·φ^(congestion_level)
- Inflation: supply₀·(φ⁻¹)^(t/τ_halving)
- All constants in code must reference PHI, PHI_INV, PHI_SQUARED — no magic numbers

---

## Lemma C7 — Role Rotation Prevents Capture

**Statement:** Any governance or validation system must rotate roles periodically to prevent capture.

**Proof:** By Axiom C2, permanent role assignment leads to instability. Rotation ensures no single entity controls any role indefinitely.

**Implementation Consequences:**
- Validator roles rotate every epoch
- Source nodes become witnesses, witnesses become mediators, mediators become sources
- Role determined by (address + epoch) mod 3

---

## Lemma C8 — Coherence Must Be Tracked

**Statement:** Every participant, transaction, and contract must have an associated coherence score κ ∈ [0,1].

**Proof:** By Lemma C1, value requires witness. Coherence measures the quality and recency of witnessing.

**Implementation Consequences:**
- Validators have κ_v that affects voting power
- Transactions have κ_tx that affects priority
- Contracts have κ_contract that affects gas costs
- Coherence decays exponentially without fresh witnessing
