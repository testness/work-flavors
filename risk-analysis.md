## Context
As part of our agile team's Security and Privacy by Design (SPbD) process, this is a sample security threat risk analysis created in collaboration with my SRE (Site Reliability Engineer) colleague. As part of this process, dev teammates were prompted with Github pull requests for review and comments as well.  

This was created for an application that generated contractual documents into a single agreement, based on a selected product or products. Per product, the agreement pulled together a versioned unique copy of 5 separate documents into a single PDF file which was downloadable and also available to anyone with whom that unique URL was shared.  The web application was built with TypeScript, Angular, Node.js, MongoDB and running on Kubernetes.

We shared this MD file as a template for other teams to use as part of their ITSS (Information Technology Solutions and Services) standards as part of their security and compliance standards documentation and practices.  

## URLs inspected
* URL 1, a public url 
* URL 2, another public url

## Analysis

*Auth & Auth:*
* no authorization required, therefore risks are inside the application output, rather than someone getting access to something
they should not see
 - being able to fake generation of a document and share it even though it is not legit with any content

*PDF security:* 
* med risk
* purposeful security requirements were made in PDF generation [link Github item for traceability]
* demonstration & documentation [link Github item for traceability]
* best effort was made to be at and above consistent security level of pre-existant PDF uneditable files  

*app-jobs:* 
low risk
* this vector could be exploited if someone internal looked at source code and 
prepared a document that conformed to our parser's formatting requirements, input illegit content
& had access to the database to upload for publishing

*APIs:*
 * notes [linked] here with INGRESS details
ok.

*Pages:*
* site can be hosted in iframe as can the root part of the website 
in theory someone could take the content & host it elsewhere. If a third-party chose to host the application they might be able to sniff...
However, the user would be aware they were on the third-party site and are unlikely to be ...

*Denial of Service:*
* Business Criticality Value 5 
* DDOS protection built in from Akamai & PaaS also
* public services running in the background [link to appscan report]
* Reputational Damage

*Disfavored Users:*
 - bad github commits which is then reverted. 
 - interal would publish a rogue container. Logs would tell us, but we would have to know to look.
 - TravisCI (builds) currently runs as User A, low risk.  
 - hack the servers [link to appscan report]
 
 *Content hacking on client side*
 - plugin or rewriting content as it comes back from the API. vulnerability with plugins (example: ad block) taking content coming back & blocking content. Example: content enumeration section 3a. 3b. 3c. and content in section 3b is omitted.
low risk, not going to mitigate.
 - making the app do something bad. e.g. if user were logged in with their companyid & make the app order. console  -  - browser console shows header server nginx. main does this, too. - low risk.  
 - disgruntled developer drops in code that does something bad... reputational damage.  developer would be in violation of BCGs (Business Conduct Guidelines). code review would stop this.



 
