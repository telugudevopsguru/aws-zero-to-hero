### **Managing Disk Space Issues on Linux and Windows**

#### 1. **Linux `/data` Directory**

**Monitor Disk Space Usage on `/data` Directory**:
- **Metric**: `system.disk.in_use`
- **Query**: `avg(last_5m):avg:system.disk.in_use{mount:/data} by {host} > 85`
  - This triggers an alert if the disk usage on `/data` exceeds 85% over the last 5 minutes.

**Alert Message**:
```text
Disk space on the '/data' directory is over 85% usage on host {{host.name}}.
Current usage: {{value}}%. 
Please investigate the disk usage and consider cleaning up unnecessary files or increasing disk capacity.
```

**Options**:
- **Thresholds**: Choose your preferred thresholds (e.g., 85% or 90%).
- **Notify**: Set up notifications to Slack, email, etc., when the alert triggers.

#### 2. **Windows `D:` Drive**

**Monitor Disk Space Usage on `D:` Drive**:
- **Metric**: `system.disk.in_use`
- **Query**: `avg(last_5m):avg:system.disk.in_use{device:D:} by {host} > 85`
  - This triggers an alert if the disk usage on `D:` exceeds 85% over the last 5 minutes.

**Alert Message**:
```text
Disk space on the 'D:' drive is over 85% usage on host {{host.name}}.
Current usage: {{value}}%. 
Please investigate the disk usage and consider cleaning up unnecessary files or increasing disk capacity.
```
