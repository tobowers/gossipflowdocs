# Gossip3

## Sync

### High level
```mermaid
sequenceDiagram
SignerA ->>+ SignerB: GetSyncer
SignerB ->> SignerA: Address of Syncer
SignerA ->> SignerB: Difference Strata
SignerB ->> SignerA: Sized IBF
Note left of SignerA: Decodes IBF
SignerA ->> SignerB: RequestKeys
Note over SignerA, SignerB: The below happens in parallel
SignerB ->> SignerA: Send wanted keys
SignerA ->> SignerB: Send wanted keys
```

### When too busy
```mermaid
sequenceDiagram
SignerA ->>+ BusySigner: GetSyncer
BusySigner--x- SignerA: Too busy
```

### With actors
```mermaid
sequenceDiagram
participant AG as A/Gossiper
participant AS as A/Storage
participant AOS as A/ObjectSender
participant AP as A/PushSyncer
participant BT as B/Tupelo
participant BG as B/Gossiper
participant BP as B/PushSyncer
participant BS as B/Storage
participant BOS as B/ObjectSender
AG ->> AP: DoOneSync
AP ->> BT: GetRemoteSyncer
BT ->> BG: Forward GetRemoteSyncer
BG ->> AP: ActorPID for syncer
AP ->> AS: GetStrata
AS ->> AP: strata
AP ->> BP: strata
BP ->> BS: get IBF
BS ->> BP: IBF
BP ->> AP: IBF
AP ->> BP: KeyRequest with A/Storage PID
AP ->> AOS: SendKeys
AOS ->> AS: GetKeys
AS ->> AOS: Keys
AOS ->> BS: Objects
BOS ->> BS: Get Keys
BS ->> BOS: Keys
BOS ->> AS: Objects
```

## Actor Communication
### A valid transaction with no flaws

```mermaid
sequenceDiagram
memPool ->> tupelo: new transaction
tupelo ->> verifier pool: transaction
verifier pool ->> tupelo: is valid
tupelo ->> conflict set router: transaction
conflict set router ->> conflict set: transaction
conflict set ->> signature generator: transactionWrapper
signature generator ->> conflict set: signatureWrapper
conflict set ->> signature sender: signatureWrapper
conflict set ->> conflict set: is done?
conflict set ->> conflict set router: currentStateWrapper
conflict set router ->> tupelo: currentStateWrapper
tupelo ->> currentStateStore: currentStateWrapper
tupelo ->> commitStore: currentStateWrapper
tupelo ->> memPool: bulk remove conflict set
```


## New Transaction
```mermaid
graph TD
subgraph Transaction Verification
  MemPool -- New Transaction --> Tupelo
  Tupelo --> ValidatorPool
  Tupelo -- If Not Valid --> Delete[Delete Key]
end
  ValidatorPool -- IsValid? --> Tupelo
  Tupelo -- If Valid --> ConflictSetRouter
  ConflictSetRouter --> ConflictSet
  ConflictSet -- If haven't already signed a diff transaction --> SignatureGenerator
  SignatureGenerator --> ConflictSet
  ConflictSet --> SignatureSender
  SignatureSender --> RewardsCommittee((Rewards Committee))
```

## New Signature
```mermaid
graph TD
Tupelo --> ConflictSetRouter
ConflictSetRouter --> ConflictSet
```

## ConflictSet logic
### New Transaction
```mermaid
graph TD
Transaction -->  D1{Already Signed?}
D1 -- Yes --> SaveTransaction
D1 -- No --> SignTransaction
SaveTransaction --> Check{Check state}
SignTransaction --> send[Send sig to rewards committee]
SignTransaction --> send2[Send sig to self]

```
### New Signature
```mermaid
graph TD
Signature --> CS(Conflict Set)
CS --> Check{Check state}
```

### Check State
```mermaid
graph TD
Check -- done --> CreateCurrentStateWrapper
CreateCurrentStateWrapper --> SendToSelf
Check{Check state} -- deadlocked --> reset[choose lowest transaction, erase all other state, sign that trans]
```

### Current State Wrapper
```mermaid
graph TD
CurrentState --> verified{Is Valid?}
verified -- yes --> ConflictSetRouter[send to parent and switch to done state]
ConflictSetRouter --> Tupelo
verified -- no --> ConflictSetRouter2[send to parent, stay processing]
```
