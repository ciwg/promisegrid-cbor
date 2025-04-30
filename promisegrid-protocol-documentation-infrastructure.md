# PromiseGrid Protocol Documentation Infrastructure

This document outlines the infrastructure for maintaining, versioning, and distributing the PromiseGrid protocol specifications using IPFS Content Identifiers (CIDs).

## Overview

PromiseGrid's protocol documentation infrastructure is built on the following principles:

1. **Immutable Specifications**: Each version of the protocol specification is stored immutably with a unique CID
2. **CID-Based Versioning**: Protocol versions are identified by their CIDs, not by version numbers
3. **IPFS Distribution**: Specifications are distributed via IPFS, ensuring decentralized availability
4. **Self-Describing Messages**: All messages reference their protocol specification CID

## Protocol Specification Format

Protocol specifications are stored in a structured JSON-LD format, which includes:

```json
{
  "@context": "https://promisegrid.org/context/v1",
  "id": "<CID of this specification>",
  "name": "PromiseGrid Wire Protocol",
  "version": "1.0.0",
  "date": "2025-04-30",
  "description": "Core specification for the PromiseGrid wire protocol",
  "messageSchema": {
    "type": "object",
    "required": ["version", "type"],
    "properties": {
      "version": {
        "type": "string",
        "description": "CID of the protocol specification"
      },
      "type": {
        "type": "string",
        "enum": ["request", "response", "notification"],
        "description": "Message type"
      },
      // Additional properties...
    }
  },
  "messageTypes": {
    // Definitions of message types...
  },
  "actionHandlers": {
    // Definitions of action handlers...
  },
  "extensions": {
    // Extension points and mechanisms...
  },
  "compatibleWith": [
    // List of CIDs of compatible protocol versions...
  ]
}
```

## IPFS Content Identifiers (CIDs)

### CID Structure

PromiseGrid uses CIDv1 for all protocol references. A CIDv1 includes:

- Multibase prefix (typically 'b' for base32)
- CID version (1)
- Multicodec information (typically 'dag-json' or 'dag-cbor')
- Multihash of the content (typically using SHA-256)

Example CID: `bafybeigdyrzt5sfp7udm7hu76uh7y26nf3efuylqabf3oclgtqy55fbzdi`

### Protocol Version Discovery

Clients can discover protocol versions through:

1. **Direct Reference**: Specified in the message's `version` field
2. **Protocol Registry**: A maintained registry of protocol versions and their CIDs
3. **IPNS Publication**: Latest versions published under stable IPNS names

## Message Structure with Protocol Versioning

### Basic Message Structure

Every PromiseGrid message MUST include a `version` field containing the CID of the protocol specification:

```json
{
  "version": "bafybeigdyrzt5sfp7udm7hu76uh7y26nf3efuylqabf3oclgtqy55fbzdi",
  "type": "request",
  "action": "query",
  "payload": {
    "query": "status"
  },
  "signature": "..."
}
```

### CBOR Encoded Message

When encoded in CBOR and tagged with the PromiseGrid CBOR tag (1735289204), the message structure is preserved:

```
D9 1A 67 72 69 64  # tag(1735289204)
   A5              # map(5)
      67           # text(7)
         76657273696F6E            # "version"
      78 59        # text(89)
         6261667962656967647972... # CID string
      # Additional fields...
```

## Publishing and Updating Protocol Specifications

### Publication Process

1. **Create Specification**: Author the protocol specification in JSON-LD format
2. **Validate Specification**: Ensure the specification is valid and complete
3. **Add to IPFS**: Add the specification to IPFS and retrieve its CID
4. **Update Registry**: Update the protocol version registry with the new CID
5. **Publish via IPNS**: Update IPNS records to point to the latest version

### Protocol Evolution Strategy

Protocol evolution follows these guidelines:

1. **Backward Compatibility**: New versions should maintain compatibility with older versions when possible
2. **Clear Deprecation**: Deprecations must be clearly documented with migration paths
3. **Extension Mechanisms**: Use defined extension points for adding new features
4. **Explicit Incompatibility**: When backward-incompatible changes are necessary, they must be explicitly documented

## Implementation Guidelines

### Message Validation

1. Extract the protocol version CID from the message
2. Retrieve the protocol specification from IPFS using the CID
3. Validate the message against the schema defined in the specification
4. Process the message according to the rules in the specification

### Error Handling

1. **Protocol Not Found**: If a protocol specification cannot be retrieved, reject the message
2. **Validation Errors**: If a message does not conform to its protocol specification, reject it
3. **Incompatible Version**: If a client cannot process a message due to protocol incompatibility, indicate the supported protocol versions

## Development Tools

### Protocol Authoring Tools

- JSON-LD editor with schema validation
- Protocol compatibility checker
- CID generator and validator

### Reference Implementations

- JavaScript/TypeScript reference implementation
- Rust reference implementation
- Protocol test suite

## Governance

The PromiseGrid Protocol Working Group maintains:

1. Guidelines for protocol evolution
2. The official protocol version registry
3. Reference implementations
4. Compatibility test suites

## Conclusion

This infrastructure provides a robust foundation for PromiseGrid's protocol development, enabling:

- Clear versioning through immutable CIDs
- Decentralized distribution via IPFS
- Self-describing messages with protocol references
- A path for protocol evolution while maintaining compatibility

This approach integrates standards-based approaches (CBOR, IPFS) with a structured governance model to create a sustainable protocol ecosystem.
