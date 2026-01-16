# **Contributing to nod-rules**

Welcome to the **nod** compliance registry\! We are building the open-source standard for AI governance policies. Whether you are a compliance officer, security engineer, or AI researcher, your contributions help make safe AI development accessible to everyone.

## **📚 The Golden Rule: "Pointer, Not Printer"**

Many compliance standards (ISO, IEC, etc.) are copyrighted. To keep this repository legally safe and open:

1. **DO NOT** copy-paste full descriptions or proprietary text from standards like ISO 42001\.  
2. **DO** reference the Control ID (e.g., "ISO 42001: 6.1.2").  
3. **DO** describe the *artifact* required in your own words (e.g., "Required Artifact: A documented risk assessment process").

We verify **evidence of compliance**, not the standard itself.

## **📂 Repository Structure**

* **`library/`**: This is where all the rule packs live. Each file should correspond to a specific standard (e.g., `hipaa.yaml`, `pci-dss.yaml`) or a specific threat model.  
* **`tests/`**: (Optional) Example markdown files that should PASS or FAIL your new rules.

## **📝 Rule Schema**

All rules must be valid YAML. Here is the structure for a standard rule pack:

```
profiles:
  standard_name:  # e.g., hipaa_security
    badge_label: "HIPAA Aligned" # The text shown on the README badge
    
    requirements:
      - id: "#+.*Risk Analysis"     # Regex to find the header in the Spec
        label: "Risk Analysis"      # Human-readable name for logs/agents
        control_id: "§ 164.308(a)(1)" # The regulatory reference
        severity: "CRITICAL"        # CRITICAL, HIGH, MEDIUM, or LOW
        remediation: "Required: Accurate and thorough assessment of potential risks."
        
        # Optional: Deep Validation
        must_contain:
          - "Methodology"
          - "Scope"
        
    red_flags:
      - pattern: "indefinite retention" # Regex to find forbidden content
        label: "Bad Retention Policy"
        severity: "HIGH"
        remediation: "Retention periods must be specific/bounded."
```

### **Severity Guide**

* **CRITICAL:** Violates the law, creates immediate liability, or leaks secrets. Blocks build.  
* **HIGH:** Missing a mandatory compliance artifact. Blocks build.  
* **MEDIUM:** Best practice violation or missing "Nice to have" documentation. Warns.  
* **LOW:** Suggestions or housekeeping.

## **🧪 How to Test Your Rules**

Before submitting a Pull Request, please test your rules using the `nod` CLI tool.

1. Install `nod` (currently via GitHub):

```
pip install git+[https://github.com/mraml/nod.git](https://github.com/mraml/nod.git)
```

2.   
   Create a dummy markdown file (`test.md`) that *should* pass your rules.  
3. Run `nod` against it using your new YAML file:

```
nod test.md --rules library/my-new-standard.yaml --strict
```

4.   
   Verify that it passes (Green) and that it fails (Red) when you remove the headers.

## **🚀 Submitting a Pull Request**

1. **Fork** this repository.  
2. Create a new branch: `feat/add-pci-dss`.  
3. Add your YAML file to `library/`.  
4. Open a Pull Request describing which standard you are adding and why.

Thank you for helping us secure the AI supply chain\! 🛡️

