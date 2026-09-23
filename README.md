# DevSecOps
# What is DevSecOps?

DevSecOps is the practice of integrating security testing into every stage of the software development process. It brings together tools and processes that encourage collaboration between developers, security specialists, and operations teams so they can build software that is both efficient and secure. ([AWS](https://aws.amazon.com/what-is/devsecops/))

The name stands for **Development, Security, and Operations**. It's an extension of the DevOps practice, where each term describes the different roles and responsibilities software teams take on when building applications. ([AWS FR](https://aws.amazon.com/fr/what-is/devsecops/))

# Why is DevSecOps important?

In traditional development, security was often bolted on at the end, right before release, and handled by a separate team. That worked when release cycles were measured in months or years. Modern software ships continuously, sometimes many times a day, and a late-stage security gate becomes a bottleneck.

DevSecOps addresses this by "shifting security left": moving security checks earlier into the development lifecycle so issues are caught when they're cheap and fast to fix rather than after deployment. The core principles are shifting security left, emphasizing automation, building in proactive defense, and relying on continuous monitoring. ([Wiz](https://www.wiz.io/academy/application-security/aws-devsecops))

# How DevSecOps works (end to end)

Security is embedded at each phase of the pipeline rather than at a single checkpoint:

1. **Plan / Design** — Threat modeling and defining security requirements before code is written.
2. **Code** — Developers check for security flaws as they write. Static analysis tools scan source code in the IDE and at commit time.
3. **Build** — Automated build steps run **SCA** (software composition analysis, for vulnerable dependencies) and **SAST** (static application security testing).
4. **Test** — Pre-release testing includes **DAST** (dynamic application security testing) against the running app, plus checks for things like authorization (users access only what they need) and input validation (correct behavior on abnormal data). ([AWS](https://aws.amazon.com/what-is/devsecops/))
5. **Release / Deploy** — Security gates in the CI/CD pipeline block deployments that fail policy. Infrastructure as Code is scanned for misconfigurations.
6. **Operate / Monitor** — After go-live, the operations team keeps monitoring for issues, makes fixes, and works with security and development to ship updated versions. ([AWS](https://aws.amazon.com/what-is/devsecops/))

Integrating these measures directly into the CI/CD pipeline enables automated security testing at every stage, which accelerates finding and fixing security issues. ([AWS Security Blog](https://aws.amazon.com/blogs/security/automate-and-enhance-your-code-security-with-ai-powered-services))

# The DevSecOps culture

DevSecOps culture combines communication, people, technology, and process. (This is the section that loaded directly from the AWS page.)

**Communication** — Adoption starts with a cultural change driven by leadership. Senior leaders convey the importance and benefits of security practices to the DevOps team, and teams get the tools, systems, and support they need to adopt DevSecOps.

**People** — DevSecOps drives a cultural shift. Developers move beyond the traditional build/test/deploy roles and work closely with security experts to strengthen security throughout development.

**Technology** — Teams use technology to run automated security testing during development, checking apps for flaws without slowing delivery. For example, they use **Amazon Inspector** to automate continual vulnerability management at scale.

**Process** — Security testing and evaluation happen at every stage. Developers check for flaws while writing code; a security team then tests the pre-release app for vulnerabilities such as:
- **Authorization** so users can access only what they need
- **Input validation** so software behaves correctly with abnormal data

Teams fix flaws before release, and testing continues after launch. For example, teams have used **Amazon CodeGuru Reviewer** to detect security vulnerabilities, exposed secrets, resource leaks, concurrency issues, incorrect input validation, and deviations from AWS API/SDK best practices. ([AWS](https://aws.amazon.com/what-is/devsecops/))

# Benefits of DevSecOps

- **Faster, secure delivery** — Security keeps pace with continuous delivery instead of blocking it.
- **Lower cost of fixes** — Catching issues early is far cheaper than fixing them in production.
- **Reduced risk** — Continuous monitoring and proactive defense shrink the vulnerability window.
- **Improved compliance** — Automated checks and audit trails support compliance frameworks.
- **Better collaboration** — Shared ownership of security across dev, sec, and ops teams.

# Common challenges

- **Cultural resistance** — Shifting security ownership to developers requires buy-in and training.
- **Tool sprawl and integration** — SCA, SAST, DAST, and monitoring tools must fit smoothly into the pipeline.
- **Alert fatigue** — Automated scanners can generate noise; tuning and prioritization matter.
- **Skills gap** — Developers need security knowledge; security teams need automation skills.

# AWS services commonly used for DevSecOps

- **Amazon Inspector** — Automated, continual vulnerability management at scale. ([AWS](https://aws.amazon.com/what-is/devsecops/))
- **Amazon CodeGuru Reviewer** — ML-based static analysis for code quality and security (note: AWS has announced deprecation of CodeGuru Reviewer, so check current status before adopting). ([Medium](https://medium.com/@fiardikarizki/security-scan-with-aws-native-got-me-crazy-b44276e2e7b8))
- **AWS CodePipeline / CodeBuild / CodeCommit** — Automate delivery pipelines, build and test code, and host Git repos to build an early feedback loop that shifts security left. ([AWS Security Blog](https://aws.amazon.com/ko/blogs/security/implement-an-early-feedback-loop-with-aws-developer-tools-to-shift-security-left/))
- **Amazon CodeCatalyst + Amazon Inspector** — Securing the software supply chain. ([AWS DevOps Blog](https://aws.amazon.com/blogs/devops/securing-your-software-supply-chain-with-amazon-codecatalyst-and-amazon-inspector/))
- **Open-source integrations** — AWS pipelines integrate cloud-native and third-party SCA/SAST/DAST tools, plus services to aggregate security findings. ([AWS DevOps Blog](https://aws.amazon.com/es/blogs/devops/building-end-to-end-aws-devsecops-ci-cd-pipeline-with-open-source-sca-sast-and-dast-tools/))

---
(https://aws.amazon.com/what-is/devsecops/)
