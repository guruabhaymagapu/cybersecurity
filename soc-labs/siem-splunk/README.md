### Day 1 – SIEM Environment Setup

- Installed and configured Splunk Enterprise locally. Verified SIEM   
  backend functionality by executing SPL query to retrieve server information.

### SPL Query Used

``` spl
| rest /services/server/info
```


### Day 2 – Windows Log Ingestion

- Installed Splunk Universal Forwarder (UF) on the Windows host.
- Configured forwarding to Splunk Indexer on 127.0.0.1:9997.
- Created custom index: windows.
- Onboarded Windows Security logs.
- Verified ingestion using Splunk Web and CLI (splunk list forward-server).

``` spl Query Used
| index=windows

```
Confirms that logs from the Windows host are successfully ingested into the windows index.

### Screenshots

- day2_splunk_web.png – Splunk Web running
- day2_receiving_port.png – Receiving port 9997 enabled
- day2_windows_index.png – Custom index created
- day2_active_forwarder.png – Active forwarder verified
- day2_index_search_results.png – Ingestion results

### Day 3 – Windows Failed Login Detection (Brute-Force Use-Case)

- Simulated multiple failed login attempts on Windows using a local test account (SOC_Test) to generate authentication failure events.
- Verified ingestion of EventID 4625 (Failed Logon) in the windows index within Splunk Enterprise.
- Extracted relevant fields (TargetUserName, IpAddress) from XML logs using SPL.
- Built brute-force detection logic by identifying ≥ 5 failed login attempts from the same IP address.
- Created a scheduled alert to detect multiple failed login attempts in near real-time (every 5 minutes).
- Configured alert severity as High to represent potential brute-force activity.
- Developed a dashboard panel to visualize failed login attempts over time for SOC monitoring.

```SPL Query Used
index=windows source="WinEventLog:Security" "<EventID>4625</EventID>"
| rex field=_raw "<Data Name='TargetUserName'>(?<TargetUserName>[^<]+)</Data>"
| rex field=_raw "<Data Name='IpAddress'>(?<IpAddress>[^<]+)</Data>"
| stats count by TargetUserName IpAddress
| where count >= 5
| sort -count
```

### Challenges Faced

- Windows Security logs were ingested in XML format (renderXml=true), which prevented direct field-based searching using EventID=4625.
- Failed logon events were present inside the _raw field as XML tags (e.g., <EventID>4625</EventID>), requiring manual field extraction using SPL rex.
- Failed login attempts from the Windows lock screen using Microsoft Account / PIN did not generate EventID 4625 events.
- Local account authentication attempts were required to reliably generate EventID 4625 (Failed Logon) events for brute-force detection testing.

### SOC Relevance

In enterprise environments using Splunk Enterprise:

- Different authentication methods may generate different Windows Event IDs.
- Detection rules based solely on lock screen login failures may miss brute-force attempts.
- Simulated network authentication attempts (e.g., via net use) can generate Logon Type 3 failures for testing detection use-cases.

### Screenshots

day3_failed_login_bruteforce_stats.png
- SPL query results showing multiple failed login attempts (EventID 4625) from the same IP address.
day3_failed_login_alert_created.png
- Scheduled alert configuration for detecting multiple failed login attempts in Splunk Enterprise.
day3_failed_login_dashboard_panel.png
- SOC Security Monitoring Dashboard panel visualizing failed login attempts over time.