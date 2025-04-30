# PromiseGrid CBOR Tag Registration Project Timeline

This document outlines timeline options for the RFC and IANA tag registration for the PromiseGrid protocol, taking into account various constraints and dependencies.

## Compressed Timeline (Optimistic)

This timeline represents an aggressive schedule with parallel work streams and assumes minimal blockers.

| Phase | Timeframe | Activities | Deliverables |
|-------|-----------|------------|--------------|
| **Preparation** | Week 1 | • Finalize Internet-Draft<br>• Prepare IANA registration template<br>• Review with stakeholders | • Completed Internet-Draft<br>• IANA registration template |
| **Submission** | Week 2 | • Submit Internet-Draft to IETF<br>• Initialize IPFS protocol documentation structure | • Submitted I-D<br>• Initial protocol documentation structure |
| **Development** | Weeks 3-4 | • Begin reference implementation<br>• Monitor IETF feedback<br>• Submit IANA registration | • Working prototype implementation<br>• Responses to initial feedback |
| **Refinement** | Weeks 5-6 | • Address IETF/IANA feedback<br>• Complete reference implementation<br>• Publish first protocol specification to IPFS | • Updated Internet-Draft<br>• Complete reference implementation<br>• Published protocol specification |
| **Completion** | Weeks 7-8 | • Monitor IANA registration progress<br>• Complete documentation<br>• Release implementation | • Final documentation<br>• Public release |

**Total Duration: 8 weeks**

## Realistic Timeline (Standard)

This timeline allows for more thorough review cycles and accounts for typical waiting periods in standards processes.

| Phase | Timeframe | Activities | Deliverables |
|-------|-----------|------------|--------------|
| **Preparation** | Weeks 1-2 | • Draft and review Internet-Draft<br>• Prepare IANA registration materials<br>• Conduct internal reviews | • Polished Internet-Draft<br>• IANA registration template<br>• Review documentation |
| **Submission** | Week 3 | • Submit Internet-Draft to IETF<br>• Announce to relevant communities | • Submitted I-D<br>• Community announcements |
| **Initial Feedback** | Weeks 4-6 | • Collect and address IETF community feedback<br>• Revise Internet-Draft as needed | • Feedback summary<br>• Revised Internet-Draft |
| **IANA Process** | Weeks 7-10 | • Submit IANA registration request<br>• Respond to expert reviewer questions<br>• Begin protocol documentation infrastructure | • Submitted IANA request<br>• Initial protocol documentation |
| **Implementation** | Weeks 11-14 | • Develop reference implementation<br>• Create protocol specifications on IPFS<br>• Develop testing framework | • Reference implementation<br>• IPFS protocol specifications<br>• Test suite |
| **Integration & Testing** | Weeks 15-18 | • Integrate components<br>• Comprehensive testing<br>• Complete documentation | • Integrated system<br>• Test reports<br>• Complete documentation |
| **Release** | Weeks 19-20 | • Public release<br>• Community education<br>• Monitor adoption | • Release packages<br>• Educational materials |

**Total Duration: 20 weeks**

## Timeline Constraints

### IETF Process Constraints

1. **Internet-Draft Expiration**: Internet-Drafts expire after 6 months if not updated or moved forward in the process
2. **IETF Meeting Cadence**: IETF meets roughly every 4 months; timing submissions relative to meetings can be strategic
3. **Review Cycles**: Community review is unpredictable in timing and extent
4. **RFC Publication Queue**: If proceeding to RFC status, publication can take several months after IESG approval

### IANA Registration Constraints

1. **Registration Procedure**: The specific CBOR tag range (32768-18446744073709551615) follows "First Come First Served" policy
2. **Expert Review**: Still requires expert review, which can take 2-4 weeks depending on expert availability
3. **Potential Issues**: Conflicts or concerns raised during review can extend the timeline
4. **Dependency on I-D**: While not strictly required, having an active Internet-Draft strengthens the registration request

### Technical Implementation Constraints

1. **IPFS Infrastructure**: Setting up and configuring IPFS nodes for protocol distribution takes time
2. **CID Versioning**: Proper implementation of CID-based versioning requires careful development and testing
3. **Interoperability Testing**: Testing with different implementations and configurations is time-consuming
4. **Security Review**: Thorough security review should be conducted before release

### Resource Constraints

1. **Team Size**: Available engineering resources will significantly impact timeline
2. **Expertise Requirements**: Specialized knowledge in CBOR, IPFS, and IETF processes is needed
3. **Stakeholder Availability**: Reviews and approvals depend on stakeholder availability
4. **Competing Priorities**: Other project commitments may impact resource allocation

## Milestones and Dependencies

### Critical Path Milestones

1. **Internet-Draft Submission**: Gateway to beginning the formal process
2. **IANA Registration Request**: Cannot be completed until draft is sufficiently mature
3. **Protocol Specification Publication**: Required for implementing the version reference system
4. **Reference Implementation Completion**: Validates the protocol design and registration

### Key Dependencies

1. Internet-Draft submission → IETF community feedback
2. Initial feedback incorporation → IANA registration request
3. IANA registration → Final implementation
4. Protocol specification → Implementation testing

## Timeline Flexibility Factors

Factors that could compress the timeline:
- Existing code that can be repurposed
- Team members with prior IETF experience
- Early engagement with IANA experts
- Parallel development of dependent components

Factors that could extend the timeline:
- Substantial community feedback requiring major revisions
- Delays in expert review for IANA registration
- Technical challenges in IPFS integration
- Resource constraints or competing priorities

## Recommended Approach

Based on the constraints above, we recommend:

1. **Start with the realistic timeline** for planning purposes
2. **Identify opportunities for parallelization** where dependencies allow
3. **Build in buffer time** for unexpected feedback or challenges
4. **Review and adjust the timeline** after each major milestone
5. **Engage early with IETF and IANA experts** to identify potential issues

## Monitoring and Adjusting

The project lead should:
1. Track progress against milestones weekly
2. Adjust the timeline as feedback is received
3. Communicate any significant changes to stakeholders
4. Document lessons learned for future standards efforts
