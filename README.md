# FlexID Aries Cloud Agent - Python  <!-- omit in toc -->


> An easy to use FlexID agent for building SSI services using any language that supports sending/receiving HTTP requests.

## Overview

FlexID Cloud Agent Python (FLACA-Py) is a foundation for building Verifiable Credential (VC) ecosystems. It operates in the second and third layers of the [Trust Over IP framework (PDF)](https://trustoverip.org/wp-content/uploads/2020/05/toip_050520_primer.pdf) using [DIDComm messaging](https://github.com/hyperledger/aries-rfcs/tree/main/concepts/0005-didcomm) and [Algorand](https://www.algorand.com) protocols. The "cloud" in the name means that FLACA-Py runs on servers (cloud, enterprise, IoT devices, and so forth), and is not designed to run on mobile devices.

To use FLFLACA-Py you create a business logic controller that "talks to" FLACA-Py (sending HTTP requests and receiving webhook notifications), and FLACA-Py handles the Aries and DIDComm functionality. That controller can be built in any language that supports making and receiving HTTP requests; knowledge of Python is not needed. Together, this means you can focus on building VC solutions using familiar web development technologies, instead of having to learn the nuts and bolts of low-level cryptography and Trust over IP-type Aries protocols.

This [checklist-style overview document](./SupportedRFCs.md) provides a full list of the features in FLACA-Py.
The following is a list of some of the core features needed for a production deployment, with a link to detailed information about the capability.

### Multi-Tenant

FLACA-Py supports "multi-tenant" scenarios. In these scenarios, one (scalable) instance of FLACA-Py uses one database instance, and are together capable of managing separate secure storage (for private keys, DIDs, credentials, etc.) for many different actors. This enables (for example) an "issuer-as-a-service", where an enterprise may have many VC issuers, each with different identifiers, using the same instance of FLACA-Py to interact with VC holders as required. Likewise, an FLACA-Py instance could be a "cloud wallet" for many holders (e.g. people or organizations) that, for whatever reason, cannot use a mobile device for a wallet. Learn more about multi-tenant deployments [here](./Multitenancy.md).

### Mediator Service

Startup options allow the use of an FLACA-Py as an [mediator] using core FlexID protocols to coordinate its mediation role. Such an FLACA-Py instance receives, stores and forwards messages to Aries  agents that (for example) lack an addressable endpoint on the Internet such as a mobile wallet.

### Scaled Deployments

FLACA-Py supports deployments in scaled environments such as in Kubernetes environments where FLACA-Py and its storage components can be horizontally scaled as needed to handle the load.

## Example Uses

The business logic you use with FLACA-Py is limited only by your imagination. Possible applications include:

* An interface to a legacy system to issue verifiable credentials
* An authentication service based on the presentation of verifiable credential proofs
* An enterprise wallet to hold and present verifiable credentials about that enterprise
* A user interface for a person to use a wallet not stored on a mobile device
* An application embedded in an IoT device, capable of issuing verifiable credentials about collected data
* A persistent connection to other agents that enables secure messaging and notifications
* Custom code to implement a new service.


