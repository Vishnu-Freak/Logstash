# Logstash
This project showcases the use of Logstash to ingest, parse, and normalize structured security log data. The Logstash pipeline processes syslog-formatted security events and outputs structured JSON, making the data more suitable for SIEM integration and security analysis.

Project Structure
README.md: This file — describes the approach and configuration.

sample.log: Contains the raw security syslog log samples.

result.json: Sample output from Logstash showing the normalized JSON structure.

result_formatted.json: Sample output from Logstash in formatted JSON structure for better understanding.

logstash.conf: The Logstash configuration file used to parse and normalize logs.

How It Works
Ingestion
Input Plugin: The file input plugin reads from sample.log.

Filtering
Filter Plugin: The grok plugin is used to match and extract key fields from the raw syslog format.

Mutate Plugin: Removes unnecessary fields like host, ip, etc., to keep the output clean.

Output
Output Plugin: The file output plugin writes the normalized JSON to result.json.

Normalization Design
The configuration is designed to:

Support any log line with the same format.

Extract values like source_ip, hostname, severity, timestamp, etc., into clearly defined fields.

Maintain flexibility to adapt to new log values without changing the grok pattern drastically.

