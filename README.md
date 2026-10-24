## Hi, I'm dsgnbyalexx 👋

**Aspiring Cloud & DevOps engineer**, currently looking for internship opportunities.

I build cloud projects the way they're built at work: infrastructure as code, automated
tests and security scans in CI, and failure experiments that check the system behaves the
way the design says it should. Every repository separates **what is built and measured**
from **what is designed but not yet deployed**, and links to the evidence.

---

### 🚀 Featured projects

#### ☸️ [Kubernetes Microservices Platform](https://github.com/dsgnbyalexx/eks-microservices-gitops-platform)
[![CI](https://github.com/dsgnbyalexx/eks-microservices-gitops-platform/actions/workflows/ci.yml/badge.svg)](https://github.com/dsgnbyalexx/eks-microservices-gitops-platform/actions/workflows/ci.yml)

Five Flask microservices (auth, catalog, orders, simulated payments, notifications)
packaged with a Helm chart and deployed to Kubernetes.

- **Zero-downtime rolling updates, measured:** 0 of 1,442 requests failed (16 failed in a
  control run without the shutdown pause). CI repeats the test on every push.
- **CI builds a real Kubernetes cluster (kind)**, deploys the chart, and runs end-to-end tests.
- Idempotent payments, timeout budgets, readiness vs liveness (verified during a Redis
  outage), default-deny NetworkPolicies, Pod Security "restricted".
- **Alpine-based images: 164 → 0 known CVEs.**

`Python` `Flask` `Docker` `Kubernetes` `Helm` `Traefik` `Redis` `GitHub Actions` · *EKS and Argo CD: planned*

#### ⚡ [Serverless Data Pipeline & Security Compliance Engine](https://github.com/dsgnbyalexx/serverless-data-pipeline-security-automation)
[![CI](https://github.com/dsgnbyalexx/serverless-data-pipeline-security-automation/actions/workflows/ci.yml/badge.svg)](https://github.com/dsgnbyalexx/serverless-data-pipeline-security-automation/actions/workflows/ci.yml)

An event-driven S3 → SQS → Lambda → DynamoDB pipeline, plus a scanner that detects risky
AWS settings and fixes them only behind explicit safeguards.

- Retries, a dead-letter queue, partial batch failures, and **idempotent writes**, proven
  by a test that fails when the safeguard is removed.
- **Compliance scanner:** 6 rules across S3, EC2 and IAM. Remediation is dry-run by default
  and needs an allowlist, `--apply`, and an opt-in tag; the scheduled Lambda has a
  read-only role.
- 49 tests against simulated AWS (moto); Terraform validated and security-scanned.

`Python` `AWS Lambda` `SQS` `DynamoDB` `S3` `EventBridge` `Terraform` `moto`

#### 🛒 [Three-Tier AWS E-Commerce Platform](https://github.com/dsgnbyalexx/aws-multi-region-ecommerce)
[![CI](https://github.com/dsgnbyalexx/aws-multi-region-ecommerce/actions/workflows/ci.yml/badge.svg)](https://github.com/dsgnbyalexx/aws-multi-region-ecommerce/actions/workflows/ci.yml)

A Node.js + PostgreSQL store, with AWS infrastructure written as Terraform modules: VPC
across two Availability Zones, load balancer, Auto Scaling, RDS.

- Orders are a single transaction with row locking: **6 concurrent orders for 3 items →
  exactly 3 succeed.**
- Graceful shutdown, liveness vs readiness checks, and migrations that are safe with many
  instances.
- CI with integration tests against a real PostgreSQL. **It blocked an unsafe dependency
  update** (the Node 25 image failed the vulnerability scan).
- Multi-region disaster recovery is **designed**, with RPO/RTO *targets*, not yet built.

`Node.js` `PostgreSQL` `Docker` `Terraform` `AWS (VPC, ALB, ASG, RDS)` `GitHub Actions` `Trivy`

---

### 🧭 How I work

- **Evidence over claims.** Results link to raw test output, scans and experiment logs.
- **Tests that can fail.** Key safeguards are checked with negative controls: break the
  code and confirm the test catches it.
- **Security in the pipeline.** Vulnerability and IaC scanning, secret scanning, SHA-pinned
  actions, non-root containers, and no secrets in Git.
- **Honest scope.** The AWS infrastructure is validated in Terraform but not yet deployed;
  each README says exactly what has and hasn't been tested.

### 🛠️ Tools used in these projects

**Cloud & IaC:** AWS (VPC, ALB, Auto Scaling, RDS, Lambda, SQS, DynamoDB, S3, EventBridge, CloudWatch) · Terraform  
**Containers:** Docker · Docker Compose · Kubernetes (kind) · Helm · Traefik  
**CI/CD & security:** GitHub Actions · Dependabot · Trivy · gitleaks · ShellCheck · actionlint · kubeconform  
**Languages & data:** Python (Flask, boto3, pytest) · Node.js (Express) · PostgreSQL · Redis · DynamoDB

### 📫 Contact

Open to Cloud / DevOps internship opportunities: **[LinkedIn](https://www.linkedin.com/in/prudence-alexx/)**
