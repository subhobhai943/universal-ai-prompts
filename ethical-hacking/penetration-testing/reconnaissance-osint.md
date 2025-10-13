# 🕵️ OSINT & Reconnaissance Prompts

> ⚠️ **ETHICAL USE ONLY**: These prompts are for authorized security testing only. Always obtain proper written permission before gathering information about any target.

## 📋 Description

Open Source Intelligence (OSINT) and reconnaissance prompts designed to help security professionals gather information about targets during authorized penetration testing activities. These prompts assist with passive information gathering, target profiling, and attack surface mapping.

## 🎯 Purpose

- **Passive Reconnaissance**: Gather information without directly interacting with target systems
- **Attack Surface Mapping**: Identify potential entry points and vulnerabilities
- **Threat Intelligence**: Collect relevant security information about targets
- **Social Engineering Preparation**: Understand organizational structure and personnel
- **Compliance Testing**: Verify information security policies and procedures

## 🤖 Compatible Models

- [x] **ChatGPT (GPT-3.5/4)** - Excellent for complex analysis and correlation
- [x] **Claude 3.5 Sonnet** - Great for detailed research and documentation
- [x] **Gemini Pro** - Good for web research and data analysis
- [x] **Llama 2** - Suitable for basic reconnaissance tasks

## 📋 Prerequisites

- Written authorization for information gathering
- Clearly defined scope and boundaries
- Understanding of legal compliance requirements
- Access to OSINT tools and databases (optional)

---

## 💡 Core OSINT Prompts

### 1. Comprehensive Domain Analysis

```
You are a cybersecurity professional conducting authorized reconnaissance. Analyze the domain [TARGET_DOMAIN] and provide a comprehensive intelligence report including:

**TECHNICAL INFRASTRUCTURE:**
- DNS records analysis (A, AAAA, MX, TXT, SPF, DKIM, DMARC)
- Subdomain enumeration strategies
- SSL/TLS certificate information
- Web technologies and frameworks in use
- Content Management Systems
- Third-party services and integrations

**NETWORK INFORMATION:**
- IP address ranges and ASN details
- Hosting providers and cloud services
- CDN usage and configuration
- Load balancers and proxies
- Network topology insights

**SECURITY POSTURE:**
- Security headers analysis
- Public vulnerability disclosures
- Security certifications and compliance
- Breach history and security incidents
- Bug bounty programs

**ORGANIZATIONAL INTELLIGENCE:**
- Company background and business model
- Key personnel and organizational structure
- Physical locations and offices
- Subsidiaries and partnerships
- Recent news and developments

**SOCIAL MEDIA FOOTPRINT:**
- Official social media accounts
- Employee social media presence
- Technology discussions and preferences
- Security awareness and practices

Format the output as a professional intelligence report with actionable insights for security assessment. Include confidence levels for each finding and recommend specific testing approaches.

Remember: This analysis is for authorized security testing only.
```

### 2. Email Intelligence & Communication Analysis

```
As an authorized security researcher, analyze the email infrastructure and communication patterns for [ORGANIZATION_NAME]. Provide intelligence on:

**EMAIL INFRASTRUCTURE:**
- Mail server configurations and providers
- SPF, DKIM, and DMARC policy analysis
- Email routing and backup MX records
- Webmail interfaces and access methods
- Mobile device management policies

**COMMUNICATION PATTERNS:**
- Common email formats and naming conventions
- Department-specific email structures
- Executive and leadership contact information
- External communication partners
- Automated system email addresses

**SECURITY ANALYSIS:**
- Email security controls and filtering
- Historical phishing attempts or breaches
- Employee security awareness training indicators
- Two-factor authentication implementation
- Email encryption practices

**ATTACK VECTORS:**
- Potential phishing targets and scenarios
- Social engineering opportunities
- Business email compromise risks
- Supply chain communication vulnerabilities
- Executive impersonation possibilities

Provide recommendations for:
- Email security testing approaches
- Social engineering assessment strategies
- Security awareness evaluation methods
- Technical email security validation

Ensure all recommendations comply with authorized testing scope and ethical guidelines.
```

### 3. Personnel Intelligence & Organizational Mapping

```
You are conducting authorized personnel intelligence gathering for security assessment of [ORGANIZATION_NAME]. Create a comprehensive organizational intelligence profile:

**LEADERSHIP ANALYSIS:**
- Executive team structure and backgrounds
- Board of directors and advisors
- Key decision makers and influencers
- Leadership communication styles and preferences
- Public speaking engagements and conferences

**TECHNICAL PERSONNEL:**
- IT and security team structure
- Key technical personnel and their specializations
- System administrators and network engineers
- Development teams and project managers
- Third-party contractors and consultants

**OPERATIONAL STRUCTURE:**
- Department organization and hierarchies
- Reporting structures and communication flows
- Physical office locations and remote work policies
- Shift schedules and operational hours
- Emergency contacts and procedures

**DIGITAL FOOTPRINT ANALYSIS:**
- Professional networking profiles (LinkedIn, GitHub, etc.)
- Conference presentations and publications
- Technical blog posts and articles
- Social media activity and technology preferences
- Job posting analysis for technology stack insights

**SECURITY IMPLICATIONS:**
- Potential social engineering targets
- High-value personnel for targeted attacks
- Technology preferences and potential vulnerabilities
- Communication patterns and trusted relationships
- Travel schedules and physical security considerations

**RISK ASSESSMENT:**
- Insider threat potential and mitigation
- Third-party access and vendor relationships
- Knowledge concentration and single points of failure
- Security awareness levels and training needs

Format as a structured intelligence report with actionable security testing recommendations. Include confidence ratings and ethical considerations for each finding.

Note: All intelligence gathering must comply with privacy laws and authorized testing scope.
```

### 4. Technology Stack & Infrastructure Discovery

```
Perform authorized technical reconnaissance on [TARGET_ORGANIZATION] to map their technology infrastructure and identify potential security testing opportunities:

**WEB APPLICATIONS & SERVICES:**
- Public-facing web applications and portals
- API endpoints and documentation
- Mobile applications and app store presence
- Web technologies, frameworks, and versions
- Content management systems and plugins
- JavaScript libraries and third-party integrations

**CLOUD & HOSTING INFRASTRUCTURE:**
- Cloud service providers and configurations
- CDN services and caching mechanisms
- Database technologies and access methods
- Container and orchestration platforms
- Serverless functions and microservices
- Backup and disaster recovery services

**NETWORK & SECURITY SERVICES:**
- DNS configurations and nameservers
- SSL/TLS implementations and certificate authorities
- Web application firewalls and security services
- Load balancers and reverse proxies
- DDoS protection and rate limiting
- VPN and remote access solutions

**DEVELOPMENT & DEVOPS TOOLS:**
- Version control systems and repositories
- CI/CD pipelines and deployment methods
- Issue tracking and project management tools
- Code quality and security scanning tools
- Container registries and artifact repositories
- Infrastructure as Code (IaC) tools

**THIRD-PARTY INTEGRATIONS:**
- Payment processing systems
- Analytics and tracking services
- Social media integrations
- Customer support and communication tools
- Marketing automation platforms
- Identity and access management solutions

**SECURITY TESTING RECOMMENDATIONS:**
- Prioritized attack surface areas
- Recommended testing methodologies
- Potential vulnerability classes to investigate
- Tools and techniques for deeper analysis
- Compliance and regulatory considerations

Provide a structured technical intelligence report with confidence levels, testing priorities, and ethical guidelines for each identified component.
```

### 5. Supply Chain & Third-Party Risk Analysis

```
Conduct authorized supply chain intelligence analysis for [TARGET_ORGANIZATION] to identify third-party risks and potential attack vectors:

**VENDOR & PARTNER ECOSYSTEM:**
- Key technology vendors and service providers
- Software suppliers and licensing relationships
- Cloud service dependencies and configurations
- Integration partners and data sharing agreements
- Outsourced services and managed service providers

**SUPPLY CHAIN DEPENDENCIES:**
- Critical supplier relationships and contracts
- Single points of failure in vendor relationships
- Geographic distribution of suppliers
- Vendor security certifications and compliance
- Supply chain resilience and redundancy

**TECHNOLOGY DEPENDENCIES:**
- Open source software and library usage
- Third-party APIs and service integrations
- Software update and patch management chains
- Hardware suppliers and firmware dependencies
- Certificate authorities and trust relationships

**COMMUNICATION CHANNELS:**
- B2B communication methods and security
- Data exchange formats and protocols
- VPN and secure communication channels
- File sharing and collaboration platforms
- Emergency communication procedures

**RISK ASSESSMENT:**
- High-risk vendor relationships
- Potential supply chain attack vectors
- Third-party access control weaknesses
- Data exposure through partner relationships
- Vendor security incident history

**SECURITY TESTING OPPORTUNITIES:**
- Third-party integration testing approaches
- Vendor security assessment methodologies
- Supply chain attack simulation scenarios
- Partner communication security validation
- Vendor access control verification

Deliver a comprehensive supply chain risk intelligence report with prioritized recommendations for security testing and risk mitigation strategies.

Ensure all analysis respects privacy boundaries and authorized testing scope.
```

---

## 🔧 Usage Examples

### Basic Domain Analysis

**Input:**
```
You are a cybersecurity professional conducting authorized reconnaissance. Analyze the domain example-corp.com and provide a comprehensive intelligence report...
[Replace example-corp.com with authorized target]
```

**Expected Output:**
```
# Intelligence Report: example-corp.com

## Executive Summary
[High-level findings and recommendations]

## Technical Infrastructure
- DNS Analysis: [Detailed findings]
- SSL/TLS Configuration: [Certificate details]
- Web Technologies: [Framework and CMS analysis]

## Security Posture
- Security Headers: [Implementation status]
- Known Vulnerabilities: [CVE analysis]
- Compliance Status: [Certifications found]

[Additional sections with detailed analysis]
```

---

## ⚙️ Customization Guide

### Required Replacements:
- `[TARGET_DOMAIN]`: The authorized target domain
- `[ORGANIZATION_NAME]`: Official organization name
- `[TARGET_ORGANIZATION]`: Organization being assessed

### Optional Modifications:
- **Scope Adjustment**: Modify focus areas based on engagement scope
- **Compliance Requirements**: Add specific regulatory frameworks
- **Industry Focus**: Tailor analysis for specific industry verticals
- **Time Constraints**: Adjust depth of analysis based on timeline

### Advanced Customizations:
- **Multi-Target Analysis**: Adapt for subsidiary or partner analysis
- **Threat Actor Profiling**: Include adversary-specific intelligence
- **Compliance Mapping**: Align findings with regulatory requirements
- **Risk Scoring**: Implement quantitative risk assessment metrics

---

## 🏷️ Tags

`#osint` `#reconnaissance` `#information-gathering` `#passive-recon` `#threat-intelligence` `#social-engineering` `#attack-surface` `#penetration-testing` `#cybersecurity` `#ethical-hacking`

---

## 📊 Effectiveness

- **Accuracy**: ⭐⭐⭐⭐⭐ (Excellent - Comprehensive and detailed analysis)
- **Consistency**: ⭐⭐⭐⭐ (High - Reliable across different targets)
- **Response Time**: ⭐⭐⭐ (Medium - Thorough analysis takes time)
- **Actionability**: ⭐⭐⭐⭐⭐ (Excellent - Direct security testing guidance)

---

## ⚠️ Limitations

- **Authorization Required**: Only use with explicit written permission
- **Legal Compliance**: Must comply with applicable privacy and data protection laws
- **Accuracy Dependency**: Quality depends on publicly available information
- **Time Sensitivity**: Information may become outdated quickly
- **Scope Boundaries**: Must respect defined engagement boundaries

---

## 📚 Related Prompts

- [Vulnerability Scanning](./vulnerability-scanning.md) - Technical vulnerability assessment
- [Social Engineering Assessment](./social-engineering.md) - Human factor testing
- [Network Mapping](../network-security/network-mapping.md) - Infrastructure analysis
- [Web Application Testing](../web-application/owasp-top10.md) - Application security assessment

---

## 🔒 Security Notes

1. **Always obtain written authorization** before conducting any reconnaissance
2. **Respect privacy boundaries** and applicable laws
3. **Document your activities** for accountability and reporting
4. **Use information responsibly** and protect sensitive findings
5. **Follow responsible disclosure** practices for any vulnerabilities found

---

*These prompts are designed to enhance authorized security testing activities. Use responsibly and ethically.*