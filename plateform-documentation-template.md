# <Client/Plateform Name>

## Emergency contacts
- Client side emergency contacts, if necessary link to [escalation matrix](../organization/escalation-matrix.md)
- Managed services technical manager
- Any relevant contact in organization (commercial manager, person involved)

## Links
- Internal Monitoring platform dashboard
- External Monitoring platform dashboard
- Graph dashboard
- Plateform service URL

## Plafeform Status

| Item | Status | Last test date |
|------|--------|----------------|
| Monitoring | Ok/Ko | |
| Backups and restoration | Ok/Ko | DD/MM/YYYY |
| DRP | Ok/Ko | DD/MM/YYYY |
| High Availability | Ok/Ko | |
| Software support | Ok/Ko | End of support date |


## General Diagram
```
               ┌──────────┐          ┌──────────┐
               │          │  VRRP    │          │
               │   LB 1   ├──────────┤   LB 2   │
               │          │          │          │
               └────┬─────┘          └─────┬────┘
                    │                      │
    ┌───────────────┼───────────────┬──────┴─────────┬───────────────┐
    │               │               │                │               │
    │               │               │                │               │
    │               │               │                │               │
┌───┴──────┐   ┌────┴─────┐   ┌─────┴────┐     ┌─────┴────┐   ┌──────┴───┐
│          │   │          │   │          │     │          │   │          │
│ Front 1  │   │ Front 2  │   │ Front 3  │     │ Back 1   │   │ Back 2   │
│          │   │          │   │          │     │          │   │          │
└───┬──────┘   └────┬─────┘   └─────┬────┘     └─────┬────┘   └──────┬───┘
    │               │               │                │               │
    └───────────────┼───────────────┴─────┬──────────┴───────────────┘
                    │                     │
                    │                     │
              ┌─────┴────┐          ┌─────┴────┐
              │          │ Replicate│          │
              │   DB 1   │◄────────►│   DB 2   │
              │          │          │          │
              └──────────┘          └──────────┘
```
## Per block specifications
### LB
- Link to generic lb software documentation
- Link to specific automation module used
- Plateform specifics (for exemple client vpn located on LB2 and link to the specifics of this VPN)
### Front/Back
- Link to generic lb software documentation
- Link to specific automation module used
- Plateform specifics
### DB
- Link to generic lb software documentation
- Link to specific automation module used
- Plateform specifics
## Network
- Ip ranges in use if possible linked to the IPAM objects
- Any special configuration to be noticed

## Client specific process
### Plateform access
- How to connect to different parts of the platform (hardware, vm)
- Client VPN in place
- (If specific) Naming convention applied to the client
### DRP
- Link to client drp document
### Data Backup
- Link to generic backups documentation
- Specific backup policy applied to the general backup process
- Specific backups in place for the client (if necessary)
### Data restoration
- Generic data restoration link
- specific client identification points
### Monitoring alert reaction
- Any specific action to perform in case of monitoring alert

## Plateform history (example)
### 15/08/2022
Adding Front 3 in the pool
### 26/09/2021 ~ 29/09/2021
Upgrade platform to debian 11
### 08/04/2021
Db replication crash, rebuild (Link to post mortem analysis)
### 30/02/2020
Plateform accepted in production
