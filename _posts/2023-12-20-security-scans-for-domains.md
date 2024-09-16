---
title: Security Scans for Domains
tags:
  - cybersecurity
  - code
  - web
---
## Website Security
1. HTTP Strict Transport Security (HSTS) not enforced: Without HSTS enforced, people browsing this site are more susceptible to man-in-the-middle attacks. The server should be configured to support HSTS
2. X-Frame-Options is not deny or sameorigin: Browsers may display this website's content in frames. This can lead to clickjacking attacks.
3. CSP is not implemented: No valid Content Security Policy is implemented. This increases the risk of XSS and clickjacking attacks.
4. X-Content-Type-Options is not nosniff: Browsers may interpret files as a different MIME type than what is specified in the Content-Type HTTP header. This can lead to MIME confusion attacks.
5. CAA not enabled: The domain does not contain a valid Certification Authority Authorization (CAA) record. A CAA record indicates which Certificate Authorities (CAs) are authorized to issue certificates for a domain.
6. Weak cipher suites supported in TLS 1.2: Weak cipher suites can potentially be broken by a well resourced attacker, and should not be supported by the server unless very old devices or browsers must be supported.
7. Certificate not found on our revoked certificate list: The site's certificate chain was checked against our list of revoked certificates.
8. SSL available: SSL is supported for this site.
9. HTTP requests are redirected to HTTPS: All HTTP requests are redirected to HTTPS.
10. Does the Hostname match the SSL certificate? The site's hostname matches the SSL certificate.
11. SSL has not expired: SSL certificate has not expired.
12. Trusted SSL certificate: The certificate presented by this domain was issued by a trusted certificate authority.
13. No insecure SSL/TLS versions available: No insecure SSL/TLS versions are available for this site.
14. SSL certificate chain present in server response: A complete SSL certificate chain was presented by the server for this domain.
15. SSL chain certificates do not expire within 20 days: SSL intermediate and root certificates do not expire within 20 days.
16. SSL expiration period shorter than 398 days: The SSL certificate presented by the server has an expiration period shorter than 398 days.
17. SSL does not expire within 20 days: SSL certificate does not expire within 20 days.
18. Strong SSL algorithm: Industry standard SHA-256 encryption in use.
19. Not vulnerable to CVE-2014-0160 (Heartbleed): A bug in OpenSSL's implementation of the TLS heartbeat extension allows access to portions of memory on the targeted host e.g. cryptographic keys and passwords.
20. Not vulnerable to CVE-2014-3566 (POODLE): The server does not support SSLv3, and is not vulnerable to the POODLE attack.
21. Not vulnerable to CVE-2015-0204 (FREAK): The server does not offer RSA_EXPORT cipher suites, so clients are not vulnerable to the FREAK attack.
22. Not vulnerable to CVE-2015-4000 (Logjam): The server is using strong Diffie-Hellman parameters and is not vulnerable to the Logjam attack.
23. Server information header not exposed: Ensuring the server information header is not exposed reduces the ability of attackers to exploit certain vulnerabilities.
24. X-Powered-By header not exposed: Information about specific technology used on the server is obscured.
25. Strong Diffie-Hellman prime used in key exchange: TLS connections to the site use a strong Diffie-Hellman prime during key exchange.
26. Strong public certificate key length: The site's public certificate provides at least 112 bits of security strength.
27. Referrer Policy is not unsafe-url: The website's Referrer Policy is not configured to allow unsafe information to be sent in the referrer header.
28. ASP.NET version header not exposing specific ASP.net version: Ensuring the ASP.NET version header is not exposing a specific version makes it harder for attackers to exploit certain vulnerabilities.
29. ASP.NET version header not exposed: Ensuring the ASP.NET version header is not exposed makes it harder for attackers to exploit certain vulnerabilities.
30. No open cloud storage service detected: No cloud storage service configured to allow anonymous file listing was detected.
31. Domain index is not a listable directory: The domain index is not a listable directory.
32. No unmaintained page detected: The page appears to be maintained

## Email Security
34. DMARC policy not found: DMARC policy was not found. This makes it easier for attackers to send email from this domain. A DMARC policy should be deployed for this domain.
35. SPF policy uses ~all: Sender Policy Framework (SPF) record is too lenient as to which domains are allowed to send email on the domain's behalf. This record should preferably not use the ~all mechanism, as this does not instruct the mail receiver to reject messages from unauthorised sources. When DMARC is not being enforced, -all should be used on the SPF record.
36. No unregistered MX records detected: No unregistered MX records that could lead to receiving mail on behalf of the target organization were detected.
37. SPF enabled: Sender Policy Framework (SPF) records prevent spammers from sending messages with forged addresses.
38. SPF syntax correct: Sender Policy Framework (SPF) record passes basic syntax checks.
39. SPF ptr mechanism not used: Sender Policy Framework (SPF) record does not include the ptr mechanism.

## Brand Protection
41. Domain has not expired: Domain has not expired.
42. No subdomain takeover vulnerability detected: No dangling DNS records that could lead to subdomain takeover were detected.
43. Domain does not expire soon: Domain does not expire within 30 days.
44. Domain not flagged as inactive: Domain is not flagged as inactive.
45. Domain not pending deletion: Domain is not pending deletion with the registrar.
46. Domain not pending restoration: Domain is not pending restoration with the registrar.
47. Domain registrar or registry deletion protection enabled: Domain is protected from unsolicited deletion requests with the registrar or registry.
48. Domain registrar or registry transfer protection enabled: Domain is protected from unsolicited transfer requests.
49. Domain registrar or registry update protection enabled: Domain is protected from unsolicited update requests with the registrar or registry.
50. Domain free of registrar DNS resolution hold: Domain is not under a DNS resolution hold with the registrar.
51. Domain free of registry DNS resolution hold: Domain is not under a DNS resolution hold with the registry itself.
52. Domain renewal not prohibited by registry: Domain is not prohibited from renewal at the registry itself.

## Network Security
53. DNSSEC not enabled: DNSSEC records prevent third parties from forging the records that guarantee a domain's identity. DNSSEC should be configured for this domain.
54. No ports are open: No open ports were detected.

## Phishing & Malware
55. No reports of botnet activity in the last 30 days: This IP/domain has not been reported as a source of botnet activity in the last 30 days.
56. No reports of brute force login attempts in the last 30 days: This IP/domain did not appear on any list of IPs and domains known to perform brute force login attempts in the last 30 days.
57. No reports of malware distribution in the last 30 days: This IP/domain has been reported for distributing malware in the last 30 days.
58. No reports of unsolicited scanning in the last 30 days: This IP/domain has not been reported for performing unsolicited scanning in the last 30 days.
59. No reports of phishing activity in the last 30 days: This IP/domain has not been reported as a phishing site in the last 30 days.
60. No reports of botnet activity in the last 90 days: This IP/domain has not been reported as a source of botnet activity in the last 90 days.
61. No reports of brute force login attempts in the last 90 days: This IP/domain did not appear on any list of IPs and domains known to perform brute force login attempts in the last 90 days.
62. No reports of malware distribution in the last 90 days: This IP/domain has been reported for distributing malware in the last 90 days.
63. No reports of unsolicited scanning in the last 90 days: This IP/domain has not been reported for performing unsolicited scanning in the last 90 days.
64. No reports of phishing activity in the last 90 days: This IP/domain has not been reported as a phishing site in the last 90 days.