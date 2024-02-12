<h1>Azure-RBAC-Management</h1>

<h2>Description</h2>

<h3>Project Overview:</h3>
<p>The Azure-RBAC-Management project aims to implement Role-Based Access Control (RBAC) in Microsoft Azure for efficient management of access to Azure resources.</p>

<h3>Key Objectives:</h3>
<p>The primary objectives of the project are to establish RBAC roles and permissions, ensure least privilege access, and streamline access management for Azure resources.</p>

<h2>Languages and Utilities Used</h2>

- <b>Azure CLI</b>
- <b>PowerShell</b>
- <b>Azure Portal</b>

<h2>Environments Used </h2>

- <b>Microsoft Azure Cloud</b>


<h2>Program walk-through:</h2>

<h2>A. Executive Summary</h2>

<p>To support expansion SWBTL LLC, relies on IT systems hosted in leased data centers. Due to escalating costs, service interruptions, and cybersecurity concerns it has prompted upper management to move to Microsoft Azure cloud services. The move over to Azure addresses legacy authentication needs, helps integrate existing infrastructure, and support scalable deployment of applications and resources. Initial migration will focus on key departments such as marketing, accounting, and IT. Concerns over compliance and cybersecurity risks prompt a focus on prioritized business requirements. The goal will be to minimize risks, ensure compliance, and strengthen cybersecurity measures. In summary, the shift to Azure reflects a strategic move towards scalability and efficiency.</p>

<h2>B. Proposed Course Of Action</h2>

<p>The chosen service model for this will be IaaS (Infrastructure as a Service). This was deemed to be the best course of action for what the company had planned due to the ability to deploy and control multiple operating systems, virtual machines, and custom applications. It also allows the company to retain flexibility and control over their IT environment.</p>

<p>The regulatory compliance present will be FISMA, The Federal Information Security Modernization Act (FISMA) defines a framework of guidelines and security standards to protect government information and operations. FISMA requires all federal agencies to develop, document and implement agency-wide information security programs (CMS Information Security & Privacy Group 2024), and PCI DSS, The Payment Card Industry Data Security Standard (PCI DSS) is a set of security standards designed to ensure that ALL companies that accept, process, store or transmit credit card information maintain a secure environment, (Payment card industry data security standard (PCI DSS) faqs 2024), and also will abide by the upcoming NIST SP 800-53 assessment.</p>

<p>Security benefits include that with IaaS the company can implement strong security controls at the infrastructure level which can include network segmentation, encryption, and identity management. IaaS also offers scalability to accommodate a growing environment while maintaining security posture. The azure cloud also provides a centralized management tool for monitoring, logging and security policy enforcement simplifying security management.</p>

<p>Some potential security threats can include potential misconfigurations. Misconfigurations in IaaS deployment can lead to vulnerabilities therefore it is essential to ensure proper configuration of all the new settings, access controls, and network policies. Another risk is that ensuring data protection and compliance with regulatory requirements can become challenging in a cloud environment. The company will need to implement encryption, access controls and auditing will become important to maintain compliance.</p>

<h2>C. Role Based Access Control</h2>

<h3>C1. RBAC Recommendations</h3>

<p>In order to maintain security least privilege will be assigned using RBAC. Three recommendations include custom RBAC roles, hierarchical RBAC assignment and regular RBAC audits and reviews. To ensure least privilege and make sure no individuals purposefully or accidentally create a security threat RBAC will limit access to responsibilities based on someone's role. For example, a person in the marketing department will only be able to access files in relation to their specific job adhering to the idea of least privilege. The second would be hierarchical RBAC assignment meaning that job roles that are assigned in each department possess a structure to ensure that access permissions are granted based on their current position. For example, a department manager would possess a higher level role with more privileges than an entry level worker. The last recommendation would be RBAC audits and reviews. It is very important in this system that audits and reviews are conducted to ensure that access permissions are assigned correctly and especially if someone changes departments or leaves the company. It will also be important to detect anomalies or unauthorized access attempts while also monitoring and enforcing compliance. Also another recommendation could be to implement PIM, “To protect privileged accounts from malicious cyber-attacks, you can use Microsoft Entra Privileged Identity Management (PIM) to lower the exposure time of privileges and increase your visibility into their use through reports and alerts. PIM helps protect privileged accounts by providing just-in-time privileged access to Microsoft Entra ID and Azure resources. Access can be time bound after which privileges are revoked automatically” (TerryLanfear, 2024).</p>

<h3>C2. RBAC Configuration</h3>

<p>In order to configure the RBAC controls in Azure custom roles were created with each department. The IT department administrators received owner privileges and full control over the Azure Cloud System. Next, the marketing team received only read permissions over files they need for their job and the accounting team received special Billing Reader privileges meaning they can see only the necessary financial information needed. To ensure hierarchical structure the managers and admins received higher tier privileges while the regular employees mostly only got read permissions to ensure least privilege. Permissions were inherited logically within the hierarchy. For the last part audits and reviews would be scheduled every week to evaluate how effective the access controls would be. A compliance review will also be completed once a month while reviews for anomalies and privilege escalation will be done daily.</p>

<p>Members of the accounting team were given Billing Reader permissions which allow read permissions only over files needed specifically for the accounting departments. While management received data owner privileges.</p>

<p>Members of the IT team were given admin privileges and were given ownership of the resource group.</p>

<p>Higher members of the IT team including admins were given owner privileges while regular IT members were given contributor privileges to ensure hierarchical privileges are being kept. Its management was also RBAC owner so they are the only one who can rearrange or write into RBAC rules.</p>

<p>The marketing team also received only read permissions for specific documents related to their department.</p>

<h2>D. Encryption</h2>

<h3>D1. Encryption Implementation</h3>

<p>In order to ensure best practices are being used for the Azure Key Vaults, configure access policies will be enforced to the principle of least privilege. Only the necessary users in each resource group will receive access to the keys stored in the Key Vault. Another feature will be to include a key rotation policy. Key rotation helps mitigate the risk associated with compromised keys. The rotation will be automatically scheduled or it is also possible to do manual rotation. Also, the key vaults and resource groups have been rearranged in order to compliment each other based on what group will hold what keys.</p>

<h3>D2. Encryption Recommendations</h3>

<p>Two recommendations for data encryption with Azure key vaults include Data-At-Rest encryption. Utilizing Azure disk encryption or Azure storage Service Encryption to encrypt data stored in virtual disks or storage accounts. Azure Disk Encryption is a new capability for encrypting your Windows and Linux virtual machine disks. Azure Disk Encryption uses the industry-standard BitLocker feature of Windows and the dm-crypt feature of Linux to provide volume encryption for the OS and the data disks (TerryLanfear, 2024). This will ensure that data remains encrypted when stored in Azure services providing an extra layer of defense. As for Data-in-Transit encryption, it's important to store and manage TLS certificates. Also you can configure Azure to use certificates stored in key vaults for encrypting communication channels. Also secure communication protocols such as HTTPS for web apps are also important. Using azure to centrally manage TLS certificates in the Azure Key Vault will ensure secure communication channels between services and clients.</p>

<p>Keys have been rearranged to fit in with the resource group they belong to.</p>

<p>The keys for the accounting resource group are only given to members of the key administrator team.</p>

<p>The keys for the accounting resource group are only given to members of the key administrator team.</p>

<p>The keys for the accounting resource group are only given to members of the key administrator team.</p>

<h2>E. Back Ups</h2>

<h3>E1. File Backup Configuration</h3>

<p>As described Azure backup can be“An important part of your organization's BCDR strategy is figuring out how to keep corporate workloads and apps running when planned and unplanned outages occur. Azure Site Recovery helps orchestrate replication, failover, and recovery of workloads and apps so that they're available from a secondary location if your primary location goes down” (TerryLanfear, 2024). In order to configure file backup settings we must first look at the company policy. Using Azure you can easily configure it to backup based on the company expectation. Listed in the review it explains that a daily backup will be performed at 7 p.m EST on all servers. This ensures a daily backup to fall into the company objective of 1 RPO per day. The next policy is the retention policy which wants backup snapshots to be maintained for 45 days. This is also very easy to set up in Azure using the Azure Backup service.</p>

<p>This shows the azure backup settings needed to ensure it matches with the company business requirements.</p>

<h3>E2. File Backup Explanation</h3>

<p>The policy listed above meets both RPO and RTO requirements by configuring daily backups at 7 EST. The 45 day retention policy is being used in order to comply with industry standards and regulations. It allows the company to retain the historical backup points to meet compliance obligations.</p>

<h2>F. Division of Responsibility</h2>

<p><strong>Responsibilities</strong></p>
<p>To describe the division of responsibilities between the company and cloud service provider we must first take into account that we decided to implement Infrastructure as a service or IaaS. The company will be responsible for data security which includes securing the data and ensuring its protection on VMs and storage systems provisioned on azure. The company is also responsible for IAM or identity and access management, network security, and compliance and regulatory compliances. Meanwhile Azure will be responsible for physical data center security, network infrastructure, virtualization infrastructure, computer infrastructure, data center operations, security of the cloud, and physical and environmental controls to ensure all services remain running.</p>

<p>Shared responsibilities between the two include security of operating systems. While azure manages the underlying infrastructure the company is responsible for securing their virtual machines and operating systems running on Azure.  Data security is another area where Azure does provide secure storage services but the company is responsible for managing and protecting the data stored in Azure. The third would be network security in which Azure provides the infrastructure but the company is responsible for securing the network configurations, subnets and network security groups. IAM also can be considered shared as Azure provides Azure Active Directory but the company is responsible for managing user identities, access control and authentication mechanics.</p>

<h3>F1. Risks</h3>

<p>Three risks assumed by the company include a data security risk, IAM risk, and compliance and regulatory risk. The first risk is that the company will assume responsibility for securing data and access controls in the cloud environment. Without proper configuration and monitoring there will always be a risk of data breaches or unauthorized access which can result in loss of sensitive information and compliance violations. The risk of this would be High as data breaches can lead to financial loss, reputation damage, and regulatory penalties.</p>

<p>The second risk is identity and access management risk. When managing user identities and access controls within the cloud it is under the company's responsibilities. Inadequate IAM practices may lead to unauthorized access or insider threats which can compromise system integrity and confidentiality. The risk factor can be considered medium depending on whether what privileges the insider threat had or what data was accessed.</p>

<p>The last risk would be the compliance and regulatory risk. The company is responsible for adhering with compliance regulations such as FISMA and PCI DSS and compliance with such requirements can result in legal consequences, fines, and loss of contacts. The risk factor is high due to the severity of the penalties, business disruptions, and damage to the companies reputations.</p>

<h3>F2. Compliance Recommendations</h3>

<p>In order to mitigate and prevent these risk recommendations have been created. To minimize the first risk it is important to conduct regular security audits, and assessments of the cloud environment to identify vulnerabilities, misconfigurations and compliance gaps. Automated security tools such as SIEMs, and SOARs are essential to assist security professions in their reviews. Regular audits help mitigate risk proactivity. To protect RBAC controls it is important to ensure least privilege principles are being implemented. Another important inclusion would be MFA and a PAM solution to mitigate the risk of privilege escalations and insider threats. Strong IAM practices enhance security by reducing the risk of unauthorized access while maintaining industry standards and best practice.</p>

<p>To ensure compliance and protect data it is important to include encryption and safeguards for protecting customer data. Key management system described earlier, and data loss prevention technology will assist in this process. Ensuring data safety helps the organization comply with standards such as FISMA and PCI DSS.</p>

<h2>G. Potential Threats</h2>

<p>Some potential threats include unauthorized access, insider threats of cyberattacks targeting vulnerabilities in the cloud infrastructure. Breaches can lead to exposure of sensitive information, financial losses and damage to reputation. Mitigation for this threat includes encryption, access controls, and monitoring tools. Also a solution would be to include Azure's Microsoft Defender for Cloud which as described can “ provide integrated security monitoring and policy management across your Azure subscriptions. It helps detect threats that might otherwise go unnoticed, and works with a broad ecosystem of security solutions” (TerryLanfear, 2024). Also enforcing strong authentication mechanisms such as MFA, and employing continuous monitoring and threat detection solutions such as SIEMs, SOARS, ids, ips. Regular audits, and penetration testing can also help identify and mitigate vulnerabilities before they are exploited.</p>

<p>Another threat can be downtimes or service interruptions. Downtimes in the cloud infrastructure can disrupt business operations, leading to productivity loss, revenue loss, and customer losses. To mitigate this it becomes important to implement redundancy and failover mechanics to ensure backups of critical services and applications. Azure can deploy availability sets and regions to distribute workloads across multiple data centers for fault tolerance. Data recovery plans and incident response also help mitigate these issues when they occur.</p>

<p>The last threat is compliance violation. Since the company has to follow PCI DSS and FISMA it is essential to implement these when upgrading to the Azure cloud environment. To mitigate this it is important to implement a fool proof compliance management process to ensure regulations are met. Regular audits and assessments are also essential.</p>

