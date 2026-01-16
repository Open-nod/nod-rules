# **nod-rules: The Official Compliance Registry 📚**

This is the official community registry for [**nod**](https://www.google.com/search?q=https://github.com/mraml/nod) compliance packs. It contains rule definitions for various regulatory standards, security frameworks, and best practices.

## **📦 Available Rule Packs**

| Standard | File | Description |
| ----- | ----- | ----- |
| **ISO 42001** | [`library/iso-42001.yaml`](https://www.google.com/search?q=library/iso-42001.yaml) | AI Management System framework. |
| **HIPAA** | [`library/hipaa.yaml`](https://www.google.com/search?q=library/hipaa.yaml) | Health Insurance Portability and Accountability Act. |
| **SOC 2** | [`library/soc2.yaml`](https://www.google.com/search?q=library/soc2.yaml) | Security, Availability, Processing Integrity, Confidentiality, and Privacy. |
| **GDPR** | [`library/gdpr.yaml`](https://www.google.com/search?q=library/gdpr.yaml) | General Data Protection Regulation for AI models. |

## **🚀 Usage**

You can use these rules directly with `nod` by referencing the raw URL.

```
# Example: Scanning against ISO 42001
nod scan docs/ --rules [https://raw.githubusercontent.com/mraml/nod-rules/main/library/iso-42001.yaml](https://raw.githubusercontent.com/mraml/nod-rules/main/library/iso-42001.yaml)
```

*(Note: In nod v2.0+, you will be able to use `nod scan --rules registry:iso-42001`)*

## **✍️ Contributing**

We welcome contributions\! If you are a compliance expert or security engineer:

1. **Fork** this repository.  
2. **Create** a new YAML file in `library/` following the [nod schema](https://www.google.com/search?q=https://github.com/mraml/nod%23configuration-rulesyaml).  
3. **Open a PR** to the `main` branch.

### **Rule Schema Example**

```
profiles:
  iso_42001:
    badge_label: "ISO 42001 Aligned"
    requirements:
      - id: "## AI Risk Assessment"
        severity: "HIGH"
        remediation: "ISO 42001 (6.1.2): You must document the AI risk assessment process."
```

