# Security Policy

## Reporting
Please do not publish exploitable vulnerabilities in public issues. Use GitHub's private vulnerability reporting feature if enabled, or contact the repository maintainer privately through GitHub.

## Scope
Report unauthorized access, cross-user data exposure, authentication bypass, unsafe file handling, secret exposure, injection vulnerabilities, and privilege escalation.

## Project requirements
- Never commit credentials or API keys.
- Keep service-role secrets server-side.
- Enforce row-level security and server authorization.
- Validate uploaded files and structured AI output.
- Treat project documents and imported content as untrusted input.
- Do not expose private project data in logs.
