# SRE - How to manage a Archivist shift

The purpose of this document is to describe the different steps
which need to be followed before, during and after a SRE shift in
the Archivist role.

Please refer to the ***Presentation*** if you need more context on
what this role is about.


- **Planning**
- **Role and Activities**
- **How to organize your Archivist shift**
    - **At the beginning of the shift**
    - **During**
    - **At the end of the shift**

# Planning

Please refer to the dedicated ***Shift SRE*** spreadsheet for the planning.

# Role and Activities

Accurate documentation and alarms are an essential part of running production systems, maintaining them and efficiently respond to customer requests, whether during a hurry or a day-to-day activity. That’s where the ***Archivist*** comes in.

The Archivist is in charge of:

- Periodically review customer and internal documentation, updating outdated information or removing them if not needed anymore
- Create a new or improve an existing documentation to handle and solve the alerts you may have encountered during a Responder or ***On-Call*** shift
- Create or improve generic documentation for handling recurring support requests
- Link documentation to the different alarms, to ease Responder and On-call shifts
- Challenge triggers accuracy and documentation, to ensure that we have meaningful alarms
- Challenge alerts going through Oncall and Responder shifts, in order to reduce noise and risk of monitoring fatigue ( especially during On-call shifts )
- Periodically go through the different tools to cleanup assets and obsolete items
- Review documentation written by others, in order to check if everything is clear enough and useful

# How to organize your Archivist shift

## At the beginning of the shift

- Prepare a list of tasks for your shift, e.g.
    - List of documentation you want or need to review or update
    - Pending tasks from a previous shift
    - Prioritize them

## During

- Review customer documentation
    - Check the accuracy of the information from the documentation
    - If you find an inaccuracy or outdated information
        - Try to find the up-to-date information and update the page accordingly
        - If the information does not seem relevant anymore, check with the platform owner if you can remove it
- Create or improve documentation to handle an alert
    - If you encountered an alert or a situation in the past and you had issue finding an accurate documentation
        - Try to find if there is any existing documentation for this situation, otherwise create one
        - Add useful information in the page: what was the alert, how did you investigate, how did you solve it?
- Challenge trigger accuracy
    - Through past situations or at random, check the relevancy of a trigger
        - Is this trigger relevant for the team?
        - Is this trigger actionable?
        - Is the threshold relevant?
    - Check with the platform owner or the team to propose an update on a trigger or threshold
- Challenge alerts going through On-Call and Responder shifts
    - Ask if an alert was relevant and actionable when it triggered a notification to the team member
    - Otherwise propose a change to the team
- Cleanup assets and items on the different tools we’re using internally
    - Check the dedicated page for more information: ***Cleaning up***
- Review documentation written by others
    - Check the recent changes or take documentation updates sent by another member
    - Review the change and comment if needed

## At the end of the shift

Once you’ve completed a shift, share information to the team, through email or Slack on our public team channel:

- Difficulties you may have encountered during your shift
- Documentation or any action you’ve done during your shift
- Request review from a platform owner when changing documentation or alerts


