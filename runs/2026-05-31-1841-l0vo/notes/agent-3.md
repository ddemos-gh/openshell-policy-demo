# Agent 3 Note

## Angle

Prevention policy should make credential exposure to agent stdout impossible by default, not merely detectable after logging.

## Findings

- Agents should never receive raw long-lived credentials when a scoped, short-lived, brokered credential can be used instead.
- Tool runners should redact secrets before stdout/stderr is returned to the agent, with deny-by-default handling for known secret fields, environment variables, headers, and token-like patterns.
- Commands that commonly print environment, config, debug traces, HTTP headers, or full request bodies should require explicit approval or run with automatic secret stripping.
- Incident policy should prohibit agents from echoing secrets back to the user or logs, including during debugging, error reporting, stack traces, and “show me the output” requests.
- Secret access should be isolated by task: only the minimum required credential should be mounted, only for the command that needs it, and removed immediately afterward.

## Evidence To Gather Next

- Audit recent agent logs for stdout/stderr lines containing environment dumps, authorization headers, `.env` contents, config files, or token-shaped strings.
- Review tool execution paths to confirm redaction happens before output is persisted, streamed to users, or added back into agent context.

## Open Questions

- Which credentials still require direct agent/tool access instead of brokered or short-lived alternatives?
- Should suspicious stdout be blocked entirely pending review, or redacted and allowed through with an incident flag?