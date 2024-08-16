SERVER OUTAGE INCIDENT REPORT

On 16th August 2024, we experienced a server outage on all our server infrastructure which resulted in clients being unable to use our services. We would like to first sincerely apologize for the financial loss our clients may have incurred during the outage.

ISSUE SUMMARY.
On 16th August 2024, we experienced downtime on all our server infrastructure that lasted for 32 minutes. As a result, our clients experienced a `http 500 error` which impacted their businesses 100% as they were unable to access our services. The root cause of the downtime was determined to be a failure to properly test out all implemented upgrades before pushing ro production servers. 
	Time (GMT +3) 		Actions
	13:15			Upgrade implementation begins
	13:35			Server outage begins
	13:36			Pagers alerted on-call team
	13:40			On-call team acknowledges
	13:45			Rollback initiation begins
	13:50			Succesful rollback
	13:55			Server restarted
	13:57			100% traffic back online
ROOT CAUSE.
At 13:15 (GMT +3), a server upgrade was initiated across all our production servers without first releasing our test environments and performing all necessary unit testing. A part of the upgrade that was shipped required authentication from a 3rd party software. This new authentication is not supported on the current version present on our servers which resulted in the downtime experienced. We were able to resolve this by performing a rollback to the server's previous state and thereafter upgrading the current version on our servers.

PREVENTION MEASURES.
- Pushing all intended changes first to our test environment before shipping to live servers.
- Increase the performance metrics threshhold to alert on-call engineers in the event of possible server crash.

