# Encoder-Caption-Troubleshooting-Runbook
Purpose: Isolate missing, intermittent, delayed, or incorrect captions without disrupting a live production feed.

Sample Encoder Caption Troubleshooting Runbook
Purpose: Isolate missing, intermittent, delayed, or incorrect captions without disrupting a live production feed.
Scope: SDI caption encoder, iCap/Lexi caption source, SDI output, and downstream distribution. Example only; follow
approved site procedures and vendor documentation for the actual device.
1. Record impact
• Note start time and time zone, affected feed, symptoms, whether video/audio are affected, and whether captions are missing
at every endpoint or only downstream.
• Record encoder model, software version, caption source, and service selection in an authorized ticket.
• For live feeds, notify the production contact and follow the change/incident process before modifying settings or restarting
equipment.
2. Locate the failure
• Confirm SDI video reaches the encoder and that the captioned output feeds the expected downstream path.
• Check captions at the encoder output versus the downstream destination. If present at the encoder output, investigate the
downstream path.
• Confirm the intended caption service and source; for Lexi, verify the relevant module is enabled and configured for the
intended service.
3. Check connectivity and caption flow
• Check encoder iCap status and connection indicators.
• Check whether audio packet counts are increasing; verify audio source and level and caption provider/session status in iCap
Admin.
• Check caption activity indicators and relevant iCap log entries with timestamps.
• If Lexi is involved, verify its activation state and settings before concluding the network is at fault.
4. Correlate logs
• Compare the incident time with encoder and iCap events. If application logs are available in Amazon CloudWatch, search the
authorized log group and time window for timeouts, disconnects, errors, and session changes.
• Preserve only the minimum relevant sanitized excerpts for escalation; do not expose tokens, private customer data, or
internal endpoints.
5. Escalate and verify
• Escalate persistent or production-impacting faults to the appropriate engineering, network, caption-service, or production
team. Provide impact, start time, checks completed, sanitized log evidence, and the last known point where captions appeared.
• After an approved fix, verify audio reaches the caption source, caption activity resumes, and captions appear at the encoder
output and downstream destination.
• Document actions, verification results, root cause if confirmed, and preventive follow-up in the ticket.
Portfolio use: This is a generic sample based on public documentation, not an official Ai-Media procedure. Replace all
customer names, IDs, screenshots, access codes, logs, and internal procedures with fictional or lab data.
Public references: Ai-Media HD492 Manual (https://www.ai-media.tv/wp-content/uploads/Manual_HD492.pdf); AWS
CloudWatch Logs Insights documentation
(https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/AnalyzingLogData.html).
