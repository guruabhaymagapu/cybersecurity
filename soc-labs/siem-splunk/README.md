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