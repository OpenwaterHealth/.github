# Security Policy

## Our Commitment

Openwater takes the security of our open-source medical device platforms extremely seriously. Patient safety depends on secure, reliable software and hardware. We appreciate the efforts of security researchers and the community in helping us maintain the highest security standards.

## Reporting a Vulnerability

**⚠️ DO NOT create a public GitHub issue for security vulnerabilities**

### Preferred Reporting Method

**Email:** [security@openwater.health](mailto:security@openwater.health)

**PGP Key:** [Available here](https://github.com/OpenwaterHealth/openwater-commons/blob/main/security/pgp-key.asc)

### What to Include

Please provide:

1. **Description** - Detailed description of the vulnerability
2. **Impact** - Potential impact on patient safety, data privacy, or system security
3. **Affected Components** - Which repositories, versions, or hardware components
4. **Reproduction Steps** - Step-by-step guide to reproduce the issue
5. **Proof of Concept** - Code, screenshots, or demonstration (if applicable)
6. **Suggested Fix** - Proposed remediation (if you have one)
7. **Your Contact Info** - How we can reach you for follow-up

### Response Timeline

| Timeline | Action |
|----------|--------|
| **24 hours** | Acknowledgment of report receipt |
| **72 hours** | Initial assessment and severity classification |
| **7 days** | Detailed response with remediation plan |
| **30 days** | Fix developed, tested, and prepared for release |
| **90 days** | Public disclosure (coordinated with researcher) |

We may request additional time for complex issues or if patches require regulatory review (FDA, CE mark, etc.).

## Severity Classification

### Critical (CVSS 9.0-10.0)
**Impact:** Immediate threat to patient safety or data breach
- Remote code execution affecting medical devices
- Unauthorized access to patient health information
- Safety-critical system compromise

**Response:** Immediate action, emergency patches

### High (CVSS 7.0-8.9)
**Impact:** Significant security risk or data exposure
- Privilege escalation
- Authentication bypass
- Sensitive data leakage

**Response:** Priority fix within 7 days

### Medium (CVSS 4.0-6.9)
**Impact:** Moderate security concern
- Denial of service
- Information disclosure (non-sensitive)
- Cross-site scripting (XSS)

**Response:** Fix within 30 days

### Low (CVSS 0.1-3.9)
**Impact:** Minor security issue
- Low-impact information disclosure
- Minor configuration issues

**Response:** Fix in next regular release

## Security Vulnerability Handling

### Internal Process

1. **Triage** - Security team evaluates severity and impact
2. **Confirmation** - Reproduction and validation of issue
3. **Fix Development** - Private development of patch
4. **Testing** - Comprehensive testing including regression
5. **Regulatory Review** - FDA/CE consultation if needed
6. **Coordinated Disclosure** - Communication with researcher and community
7. **Public Release** - Patch release with security advisory

### Affected Stakeholders Notification

For critical vulnerabilities, we will notify:
- Active users and deployment sites
- Research partners and collaborators
- Regulatory bodies (FDA, etc.) if required
- Security mailing list subscribers

## Supported Versions

| Platform | Version | Supported |
|----------|---------|-----------|
| OpenLIFU-python | 2.x | ✅ Security updates |
| OpenLIFU-python | 1.x | ⚠️ Critical fixes only |
| OpenLIFU-python | < 1.0 | ❌ No longer supported |
| OpenMOTION-Pylib | 1.x | ✅ Security updates |
| Firmware | Latest | ✅ Security updates |
| Firmware | Previous | ⚠️ Critical fixes only |

We recommend always running the latest stable version.

## Known Security Considerations

### Medical Device Specific

1. **FDA Regulations**
   - Our devices are investigational (not FDA cleared for clinical use)
   - Security updates may require regulatory review
   - Some vulnerabilities may need FDA reporting under MDR

2. **Patient Data Privacy**
   - All patient data must comply with HIPAA (US) and GDPR (EU)
   - PHI (Protected Health Information) encryption required
   - Audit logging for all data access

3. **Network Security**
   - Devices should be on isolated networks
   - No direct internet exposure recommended
   - VPN required for remote access

### Hardware Security

1. **Firmware Signing**
   - All firmware should be cryptographically signed
   - Verify signatures before flashing
   - Do not install unsigned firmware

2. **Physical Security**
   - Devices contain powerful ultrasound transducers
   - Physical access controls required
   - Tamper-evident seals recommended

3. **Supply Chain**
   - Verify component authenticity
   - Source from reputable suppliers
   - Check for counterfeit components

## Security Best Practices

### For Developers

**Code Review:**
```bash
# Run security linters
bandit -r src/  # Python security linter
cppcheck src/   # C/C++ static analysis
```

**Dependency Scanning:**
```bash
# Check for vulnerable dependencies
pip-audit                    # Python
npm audit                    # JavaScript
cargo audit                  # Rust
```

**Secret Scanning:**
```bash
# Never commit secrets to git
git-secrets --scan           # Check commits
trufflehog filesystem src/   # Deep scan
```

**Testing:**
```bash
# Include security tests
pytest tests/security/
```

### For Deployers

**System Hardening:**
- Keep operating systems updated
- Use firewall rules to restrict access
- Enable full-disk encryption
- Implement strong authentication (2FA)
- Regular security audits

**Network Segmentation:**
- Isolate medical devices from general network
- Use VLANs for medical equipment
- Implement IDS/IPS monitoring
- Restrict outbound connections

**Access Control:**
- Principle of least privilege
- Role-based access control (RBAC)
- Audit all privileged access
- Regular access reviews

**Data Protection:**
- Encrypt data at rest (AES-256)
- Encrypt data in transit (TLS 1.3+)
- Secure backups (encrypted, off-site)
- Data retention policies

## Security Disclosure Policy

### Coordinated Disclosure

We practice responsible, coordinated disclosure:

1. **Private Disclosure** - Report sent to security@openwater.health
2. **Investigation Period** - 90 days maximum for fix development
3. **Coordinated Release** - Work with researcher on disclosure timing
4. **Public Advisory** - Security advisory published with patch
5. **Credit Given** - Researcher credited (if desired) in advisory

### Public Disclosure

After patch release, we will publish:
- Security advisory on GitHub Security Advisories
- CVE request (if applicable)
- Blog post explaining impact and remediation
- Update to this security policy

## Security Research Guidelines

### Authorized Testing

**We welcome security research on:**
- Public source code repositories
- Test/demo environments we provide
- Our public websites (openwater.health, docs.openwater.health)

**Out of Scope:**
- Production clinical environments
- Third-party systems
- Social engineering attacks
- Physical attacks on hardware
- Denial of service attacks
- Automated scanning (please coordinate first)

### Researcher Recognition

We appreciate responsible disclosure and offer:
- Public recognition in security advisories (if desired)
- Hall of Fame listing on our website
- Swag and thank-you gifts
- Reference letters for significant findings
- Possible bug bounty (under development)

## Compliance & Certifications

### Current Status

- **FDA:** Investigational device exemption (IDE) in process
- **ISO 13485:** Medical devices quality management (in process)
- **IEC 62304:** Medical device software lifecycle
- **IEC 60601-1:** Medical electrical equipment safety

### Security Frameworks

We align with:
- NIST Cybersecurity Framework
- ISO 27001 (Information Security Management)
- FDA Medical Device Cybersecurity Guidance
- HIPAA Security Rule
- GDPR Privacy by Design

## Security Contacts

**Primary Contact:**
- Email: [security@openwater.health](mailto:security@openwater.health)
- PGP: [PGP Key](https://github.com/OpenwaterHealth/openwater-commons/blob/main/security/pgp-key.asc)

**Security Team:**
- Listed in [security team directory](https://github.com/OpenwaterHealth/openwater-governance/blob/main/security-team.md)

**Emergency Contact (Critical Patient Safety Issues):**
- Email: [emergency@openwater.health](mailto:emergency@openwater.health)
- Phone: +1 (XXX) XXX-XXXX (24/7 on-call)

## Security Mailing List

Subscribe to receive security advisories:
[security-announce@openwater.health](https://openwater.health/security-list)

## Hall of Fame

We thank the following security researchers for responsible disclosure:

_(List will be populated as we receive reports)_

## Questions?

For security questions or clarifications:
- Email: [security@openwater.health](mailto:security@openwater.health)
- Discord: [#security channel](https://discord.gg/openwater) (for general questions only, not vulnerabilities)

---

**Patient safety is our top priority. Thank you for helping us build secure medical devices.** 🔒

Last updated: December 2025
