<h1>Postmortem</h1>
<h2>Issue Summary:</h2>
On March 2nd, 2023, our web application experienced an outage that lasted for 2 hours and 30 minutes from 1:00 PM to 3:30 PM Eastern Standard Time (EST). During this time, our users were unable to access the login page and were receiving error messages when attempting to do so. Approximately 50% of our users were affected by this outage.

<h2>Root Cause:</h2>
The root cause of the issue was a misconfiguration in the load balancer that prevented incoming requests from being forwarded to the backend servers. The misconfiguration occurred during a routine update of the load balancer configuration.

<h2>Timeline:</h2>

1:00 PM EST: The outage was detected when the monitoring system sent an alert to the operations team.
1:05 PM EST: The operations team attempted to restart the affected servers but found no issues.
1:10 PM EST: The team started investigating the load balancer configuration as a possible root cause.
1:30 PM EST: The team identified the misconfiguration in the load balancer and attempted to fix it.
1:40 PM EST: The team discovered that the fix did not resolve the issue and continued their investigation.
2:00 PM EST: The team escalated the issue to the development team for additional support.
2:15 PM EST: The development team identified the root cause of the issue and implemented a fix.
3:00 PM EST: The operations team confirmed that the issue was resolved, and the application was restored to normal functionality.
3:30 PM EST: The monitoring system sent a confirmation that the application was functioning correctly.
Misleading Investigation/Debugging Paths:
The initial investigation focused on the server-side components, including the backend servers and the database, which were found to be functioning correctly. The team also focused on the network connectivity between the servers, which was also found to be normal. This resulted in a delay in identifying the root cause of the issue.

<h2>Incident Escalation:</h2>
The issue was initially escalated to the development team for additional support.

<h2>Resolution:</h2>
The development team identified the misconfiguration in the load balancer and implemented a fix to correct it. The team also verified that the application was functioning correctly after the fix.

<h2>Corrective and Preventative Measures:</h2>
To prevent similar issues in the future, the following tasks will be completed:

Automated load balancer configuration testing will be implemented to verify configuration changes.
Load balancer configuration changes will be reviewed by a second person before being applied to the production environment.
Improved monitoring of the load balancer and backend servers will be implemented to quickly detect and diagnose similar issues.
