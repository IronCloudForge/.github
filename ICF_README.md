# ⚡ IronCloudForge

**Forging hardened compliance artifacts for federal cloud environments.**

We build open-source tooling that converts cloud security telemetry into machine-readable compliance artifacts — bridging the gap between what your CNAPP sees and what your ATO package requires.

---

## The Problem We're Solving

Federal cloud security runs on Word documents.

NIST publishes controls. FedRAMP requires System Security Plans. Agencies write narratives. Auditors read PDFs. ISSOs manage POA&Ms in spreadsheets. The entire compliance lifecycle is manual, disconnected, and impossible to automate at scale.

Meanwhile, your cloud environment is generating continuous security telemetry — misconfigurations, vulnerabilities, IAM anomalies, network exposures — in real time. That data contains everything needed to assess your control posture. It just never makes it into your ATO package.

**FedRAMP RFC-0024 changes that.** As of September 2026, all FedRAMP-authorized Cloud Service Providers must submit machine-readable OSCAL packages. The Word document era is ending. The tooling to replace it barely exists.

IronCloudForge builds that tooling.

---

## What We Build

| Repository | What It Does |
|------------|-------------|
| [`policy-as-code`](https://github.com/IronCloudForge/policy-as-code) | NIST 800-53 Rev 5 controls expressed as machine-enforceable OPA/Rego rules |
| [`wiz-oscal`](https://github.com/IronCloudForge/wiz-oscal) | Wiz for Gov → OSCAL 1.1.2 SSP & POA&M generator. RFC-0024 compliant. |
| `fedramp-baselines` *(coming)* | OSCAL profiles for FedRAMP Low, Moderate, and High baselines |
| `cac-azure` *(coming)* | Compliance as Code for Azure — Terraform + policy enforcement mapped to 800-53 |

---

## The Stack

```
Human Language Policy (NIST · FedRAMP · Agency DRs)
        │
        ▼
AI Policy Analysis Engine          ← document-to-document gap analysis
        │
        ▼
OSCAL Structured Data              ← machine-readable SSP · SAR · POA&M
        │
        ▼
Policy as Code Runtime             ← OPA/Rego · Checkov · Cloud-native policy
        │
        ▼
CI/CD Pipeline                     ← shift-left security gates
        │
        ▼
Runtime Infrastructure             ← continuous posture monitoring
        │
        ▼
Continuous Monitoring & ATO        ← automated ConMon · RFC-0024 compliant packages
```

---

## Why Now

Three federal mandates are converging simultaneously:

**FedRAMP RFC-0024** requires machine-readable OSCAL authorization packages from all FedRAMP-authorized CSPs. The notification deadline is September 30, 2026. The revocation deadline is September 30, 2027. Most federal cloud teams don't know this exists yet.

**CISA BOD 25-01** requires continuous configuration assessment against SCuBA baselines. Most agencies ran the free ScubaGear tool, generated reports, and filed them manually. Nobody built the operational pipeline to make those findings actionable.

**FedRAMP 20x** targets a 20x reduction in authorization time — from 22 months to 90 days — through OSCAL submissions and streaming continuous monitoring. The first pilot completed in 119 days. The tooling to scale that result doesn't broadly exist yet.

The gap between mandate and tooling is where IronCloudForge operates.

---

## Who This Is For

- **ISSOs and ISSMs** managing FedRAMP authorizations who need RFC-0024 compliant packages without a $2M GRC platform procurement
- **Cloud security engineers** building cATO pipelines who need NIST control coverage mapped to runtime enforcement
- **Federal DevSecOps teams** integrating compliance into CI/CD without blocking delivery
- **3PAOs and consultants** who need reproducible, validated OSCAL output for authorization engagements

---

## Principles

**Use the data you already have.** Your CNAPP is scanning continuously. Your cloud config tools are generating findings. The gap is not data — it's the pipeline that converts telemetry into compliance evidence. We build that pipeline.

**Machine-readable by default.** Every artifact we produce validates against the NIST OSCAL CLI. If it doesn't validate, it doesn't ship.

**Domain expertise over automation.** Copilot writes the syntax. The control mapping logic — which Wiz finding maps to CM-6, what a CM-7 violation looks like in Kubernetes — requires understanding NIST intent. That knowledge is built in, not generated.

**Open source.** Federal compliance tooling should not be locked behind enterprise contracts. The standards are public. The tooling should be too.

---

## Contributing

The most valuable contributions are to the control mapping tables — the translation layer between cloud security findings and NIST 800-53 control IDs. If you're running FedRAMP workloads and your tooling produces findings that don't map cleanly to a control in our libraries, open an issue or submit a PR.

We also welcome:
- OSCAL schema corrections and validation improvements
- Additional cloud provider support (AWS, GCP)
- New compliance framework mappings (CMMC, StateRAMP, DoD IL)
- Real-world 3PAO feedback on OSCAL package acceptance

---

## Follow Along

Articles, deep-dives, and lessons learned from building federal compliance automation in public:

🔗 [ironcloudforge.com](https://ironcloudforge.com)

---

*Built by practitioners who have sat in the ATO war rooms, written the POA&Ms, and watched the same manual process fail at scale — and decided to build the alternative.*

---

![Policy as Code](https://img.shields.io/badge/Policy_as_Code-NIST_800--53_Rev_5-2ea44f?style=flat-square)
![OSCAL](https://img.shields.io/badge/OSCAL-1.1.2-6f42c1?style=flat-square)
![FedRAMP](https://img.shields.io/badge/FedRAMP-RFC--0024_Target-0078d4?style=flat-square)
![License](https://img.shields.io/badge/License-Apache_2.0-orange?style=flat-square)
