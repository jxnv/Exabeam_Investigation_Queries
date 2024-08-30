# Exabeam_Investigation_Queries

## Detailed Table of Events Filtered by Key Artifacts
```exabeam
SELECT
    timestamp AS "Timestamp", 
    user AS "UserName", 
    index, 
    source, 
    sourcetype, 
    eventtype, 
    action, 
    destination AS "Destination", 
    source_ip AS "Source_IP", 
    destination_ip AS "Destination_IP", 
    application AS "Application", 
    status, 
    signature
FROM events
WHERE KeyArtifact IN (event_name, source, destination, action, etc.)
ORDER BY timestamp ASC
```
## 24 Hour Notable User review
```exabeam
SELECT 
    timestamp AS "Timestamp", 
    user AS "UserName", 
    event_type AS "EventType", 
    source_ip AS "Source_IP", 
    destination_ip AS "Destination_IP", 
    action AS "Action", 
    application AS "Application", 
    status AS "Status"
FROM events
WHERE user = 'KeyArtifact'
AND timestamp >= NOW() - INTERVAL '24 HOURS'
ORDER BY timestamp ASC
```
