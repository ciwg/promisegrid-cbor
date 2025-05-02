# RFC and IANA Tag Registration for PromiseGrid

This repository contains the necessary documentation for registering the CBOR tag `0x67726964` (ASCII "grid") with IANA to support the PromiseGrid wire protocol, and to publish a corresponding informational RFC.

## Repository Contents

- **`draft-promisegrid-cbor-tag-00.xml`**: The Internet-Draft in xml2rfc v3 format that formally defines the CBOR tag for PromiseGrid protocol messages, following IETF standards for RFC publication.

- **`iana-cbor-tag-registration-promisegrid.txt`**: A template for the IANA registration request that will be submitted to register tag number 1735289204 in the CBOR Tags registry.

- **`promisegrid-protocol-documentation-infrastructure.md`**: Documentation outlining how PromiseGrid protocol specifications are stored, versioned, and referenced using IPFS Content Identifiers (CIDs).

## External Files

- **[Master TODO List for PromiseGrid CBOR Tag](https://docs.google.com/document/d/14EfC7GvkJ6YuuorRzP4N7F5_6GeKcN51UIuBrFfXwuU/edit)**: A comprehensive checklist of technical, documentation, and coordination tasks required to define, implement, and register the PromiseGrid CBOR tag by IETF 123.

- **[Deliverables and Deadlines for PromiseGrid CBOR Tag](https://docs.google.com/document/d/1PUaLawlAeKRwhmrgTN_6p2oNbQauud8dzIYPXTChQpU/edit)**: A structured timeline with milestone deadlines and descriptions for completing the draft, implementation, community engagement, and IETF submission.



## Project Overview

PromiseGrid is a decentralized, agent-based protocol designed for structured message exchange. The CBOR tag `0x67726964` will serve as a wrapper for encoded messages that conform to the PromiseGrid wire protocol, allowing decoders to recognize and properly interpret message contents.

Messages in the PromiseGrid ecosystem reference versioned protocol specifications stored on IPFS, with each specification identified by a unique Content Identifier (CID).

## Next Steps

1. Submit the Internet-Draft to the IETF Datatracker
2. Address feedback from the IETF community
3. Register the CBOR tag with IANA following the "First Come First Served" policy
4. Implement the protocol documentation infrastructure on IPFS
5. Develop reference implementations for encoding/decoding tagged messages

## Contributing

This project is open to collaborators with experience or interest in:
- Internet-Draft preparation and submission
- Protocol design
- IETF/IANA processes
- Decentralized systems (IPFS, CID-based versioning)
- CBOR encoding and message serialization

## License

This work is licensed under [LICENSE DETAILS].
