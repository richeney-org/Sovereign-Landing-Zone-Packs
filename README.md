# Azure Landing Zones Library - Country & Industry Packs

This repository provides a centralized collection of example country-specific and industry-specific compliance packs for the [Azure Landing Zones Library](https://aka.ms/alz/library) format. These packs extend the standard platform libraries with additional sovereignty and compliance requirements.

## Purpose

While the [Azure Landing Zones Library](https://aka.ms/alz/library) provides foundational platform configurations, organizations often need additional policies and controls to meet:

- **Country-specific regulations** (data residency, sovereignty requirements)
- **Industry compliance standards** (financial services, healthcare, government)

This repository bridges that gap by providing pre-built, reusable compliance packs that stack on top of standard landing zones.

## Repository Structure

```text
/country/<country_code>/<framework>/
/industry/<sector>/<standard>/
```

Each pack contains standard Azure Landing Zone library assets such as:

- `alz_library_metadata.json` - Library definition and dependencies
- `archetype_*.json` - Management group archetype configurations
- `policy_*.json` - Custom policy definitions and assignments
- `alz_policy_default_values.json` - Policy parameter defaults (optional)
- `README.md` - Pack-specific documentation

See the <https://aka.ms/alz/library/site> for more detail.

## Available Packs

### Country Packs

- **Netherlands (NL)**
  - `country/nl/bio/` - Dutch Government Information Security Baseline (BIO) compliance

### Industry Packs

*Coming soon*

## Usage

These packs are designed for use with Azure Landing Zone deployment tools that support the ALZ Library format:

- **Terraform**: [Azure/terraform-azurerm-avm-ptn-alz](https://github.com/Azure/terraform-azurerm-avm-ptn-alz)
- **Bicep**: [Azure/ALZ-Bicep](https://github.com/Azure/ALZ-Bicep)

Reference packs by their library metadata path and version when configuring your landing zone deployment.

## Contributing

Contributions of new country and industry packs are welcome. Please ensure:

- Compliance with the [ALZ Library schema](https://azure.github.io/Azure-Landing-Zones-Library/)
- Clear documentation of regulatory requirements
- Use of official Azure Policy initiatives where available
- Proper versioning and dependency management

## Resources

- **Azure Landing Zones Library**: [aka.ms/alz/library](https://aka.ms/alz/library)
- **Azure Policy Documentation**: [learn.microsoft.com/azure/governance/policy](https://learn.microsoft.com/azure/governance/policy)
- **Sovereign Landing Zones**: [aka.ms/alz/slz](https://aka.ms/sovereign/slz)

## License

This project follows the same licensing as the Azure Landing Zones Library.
