# azure-devsecops-pipeline
Repository for Azure DevSecOps pipelines code and design
# 🛡️ DevSecOps Lifecycle – Top Security Tools & Frameworks

This document maps the most widely used security tools across each stage of the DevSecOps lifecycle with:

- 📌 What it does
- 🔒 Why it matters
- 🛠️ How to use
- 🔄 Analogy
- 💡 Example

---

## 📊 DevSecOps Tools Table

| **Stage** | **Tool** | **What** | **Why** | **How to Use** | **Analogy** | **Example** |
|----------|----------|---------|--------|----------------|-------------|--------------|
| **1. Plan** | [Microsoft Threat Modeling Tool](https://aka.ms/tmt) | Identify architectural threats early | Prevent flaws before they're coded | Model system & generate threat reports | Like reviewing a building blueprint for flaws | Use TMT to model a web app & find spoofing threats |
| **2. Develop** | [Git Secrets](https://github.com/awslabs/git-secrets), [Gitleaks](https://github.com/gitleaks/gitleaks) | Detect secrets in code | Avoid secret exposure | Pre-commit or CI scan | Like spotting a key left in the open | Gitleaks catches an AWS key in a commit |
| **3. Build** | [Trivy](https://github.com/aquasecurity/trivy), [Grype](https://github.com/anchore/grype) | Scan containers & code for CVEs | Block vulnerable builds | CLI or CI plugin | Like a food inspector checking ingredients | Trivy flags log4j in Docker build |
| **4. Test** | [ZAP](https://www.zaproxy.org/), [OWASP Dependency-Check](https://owasp.org/www-project-dependency-check/) | Dynamic testing & dependency analysis | Find runtime and third-party flaws | Automated or manual test | Like simulated break-ins to test security | ZAP crawls a staging site |
| **5. Release** | [Checkov](https://www.checkov.io/), [TFSec](https://github.com/aquasecurity/tfsec) | Analyze Infrastructure as Code (IaC) | Stop insecure infrastructure | Run before deploy | Like approving blueprints before construction | Checkov flags public S3 bucket config |
| **6. Deploy** | [OPA Gatekeeper](https://github.com/open-policy-agent/gatekeeper), [Kube-Bench](https://github.com/aquasecurity/kube-bench) | Kubernetes policy enforcement | Prevent insecure deployments | Use constraints/policies | Like a gate guard blocking non-compliant entries | Gatekeeper denies pod with no labels |
| **7. Operate** | [Falco](https://falco.org/), [Sysdig Secure](https://sysdig.com/) | Monitor runtime behavior | Detect attacks live | Syscall/event-based agents | Like motion detectors & tripwires | Falco alerts on bash session in container |
| **8. Monitor** | [Prometheus](https://prometheus.io/) + [Grafana](https://grafana.com/), [Azure Monitor](https://learn.microsoft.com/en-us/azure/azure-monitor/) | Observe health, trends, incidents | Enable alerting & recovery | Instrument, export, visualize | Like CCTV + alarm system | Prometheus tracks AKS node metrics, Grafana alerts spike |

---

## ✅ Summary of Usage

| **Stage** | **Use in CI/CD** |
|----------|------------------|
| Plan | Threat modeling diagrams |
| Develop | Secrets scan in code |
| Build | Image/package CVE scans |
| Test | DAST and dependency check |
| Release | Terraform/ARM/Azure Bicep policy check |
| Deploy | Kubernetes admission controls |
| Operate | Runtime anomaly detection |
| Monitor | Metrics, logging & dashboards |

---

## 🧠 Analogy Map

- **Plan**: Securing architecture plans  
- **Develop**: Avoid exposing secret keys  
- **Build/Test**: QA check for security flaws  
- **Release/Deploy**: Final approval before going live  
- **Operate/Monitor**: Active surveillance after deployment  

---

## 🔗 Recommended Integrations

Integrate these tools using:
- GitHub Actions / Azure DevOps pipelines
- Admission Controllers (OPA/Gatekeeper)
- Prometheus Exporters for metrics
- Security dashboards and SIEM tools
