# ERICA Knowledge Graph Navigator

Artifact Type: KNOWLEDGE-ENGINEERING APPLICATION CANDIDATE

Project Status: MIXED MATURITY

Maturity Status: IMPLEMENTATION (historical inventory; verification unresolved)

Public Repository Status: INVENTORY SUMMARY ONLY

## System Role

The Knowledge Graph Navigator is a historical knowledge-navigation and relationship-exploration candidate discovered in the imported project inventory.

It is related to the ERICA knowledge architecture, but it is not evidence that the current ERICA Knowledge Graph is implemented or that the candidate is integrated with ERICA Library.

## Historical Inventory

The 2026-11-13 source inventory recorded:

- 10 discovered files.
- 8 Python files.
- 1 test-related file.
- 1 project manifest.

The inventory is not a build or runtime verification. Source contents, schema compatibility, graph persistence, provenance behaviour, and test results were not established by that inventory alone.

## Integration Boundary

Potential overlap exists with ERICA Library, Knowledge Forge, and the target Knowledge Graph. Before reuse, determine:

- The graph entity and relationship model.
- Source identity and locator preservation.
- Whether edges represent observed facts, derived assertions, or hypotheses.
- Persistence and ownership boundaries.
- Import/export and migration semantics.
- How review and correction propagate to derived graph views.

Do not create a second authoritative knowledge database merely to reuse the navigator UI or graph model.

## Next Verification Gates

1. Locate and pin the source tree and revision.
2. Inspect the package, dependencies, schema, and tests.
3. Run a bounded fixture-based test.
4. Compare the graph schema with the ERICA Library source/provenance model.
5. Decide whether to ADAPT, REFERENCE, or REJECT individual mechanisms.
6. Verify graph relationships remain traceable to immutable source locators.

No live graph runtime, integrated Library workflow, or public reproducible implementation is claimed.
