## Context
This is a document I created and shared per request of our company's project management guild.  It is intended to highlight our engineering team's DevOps culture and successful ways of working with high SLAs, SLOs, and excellent customer service.  Our engineering team's name: SABA (SaaS Acceleration Business Applications)
   
## Overview  

All SABA applications run on Kubernetes and are monitored with New Relic synthetic monitoring. Application squads are lean; we have automated most everything, including Level 1 support. It is rare that we have major application issues.  However, in the event of a high severity problem, with minimal process the person on-call via PagerDuty rotation & supporting team can focus on fixing the problem.  

Automation provides scaffolding to give timely, transparent & sufficient communications to our stakeholders, both internal & external to our company.  Incidents are posted on Statuspage.io.   Additionally, incidents & status are posted in the stakeholder slack channels.

Subsequent to each high severity issue, the team conducts RCA, root cause analysis, in a slack channel dedicated to the specific incident, supplemented with video conference session if needed.  The RCA process fosters team learning from situations & helps the team take action to make adjustments to strengthen operations.  

*Figure 1: Our DevSecOps support model for critical issues*
![DevSecOpsSptModel-Critical](https://github.com/testness/work-samples/assets/10069969/f36b0bc9-3b31-43c5-a0a4-810efcad5cce)

*Figure 2: Our support model for non-critical issues*
![DevSecOpsSptModel-NonCritical](https://github.com/testness/work-samples/assets/10069969/e95e429e-d509-4e2c-affe-672299ec1489)

SABA uses slack stakeholder support channels & GitHub Enterprise so that any employee can quickly & easily submit issues for investigation & easily watch ticket progress.  Note that for the external facing application, PX, PX users submit tickets via SystemA in their local geography.  Employees in SystemA escalate via GitHub\slack if needed.  

All GitHub support projects are evaluated weekly for measurement against SLOs for response time, closure, & other health metrics.  
