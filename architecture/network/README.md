# Network Architecture

Artifact Type: SPEC
Maturity Status: CONCEPT

Scope:

- Private mesh
- Segmentation
- Restricted management paths
- Identity-based connectivity

Principle:

Connectivity is an engineered control surface, not an always-open utility.

## Trust Zones (Design)

```mermaid
flowchart TD
    subgraph Untrusted
        PUB[Public Internet]
    end
    subgraph Perimeter
        MGMT[Management Access Point]
    end
    subgraph Mesh[Private Mesh - Trusted]
        N1[Node A]
        N2[Node B]
        N3[Node C]
    end
    subgraph Restricted[Restricted / Segmented]
        CTRL[Deterministic Control Segment]
    end

    PUB -->|authenticated only| MGMT
    MGMT -->|identity-gated| Mesh
    N1 --- N2
    N2 --- N3
    Mesh -->|policy-gated, one-way preferred| Restricted
```

This diagram describes intended segmentation only; no deployed topology exists in this repository. See [architecture/security/THREAT_MODEL.md](../security/THREAT_MODEL.md) for trust boundary analysis.
