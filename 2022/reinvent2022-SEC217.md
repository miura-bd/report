# [NEW LAUNCH!] Detecting vulnerabilities in AWS Lambda functions using Amazon Inspector

## description

Developers are moving toward serverless compute, like AWS Lambda, for reduced infrastructure management, more efficient scaling, and reduced costs, but serverless workloads must be monitored for vulnerabilities in application code. In this session, learn how you can now use Amazon Inspector to detect vulnerabilities in your AWS Lambda functions in addition to software vulnerabilities and unintended network exposure in Amazon EC2 and container-based workloads. Learn now Amazon Inspector automatically discovers and inventories all existing and newly created Lambda functions for scanning and continually monitors to automatically detect issues. Inspector gives you a single view of your workload vulnerabilities and helps you prioritize remediation through its highly contextualized severity scoring.

## memo

### What is Amazon Inspector?

- 自動で継続的に vulneralility and unitended network についてスキャンしてくれる管理サービス
- what solve?
  - build for cloud
  - manage vulnerabilities in near real time
  - Consolidated solution for all compute types
  - Automated patching and ticketing
- How Amazon Inspector work
  - Frictionless activation and management
    - one-click activation
    - integration with AWS Organization
    - Auto-activation of new accounts
    - Security by default with simple organization level configuration
    - centralized view for the administrator account, while individual accounts can view their account-specific information
  - Continual vulnerability monitoring
    - Automated discovery of all resources
    - Findings in real time through continual vulnerability and networl reachability scanning
    - Intelligent algorithm determines what to scan, when to scan, or how often to scn based on event triggers:
      - A new software package is installed
      - An instance is patched
      - A new CVE is published
  - Prioritized and contextualized results
    - Amazon Inspector risk score is 
      - Netrwork exposure of an instance
      - Exploitability details
      - Potential security threats
    - 


### Security for serverless functions


### What's new?

- Added support for Lambda functions
  - With this expanded capability, Amazon Inspector now identifies software vulnerabilities (EVWs) in application package dependencies used in the Lmabda functon code and associated layers.
    - AWS Organizations
    - Automated discovery and continuous monitoring of all functions
    - Easy prioritization and remediation with exploitability and fixed-in package details
    - EventBridge
  - A single pane of glass for bulneravilities across all resources



### Demo

- Organizations のコンソールから設定
- Inspector のコンソールからアカウントを指定
- 