# Azure Landing Zones Library - Dutch BIO Compliance

This repository contains Azure Landing Zone configurations implementing the Dutch Government Information Security Baseline (BIO) compliance framework.

## About BIO

The **Government Information Security Baseline (BIO)** is the basic framework of standards for information security within all levels of Dutch government, including central government, municipalities, provinces, and water boards.

**BIO2** (Baseline Informatiebeveiliging Overheid 2) is the successor to BIO 1.04zv and represents the current standard for government information security in the Netherlands. This is not yet formalised at the time of writing, but it is suggested that future versions of this example could include some of the additional policies and standards. This could be accomplished by referencing an updated inbuilt policy initiative or by adding additional assets into this library.

### Key Resources

- **Official BIO Portal**: [bio-overheid.nl](https://www.bio-overheid.nl/category/producten/bio)
- **Digital Government Overview**: [digitaleoverheid.nl - BIO](https://www.digitaleoverheid.nl/overzicht-van-alle-onderwerpen/cybersecurity/kaders-voor-cybersecurity/baseline-informatiebeveiliging-overheid/)
- **Azure Policy Samples**: [Microsoft Learn - NL BIO Cloud Theme](https://learn.microsoft.com/en-us/azure/governance/policy/samples/nl-bio-cloud-theme)

## Azure Implementation

Microsoft Azure provides built-in compliance support for BIO2 through the **NL BIO Cloud Theme V2** policy initiative:

- **Initiative ID**: `d8b2ffbe-c6a8-4622-965d-4ade11d1d2ee`
- **Policy Count**: 283 policies
- **Category**: Regulatory Compliance
- **Ownership**: Customer

### Azure Policy Resources

- **Azure Advertizer**: [aka.ms/azadvertizer](https://aka.ms/azadvertizer) - Search for "NL BIO" or "BIO"
- **Azure Policy Repository**: [github.com/Azure/azure-policy](https://github.com/Azure/azure-policy)
- **BIO Policy Definition**: [NL_BIO_Cloud_Theme_V2.json](https://github.com/Azure/azure-policy/blob/master/built-in-policies/policySetDefinitions/Regulatory%20Compliance/NL_BIO_Cloud_Theme_V2.json)

## Repository Structure

This repository implements BIO2 compliance using the [Azure Landing Zones Library](https://azure.github.io/Azure-Landing-Zones-Library/) framework.

### Key Components

- **alz_library_metadata**: This library is stacked on top of the Sovereign Landing Zone
- **nl_slz**: Architecture definition extending the Standard Landing Zone (SLZ) with Dutch compliance archetypes
- **Audit-NL-BIO**: Policy assignment implementing the full NL BIO Cloud Theme V2 initiative for audit compliance
- **Deny-NL-Optional**: Custom policy set enforcing additional requirements as an example of adding assets:
  - Geographic restrictions (defaults to West Europe and Noth Europe regions)
  - Confidential computing VM SKU requirements (DCv3/DCv5 series)
  - Premium Key Vault requirements for enhanced security
- **Enforce-KV-Premium**: Pulled from <https://github.com/Azure/Community-Policy/tree/main/policyDefinitions/Key%20Vault/enforce-key-vault-premium-sku>
- **alz_policy_default_values**: The file from SLZ is expanded so that `allowed_locations` also applies to the Deny-NL-Optional group.

Some of these can also be accomplished with Sovereign Landing Zones.

### Archetype Definitions

- **nl_root**: Root management group policies including BIO audit requirements
- **nl_confidential_corp**: Corporate confidential workload policies
- **nl_confidential_online**: Online service confidential workload policies

## Deployment

This library is compatible with Azure Landing Zone deployment tools that support the ALZ Library format, including:

- **Terraform**: [Azure/terraform-azurerm-avm-ptn-alz](https://github.com/Azure/terraform-azurerm-avm-ptn-alz)
- **Bicep**: [Azure/ALZ-Bicep](https://github.com/Azure/ALZ-Bicep)

## Compliance Notes

- All policies follow the official Azure BIO2 implementation (B.01.3)
- Geographic restrictions ensure data residency compliance within the EU
- Confidential computing requirements align with Dutch government security standards
- Policy assignments use system-assigned managed identities for secure execution

## Documentation

For detailed Azure Landing Zone documentation, see: [Azure Landing Zones Library](https://azure.github.io/Azure-Landing-Zones-Library/)
