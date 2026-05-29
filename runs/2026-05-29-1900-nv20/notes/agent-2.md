# Agent 2 Note

## Angle

Security controls for sandboxed coding agents should be evaluated by how well they prevent credential exposure, unauthorized network access, and unintended data movement.

## Findings

- The most important control is strict credential isolation: agents should not inherit ambient secrets from the host shell, developer dotfiles, cloud CLIs, package managers, SSH agents, or browser/session stores unless explicitly granted.

- Network access should default to deny or require scoped approval. Sandboxes that allow unrestricted outbound traffic make it easier for compromised dependencies, prompt-injected code, or malicious tests to exfiltrate repository contents and credentials.

- Approval boundaries matter more than UI labels. Teams should verify whether “read-only,” “sandboxed,” or “restricted” modes actually block file writes, process escapes, credential discovery, local socket access, and network calls.

- Logs and transcripts are part of the security surface. Agent prompts, command output, stack traces, and generated patches can accidentally include secrets, so evaluation should include redaction behavior and retention controls.

- Dependency execution is a high-risk path. Installing packages, running build scripts, invoking test suites, or executing project tooling can trigger arbitrary code, so these actions need separate policy controls from simple file inspection.

## Evidence To Gather Next

- Run controlled canary-secret tests to confirm whether agents can discover, print, persist, or exfiltrate fake credentials from environment variables, home directories, config files, SSH agents, and cloud CLI caches.

- Review sandbox enforcement documentation and perform practical network tests covering DNS, HTTP(S), package registries, local network access, metadata endpoints, localhost services, and raw socket behavior.

## Open Questions

- How granular should approval policies be: per command, per capability, per destination, per repository, or per session?

- What level of network restriction is practical without making common development workflows, such as dependency installation and test execution, too slow or brittle?