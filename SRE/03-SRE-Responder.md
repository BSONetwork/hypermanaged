# SRE - How to manage a Responder shift

The purpose of this document is to describe the different steps
which need to be followed before, during and after a ***SRE shift*** in
the Responder role.

Please refer to the Presentation if you need more context on
what this role is about.


- **Planning**
- **Roles and Activities**
    - **Responder Goals and explanation**
- **How to organize your Responder shift**
    - **Before**
    - **During**
    - **After**
- **Continuous improvement**

# Planning

Please refer to the dedicated ***Shift SRE*** spreadsheet for the planning.

# Roles and Activities

The Responder is in charge of:

- Respond to all alerts
- Handle or dispatch incoming Helpdesk tickets
- Challenge alerts and tickets priorities
- Handle alerts sent by the On-Call member

## Responder Goals and explanation

***Responder*** folks takes care of all the incoming alerts and helpdesk tickets for the hosting team.
Refresh the unassigned tickets, and is in charge of finding a way to handle the ticket and/or find someone responsible for the ticket and assign it to him.

At the end of his shift, all tickets need to be assigned, and/or solved if they are documented.
If for any result it’s not the case, the *Responder* needs to explain at the end of the shift the exact situation at the other one, who take the next shift.

**General advice to run as a ***Responder*** smoothly**

- Ask yourself how, you’ll handle the issue, if you were in charge of this, and do a proposition of this process to the platform owner and/or his backup
- If the issue and is resolution isn’t documented yet, begin a documentation of how you handled it and link this within the customer global documentation
- If the issue is already documented, try to apply the documentation and to solve the ticket by yourself!
- If you find some unclear documentation part, try to improve it
- If there is an alert who is firing in case of the issue produce, it’s a good idea to put the link of the documentation you produced inside the description of the alarm
- If there is no alarm to describe this, and you find we need an alarm to avoid the ticket to happen again, please discuss that frankly and with kindness to the platform owner and his backup. Stand-up and Todo-sync are a good place to discuss this

**Example of an incoming ticket :**

First answer to do whatever you’ll handle the ticket at the end or not with this message :

**“Dear valued Customer,
Thank you for reaching out to our SYSSRE support team. This is to confirm that we have received your ticket, and it is currently under review.
Our team is diligently examining the process, carefully reviewing documentation, and will soon initiate the necessary actions to address your concerns. We understand the importance of a prompt resolution and are committed to providing a timely solution.
Rest assured, once the action is deployed, we will promptly respond to this ticket to update you on the progress. This allows you to verify that the reported issue and/or request has been effectively resolved.
We appreciate your patience and understanding as we work towards ensuring your satisfaction.
Best Regards,
[Your Name] Support Team”**


Now I’m searching if there is a documentation to handle this ticket :

And I find 2 documentations.

- ***Mazars SC - Cloud - Deploy a datafix***
- ***Mazars SC - Datafixes***

I ask the person in charge, which one is the good documentation?

From what I understood, I need to perform a backup of the DB, and then run the asked update directly in the DB.

⇒ I’m doing what the customer is asking, and what the documentation is explaining.

I reply to the ticket and copy and paste all the result of what they asked :

# How to organize your Responder shift

## Before

- Plan a time for the shift transmission
    - Add yourself yo the oncall override calendar. See the ***on-call procedure.***
    - Need to communicate with the previous person in charge about what happened during his shift
    - Be sure to have all access already available
        - VPN
        - Different access ( *Stargate, Zabbix, Grafana Oncall ...* )

## During

- New ticket incoming
    - Send a first answer
    - Verify typologies and information on the ticket
    - Verify priority
    - Add the right tag on the tickets
- Prioritize the ticket management
    - Typology
    - Priority
    - Delay asked by customer
- Handle the demand
    - If possible, the person in charge must manage the ticket and resolved it
        - Knowledge of the resolution
        - Documentation available on the resolution
    - In the case of particular where knowledge isn’t on the hand of the person in charge
        - Ask the lead platform engineer
            - Who can manage the issue
            - Who the ticket needs to be assigned to
- Update documentation
    - If some improvement can be done on the documentation
        - Just go for it
        - Report the needs
        - Documentation for usual ticket treatment can be created when necessary
        - Inform R&D team if some automation can be done on the treatment
- Proactive monitoring
    - Verify the non-ack alarms ( Zabbix, Grafana Oncall, ... )
        - Create a proactive ticket
        - Ack the alarm if necessary, add a comment about the alert and why you ack it and the ticket number if applicable
    - Identify the false positive, and upgrade the monitoring
        - Deleted non-relevant alarms
        - Update the thresholds of false positives alarms
        - Update the alarms’ documentation

## After

- Inform the following shift
    - About the ticket which need to be manage
        - Unassigned, the tickets which need to be followed by the next shift
    - About the important situation which happened during the shift

# Continuous improvement

**Informs about :**
- Documentation updating needs
- Lack of information
    - Procedures
    - Person to contact