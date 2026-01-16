# **nod-rules: Official Compliance Registry 📚**

This is the official community registry for [**nod**](https://www.google.com/search?q=https://github.com/mraml/nod) compliance packs. It contains rule definitions for various regulatory standards, security frameworks, and best practices.

## **⚠️ Important Disclaimer**

**nod** and these rule packs verify the **presence and alignment** of policy elements within a specification. They act as a blueprint auditor; they **do not** guarantee the security or legal compliance of the final running code, product, or organization. A "green light" from nod means the **intent** matches the policy requirements, but independent runtime auditing and legal counsel are still required for full compliance certification.

## **📦 Available Rule Packs**

| Standard | File | Description |
| ----- | ----- | ----- |
| **EU AI Act** | [`library/eu_ai_act.yaml`](https://www.google.com/search?q=library/eu_ai_act.yaml) | High-Risk AI System classification & documentation. |
| **NIST AI RMF** | [`library/nist_ai_rmf.yaml`](https://www.google.com/search?q=library/nist_ai_rmf.yaml) | Govern, Map, Measure, Manage functions. |
| **OWASP LLM Top 10** | [`library/owasp_llm.yaml`](https://www.google.com/search?q=library/owasp_llm.yaml) | Critical vulnerabilities for Large Language Model apps. |
| **Security Baseline** | [`library/security_baseline.yaml`](https://www.google.com/search?q=library/security_baseline.yaml) | Encryption, Access Control, and Secrets Management. |
| **ISO 42001** | [`library/iso_42001.yaml`](https://www.google.com/search?q=library/iso_42001.yaml) | AI Management System artifact verification. |
| **SOC 2** | [`library/soc2.yaml`](https://www.google.com/search?q=library/soc2.yaml) | Security, Availability, and Confidentiality artifacts. |
| **HIPAA** | [`library/hipaa.yaml`](https://www.google.com/search?q=library/hipaa.yaml) | ePHI Security Rule safeguards. |
| **GDPR (AI)** | [`library/gdpr.yaml`](https://www.google.com/search?q=library/gdpr.yaml) | Data protection, DPIA, and RoPA artifacts. |

## **🚀 Usage**

You can use these rules directly with `nod` by referencing the raw URL.

```
# Example: Scanning against ISO 42001
nod scan docs/ --rules [https://raw.githubusercontent.com/mraml/nod-rules/main/library/iso_42001.yaml](https://raw.githubusercontent.com/mraml/nod-rules/main/library/iso_42001.yaml)
```

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

