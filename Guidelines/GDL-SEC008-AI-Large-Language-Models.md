# Artificial Intelligence (AI) - Large Language Models

| Document Information |
---|
| Category: Architecture Guidelines |
| Created: 05-07-2023 |
| Domain: Security |
| Author: paul.fitzgibbons@education.gov.uk |
| References: |
| [GDL-SEC005-Cloud-Platforms](../Guidelines/GDL-SEC005-Cloud-Guidelines.md) |

## Large Language Models (LLMs)

Large Language Models use machine learning techniques to build statistical models of natural language (i.e. English). The models are "trained" on large amounts of data that can be taken from the public domain or from private sources. Once "trained" the models can be used to generate responses to prompts. The responses can appear as if a human is responding or the AI can be programmed to respond in a variety of different styles.

While the responses can be stated with seeming confidence, there is a need to validate the responses as the algorithms can "hallucinate" responses under certain circumstances.

Use of large language models and AI within the department is in early stages and the Chief Technology Officer has requested that all use of these technologies are registered:

[DfE Intranet - ChatGPT and LLMs - a Guide to Experimenting Safely](https://educationgovuk.sharepoint.com/sites/dfe-home/SitePages/080323-Using-ChatGPT-and-other-Large-Language-Models-for-work-a-guide-to-experimenting-safely.aspx)

### Development using LLMs

This guideline provides general principles and links to other guidelines to support teams in the secure use of Large Language Models within development of their service(s) and to align with industry best practices. 

The appendices of these guidelines lists links to further reading materials which may be of use.

The method of how these are applied is not dictated within these guidelines as it will depend on the structure of the team which is managing and supporting the relevant service(s).

> Regardless of the team size and type, it is expected that the guidelines will be applied to service(s) and that other security requirements will be adhered to as a matter of course.

>Adherence to these principles will need to be demonstrated as part of ongoing service assurance with non-compliance reported and escalated if required.

As a general principle, Large Language Models are not a silver bullet, panacea or suitable for all tasks/problems. Use of Large Language Models and AI within services should involve Architecture teams to ensure alignment with business strategy and objectives. 

## Use of the guidelines

This guideline is **level 2** and part of a hierarchy which inherits the guidelines from its corresponding [**level 1** guideline](../Guidelines/GDL-SEC005-Cloud-Guidelines.md). The information provided within provides  specfic guidelines for the specific technology or capability area underneath the **level 1** guideline.

![Guidelines Hierarchy](../Guidelines/images/ESA-Guideline-Hierarchy.png)

This guideline is intended for Civil Servants, contract/contingent workers and Managed Service Providers (MSPs).

This guideline is non-exhaustive in nature. The rapid pace of development within Artificial Intelligence and Large Language Models means that new mechanisms may become available.  If for example, the LLM is being embedded in e.g a Web Application it would be expected that the OWASP top 10 would also apply.

You should engage with [the architecture team](mailto:security.architecture@education.gov.uk) to discuss any novel approaches to Artificial Intelligence and Large Language Models **BEFORE** you start any use or development activity.

**Aligment and exceptions** to the principles will be reviewed as part of assurance processes with the security and architecture professions to streamline governance, Exceptions will be approved or declined as relevant, with all decisions tracked with rationale for future reference.

**Updates or modifications** to the principles can be requested initially via the Architecture Community of Interest, and in the future with standard updates and iterations via GitHub.

## 1. Refer to the Level 1 guidance for Cloud Platforms

*The Cloud Platforms guidelines provide the baseline security and best practices*

### How?

* Follow the level 1 guidelines [here](../Guidelines/GDL-SEC005-Cloud-Guidelines.md)

* Review these guidelines along with the more specific guidelines to ensure your service will meet the standard best practice configuration expected by the Department

## 2. Ensure engagement with Privacy Teams/Data Protection Office has taken place and that your use of AI is known, approved and has been risk assessed.

### Why?
Reduces risk to the department from non-compliance with Data Privacy legal responsibilities and ensures that the department is managing responsibilities to data appropriately (General Data Protection Regulation, GDPR).

## 3. Review and apply the guidance from Open Web Application Security Project (OWASP)

*Applying Industry Best Practice to our use of AI reduces risk and ensures conscious and appropriate use of technologies*

### Why?

It is essential that we manage the use of Artificial Intelligence appropriately to protect the Department and our users from malicious use, reputational damage and privacy issues arising from disclosure of information. Adhering to industry best practice ensures that we only have access to the roles and permissions when we need them, as this reduces the risk if a user's account is compromised.

Utilising these guidelines also ensures that we take due care when utilising these technologies.

### How?

#### *OWASP Top 10 for Large Language Models (0.5) - July 2023*

**LLM01: Prompt Injections**

*Prompt Injection Vulnerabilities in LLMs involve crafty inputs leading to undetected manipulations. The impact ranges from data exposure to unauthorized actions, serving attacker’s goals.*

**LLM02: Insecure Output Handling**

*These occur when plugins or apps accept LLM output without scrutiny, potentially leading to XSS, CSRF, SSRF, privilege escalation, remote code execution, and can enable agent hijacking attacks.*

**LLM03: Training Data Poisoning**

*LLMs learn from diverse text but risk training data poisoning, leading to user misinformation. Overreliance on AI is a concern. Key data sources include Common Crawl, WebText, OpenWebText, and books.*

**LLM04: Denial of Service**

*An attacker interacts with an LLM in a way that is particularly resource-consuming, causing quality of service to degrade for them and other users, or for high resource costs to be incurred.*

**LLM05: Supply Chain**
LLM supply chains risk integrity due to vulnerabilities leading to biases, security breaches, or system failures. Issues arise from pre-trained models, crowdsourced data, and plugin extensions.

**LLM06: Permission Issues**

*Lack of authorization tracking between plugins can enable indirect prompt injection or malicious plugin usage, leading to privilege escalation, confidentiality loss, and potential remote code execution.*

**LLM07: Data Leakage**

*Data leakage in LLMs can expose sensitive information or proprietary details, leading to privacy and security breaches. Proper data sanitization, and clear terms of use are crucial for prevention.*

**LLM08: Excessive Agency**

*When LLMs interface with other systems, unrestricted agency may lead to undesirable operations and actions. Like web-apps, LLMs should not self-police; controls must be embedded in APIs.*

**LLM09: Overreliance**

*Overreliance on LLMs can lead to misinformation or inappropriate content due to “hallucinations.” Without proper oversight, this can result in legal issues and reputational damage.*

**LLM10: Insecure Plugins**

*Plugins connecting LLMs to external resources can be exploited if they accept free-form text inputs, enabling malicious requests that could lead to undesired behaviors or remote code execution.*

## Appendix A - Useful Links

[NCSC - ChatGPT and Large Language Models](https://www.ncsc.gov.uk/blog-post/chatgpt-and-large-language-models-whats-the-risk)

[DfE Intranet -Guide to Experimenting Safely](https://educationgovuk.sharepoint.com/sites/dfe-home/SitePages/080323-Using-ChatGPT-and-other-Large-Language-Models-for-work-a-guide-to-experimenting-safely.aspx)

[OWASP Top 10 for Large Language Models](https://owasp.org/www-project-top-10-for-large-language-model-applications/)

[OWASP Top 10 for Large Language Models (PDF)](https://owasp.org/www-project-top-10-for-large-language-model-applications/assets/PDF/OWASP-Top-10-for-LLMs-2023-v05.pdf)

[Andreeson Horowitz - AI Canon](https://a16z.com/2023/05/25/ai-canon/)

[Andreeson Horowitz - Emerging Architectures for LLM Applications](https://a16z.com/2023/06/20/emerging-architectures-for-llm-applications/)
