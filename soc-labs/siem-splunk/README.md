### Day 1 – SIEM Environment Setup

- Installed and configured Splunk Enterprise locally. Verified SIEM   
  backend functionality by executing SPL query to retrieve server information.

### SPL Query Used

``` spl
| rest /services/server/info
```
