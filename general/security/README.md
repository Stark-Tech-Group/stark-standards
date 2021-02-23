| Code   | Description                                                                                |
|--------|--------------------------------------------------------------------------------------------|
| sec-1  | Do not allow cross-site scripting (XSS) vulnerabilities                                    |
| sec-2  | Do not allow cross-site request forgery (CSRF) vulnerabilities                             |
| sec-3  | Do not allow sql injection vulnerabilities, favor prepared statements and named variables  |
| sec-4  | Do not commit secrets to source control                                                    |
| sec-5  | Use a secrets manager                                                                      |
| sec-6  | Do not log secrets                                                                         |
| sec-7  | Treat Personal Identifiable Information (PII) as secrets                                   |
| sec-8  | Always assume inputs will be malicious                                                     |
| sec-9  | Always assume file uploads will be malicious in content, size and type                     |
| sec-10 | Do not include secrets in error or exception messages                                      |
| sec-11 | Use well known encryption tools. Don't create your own encryption algorithm                |
| sec-12 | Avoid keeping secrets in memory longer than needed                                         |
| sec-13 | Favor char arrays over strings for when storying secrets in memory                         |
| sec-14 | Protect against arithmetic overflow and underflow                                          |
| sec-15 | Limit the count and size a log file can grow to                                            |
| sec-16 | Configure XML parsers to prevent XXE                                                       |
| sec-17 | Never store secrets or PII in plain text                                                   |
| sec-18 | Limit serialization interfaces and protect against unsafe de-serialization vulnerabilities |
| sec-19 | HTTPS only                                                                                 |
| sec-20 | Assume supply chains and vendors are compromised                                           |
| sec-21 | Assume parsers are vulnerabilities (HTML, CSV, XML, JSON, REGEX, etc.)                     |
| sec-22 | Limit the number of chained exceptions                                                     |
| sec-23 | Log failed access and authentication attempts                                              |
| sec-24 | Favor deny all                                                                             |
| sec-25 | Document trusted IP address in net-sec repository                                          |
| sec-26 | Document malicious IP addresses in net-sec repository                                      |
| sec-27 | Limit number of failed access and authentication attempts                                  |
| sec-28 | Use de-bouncing techniques                                                                 |
| sec-29 | Do not store secrets in containers                                                         |
