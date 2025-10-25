

# Stablecoin Risk Assessment Framework (SRAF) – v0.1
A layered, modular, experimental framework for assessing risk in stablecoin ecosystems across the entire stack from settlement layer to application layer. The objective of this framework is to assist in identifying areas of risk for participants in the stablecoing ecosystem.

This model evaluates risk across the stablecoin stack defined as four layers:
- Settlement Layer
- Issuance Layer
- Application Layer
- User Layer

Risks are scored qualitatively from Low to High as follows:  
Score each question: **0 = Low risk**, **1 = Medium risk**, **2 = High risk**,
If information is missing or unavailable, default to **2** which emphsizes the complex nature of these echosystems and the risks of unknown factors inherent in the stack. 

Due to the complexity of the stack, quantitative measurements are intentionally avoided, though the  framework could evolve to incorproate more analytical measurements for each area of risk. 

---

## 1. Settlement Layer  
The blockchain foundation on which stablecoins are issued and transacted. This layer represents the underlying network that enforces finality for stablecoin transactions regardless of the Layer 1 vs Layer 2 rollup distinction.

### Technical Risks
- [ ] Has the chain avoided major ***protocol bugs or downtime***  -  consensus (L1) or sequencer (L2) vulnerabilities halting or forking the chain in the past 12 months? 
- [ ] Is there sufficient **node/client diversity** in the deployment to avoid correlated failure risk?  
- [ ] Are **reorgs** rare and **finality** strong?  
- [ ] Is **bridge dependence** minimized or diversified?

### Operational Risks
- [ ] Is **RPC infrastructure** sufficiently decentralized, diversified or distributed?  
- [ ] Is the **validator or sequencer set** sufficiently decentralized, diversified or distributed? 
- [ ] Is **security operations maturity** high (monitoring, code-signing, strong developer security practices)?
- [ ] Has the chain been **operational on Mainnet** for more than two years? Less than one year scores 2, 1-3 years scores 1, greater than 3 years scores 0.

### Governance & Regulatory Risks
- [ ] Is **protocol governance** resilient to capture or manipulation?  
- [ ] Is **validator/sequencer collusion or censorship** risk mitigated?
- [ ] Is there risk of **censorship** due to legal/political pressure?

---

## 2. Issuance Layer  
Where stablecoins are created, collateralized, governed, and redeemed.

### Technical Risks
- [ ] Are contracts recently **audited** and is there an active **bug bounty** program?  
- [ ] Is the **upgrade process** transparent (timelocks, multisig, clear governance)?  
- [ ] Are **admin keys** constrained and secured? (this is a significant operational component that is hard to measure, so it's worth noting any historical administrative incidents)
- [ ] Is **native vs. wrapped issuance** clearly documented and consistent across chains?

### Operational Risks
- [ ] Is **collateral quality** conservative and well defined (i.e cash and short-term Treasuries vs. risky or volatile assets)?  
- [ ] Are reserves **diversified across custodians and geographies**?  
- [ ] Is **rehypothecation** avoided or clearly disclosed and limited?  
- [ ] Can **redemptions** reliably occur at par even under stress?  
- [ ] Are **attestations/audits** independent, recurring, and comprehensive?

### Governance & Regulatory Risks
- [ ] Is the **issuer** transparent, well-governed, and reputable (structure, backers, track record)?  
- [ ] Does the issuer leverage **regulatory frameworks** such as trust charters or compliance with emerging frameworks such as the U.S. Genius Act (when defined)?
- [ ] Is **blacklisting/freezing authority** transparent and controlled?  
- [ ] Is **jurisdictional exposure** diversified across geographies and/or jurisdictional regimes?

### Market Risks
- [ ] Is the **collateralization model** conservative (1:1) rather than algorithmic or complex?



---

## 3. Application Layer  
Encompasses all applications, infrastructure, and supply-chain dependencies such as wallets, exchanges, APIs, SDKs, DeFi protocols, on/off-ramps, bridges, and third-party services.

### Technical Risks
- [ ] Are **smart contracts** secure and covered by recent audits?  
- [ ] Are **oracles and data feeds** robust and monitored for manipulation?  
- [ ] Are **SDKs/APIs** vetted and supply-chain risk managed?  
- [ ] Are **bridges** secure, with fallback options available?
- [ ] Is **user interface infrastructure** secured with a process to minimize risk of man-in-the-middle or phishing attacks.

### Operational Risks
- [ ] Is **security operations maturity** high across the application ecosystem?  
- [ ] Are **third-party dependencies** evaluated for security posture and risk?  
- [ ] Are **on/off-ramps** solvent, compliant, reputable and well-controlled?  
- [ ] Are **custodians** diversified, reputable, solvent? Are funds segregated?

### Governance & Regulatory Risks
- [ ] Are **governance and upgrade keys** sufficiently decentralized?  
- [ ] Is **regulatory contamination** risk from unregulated assets well defined and understood?  
- [ ] Is the **user interface** accurate and resistant to spoofing or mislabeling?

### Market Risks
- [ ] Is there sufficient **liquidity** to avoid slippage and fragmentation?  
- [ ] Is **wrapped-asset exposure** clearly understood and minimized?  
- [ ] Is **composability risk** with risky DeFi protocols limited?


---

## 4. User Layer  
Where human behavior, wallet security, and user understanding impacts net risk.

### Technical Risks
- [ ] Is **user interface** resistant to spoofing, phishing, and impersonation?

### Operational Risks
- [ ] Are **private keys** securely stored?  
- [ ] Are **backup and recovery procedures** clear, functional with appropriate level of user education?  
- [ ] Are **hot wallet and signing risks** mitigated (clear approval process, limited permissions, revocation options, etc)? 
- [ ] Is **user education** effective against phishing, social engineering and private key/seedphrase disclosure risk?

### Governance & Regulatory Risks
- [ ] Are **geo-fencing** and usage constraints clearly communicated and enforced?

---

## Scoring & Interpretation

Quantitative scoring can obscure the layered complexity of stablecoin systems; this framework is designed to highlight areas of relative risk and maturity rather than assign precise numerical values. 
Each question is evaluated qualitatively on a high, medium, low model: 

- **0 = Low Risk** – Strong posture, mature controls, or high transparency.  
- **1 = Medium Risk** – Partial controls, evolving maturity, or limited visibility.  
- **2 = High Risk** – Significant vulnerabilities, opacity, or known weaknesses.  

To assess the relative risk of each category (e.g., Settlement, Issuance, Application, or User Layer) and to identify areas of outsized risk, averaging the individual question scores to produce a **category-level score** between 0–2 can be considered. For example, each category can be interpreted as follows:

| Category Score | Interpretation |
|----------------|----------------|
| **0.0 – 0.6** | **Low Risk** – Strong posture; well-defined controls and transparency. |
| **0.7 – 1.3** | **Medium Risk** – Partial controls; acceptable with further due diligence. |
| **1.4 – 2.0** | **High Risk** – Significant vulnerabilities or uncertainty. |

This produces a qualitative “risk grade” per category. You may optionally average all category scores to produce an overall rating.  

**Future Considerations:**  
- Weighting by category (e.g., Issuance 40%, Settlement 30%, Application 20%, User 10%) could also be considered in the future.

---

## Notes on Use
- Score **0** when data is missing — lack of transparency *is itself* a risk.  
- Reassess periodically — risk posture changes over time (audits expire, code evolves, regulations shift).  
- Use scenario testing (e.g., bridge failure, redemption stress, regulatory action) to refine scores.
