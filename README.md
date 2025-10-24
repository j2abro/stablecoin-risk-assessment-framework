

# Stablecoin Risk Assessment Framework (SRAF) – v0.1
A layered, modular, experimental framework for assessing risk in stablecoin ecosystems across the entire stack from settlement layer to application layer. The objective of this framework is to assist in identifying areas of risk for participants in the stablecoing space.

This model evaluates risk across the stablecoin stack defined as four layers:
 - Settlement Layer
 - Issuance Layer
 - Application Layer
 - User Layer

Risks are scored qualitively from Low to High as follows:  
Score each question: **01= Low risk**, **1 = Medium risk**, **2 = High risk**,
If information is missing or unavailable, default to **2** which emphsizes the complex nature of these echosystems and the risks of unknown factors in the stack. 

Due to the complexity of the stack, quantitive measurements avoided, though the  framework could evolve to incorproate more analytical measurements for each are of risk. 

---

## 1. Settlement Layer  
*The blockchain foundation on which stablecoins are issued and transacted.*

### Technical Risks
- Has the chain avoided major **downtime** or **consensus failures** in the past 12 months?  
- Is there sufficient **client diversity** (multiple production-grade clients in use)?  
- Are **reorgs** rare and **finality** strong?  
- Is **bridge dependence** minimized or diversified?

### Operational Risks
- Is **RPC infrastructure** decentralized and diversified?  
- Is the **validator set** sufficiently decentralized and distributed?  
- Is **security operations maturity** high (monitoring, code-signing, strong developer security practices)?
- Has the chain been **operational on Mainnet** for more than two years. Less than one year scores 2, 1-3 years scores 1, greater than 3 years scores 0.

### Governance Risks
- Is **protocol governance** resilient to capture or manipulation?  
- Is **validator collusion or censorship** risk mitigated?

### Regulatory Risks
- Are there safeguards against **censorship under legal pressure** (e.g., OFAC-sanctioned addresses)?

---

## 2. Issuance Layer  
*Where stablecoins are created, collateralized, governed, and redeemed.*

### Technical Risks
- Are contracts recently **audited** and is there an active **bug bounty** program?  
- Is the **upgrade process** transparent (timelocks, multisig, clear governance)?  
- Are **admin keys** constrained and secured (e.g., HSM, multisig)?  
- Is **native vs. wrapped issuance** clearly documented and consistent across chains?

### Operational Risks
- Is **collateral quality** conservative (cash and short-term Treasuries) vs. risky assets?  
- Are reserves **diversified across custodians and geographies**?  
- Is **rehypothecation** avoided or clearly disclosed and limited?  
- Can **redemptions** reliably occur at par even under stress?  
- Are **attestations/audits** independent, recurring, and comprehensive?

### Governance Risks
- Is the **issuer** transparent, well-governed, and reputable (structure, backers, track record)?  
- Does the issuer leverage **regulatory frameworks** (trust charters, Genius Act registration) for assurance?

### Market Risks
- Is the **collateralization model** conservative (1:1) rather than algorithmic or complex?

### Regulatory Risks
- Is **blacklisting/freezing authority** transparent and controlled?  
- Is **jurisdictional exposure** diversified (not dependent on a single enforcement regime)?

---

## 3. Application Layer  
*Encompasses all applications, infrastructure, and supply-chain dependencies — wallets, exchanges, APIs, SDKs, DeFi protocols, on/off-ramps, bridges, and third-party services.*

### Technical Risks
- Are **smart contracts** secure and covered by recent audits?  
- Are **oracles and data feeds** robust and monitored for manipulation?  
- Are **SDKs/APIs** vetted and supply-chain risk managed?  
- Are **bridges** secure, with fallback options available?

### Operational Risks
- Is **security operations maturity** high across the application ecosystem?  
- Are **third-party dependencies** evaluated for security posture and risk?  
- Are **on/off-ramps** solvent, compliant, and well-controlled?  
- Are **custodians and sub-custodians** solvent with segregated funds?

### Governance Risks
- Are **governance and upgrade keys** sufficiently decentralized?  
- Are **private keys** for operational and developer use secured?

### Market Risks
- Is there sufficient **liquidity** to avoid slippage and fragmentation?  
- Is **wrapped-asset exposure** clearly understood and minimized?  
- Is **composability risk** with risky DeFi protocols limited?

### Regulatory Risks
- Are there controls against **regulatory contamination** from unregulated assets?  
- Is the **user interface** accurate and resistant to spoofing or mislabeling?

---

## 4. User Layer  
*Where human behavior, wallet security, and user understanding determine realized risk.*

### Technical Risks
- Are **interfaces** resistant to spoofing, phishing, and impersonation?

### Operational Risks
- Are **private keys** securely stored (e.g., hardware, secure enclave)?  
- Are **backup and recovery procedures** clear and functional?  
- Are **hot wallet risks** mitigated (approval hygiene, limited permissions)?  
- Is **user education** effective against phishing and social engineering?

### Regulatory Risks
- Are **geo-fencing** and usage constraints clearly communicated and enforced?

---

## Scoring & Interpretation

Some beta scoring might be to set some ranges as follows, after normalizing the scores to 100.
| Score | Interpretation |
|-------|------------------|
| **0 – 39** | Low Risk – Strong posture; still requires continuous monitoring. |
| **40 – 69** | Medium Risk – Partial controls; use-case dependent; further due diligence required. |
| **70 – 100** | High Risk – Significant vulnerabilities; unsuitable for most uses. |

**Consider weighting scores by category:**  
- Settlement: 30%  
- Issuance: 40%  
- Application: 20%  
- User: 10%

---

## Notes on Use
- Score **0** when data is missing — lack of transparency *is itself* a risk.  
- Reassess periodically — risk posture changes over time (audits expire, code evolves, regulations shift).  
- Use scenario testing (e.g., bridge failure, redemption stress, regulatory action) to refine scores.
