https://tryhackme.com/room/agentwentrogue


---------

## The Agent-Driven Decision




### Your Case Bundle

Start the machine, then connect as the analyst user with the password Investigation2026!. The account is deliberately unprivileged, with no sudo rights, which is the right shape for an analyst account handling evidence.

No single source tells that story. The skill this room teaches is joining them, and the quickest way to see why is to put the plaintext logs on one timeline.

`$ lnav /opt/incident/*.log`



----------

## Triage the Action Trace

### Bucketing 279 Actions by Type
Before filtering for anything, we want the shape of the campaign. A distribution tells you where the volume is, and volume is where an agent-driven intrusion hides its one success. Each event in agent-trace.json carries the same seven fields: ts, action_id, phase, action_type, cmd, result, and refs. Two of those, action_type and phase, are the axes worth counting.

jq -r 'group_by(.action_type)[] | "\(.[0].action_type) \(length)"' /opt/incident/agent-trace.json
c2 33
cloud 10
dropper 81
exfil 5
k8s 10
pivot 1
recon 122
secret 16
source_control 1
