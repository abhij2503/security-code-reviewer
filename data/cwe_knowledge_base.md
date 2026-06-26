# CWE Security Vulnerability Reference

## CWE-89: SQL Injection
CWE-89 (Improper Neutralization of Special Elements used in an SQL Command), commonly known as SQL Injection, occurs when user-controllable input is incorporated into an SQL query without proper sanitization or parameterization. OWASP Category: A03 (Injection). An attacker can manipulate the query to read, modify, or delete database data, bypass authentication, or execute administrative operations. Mitigation: Use parameterized queries (prepared statements), use ORM frameworks, validate and sanitize all input, and apply least-privilege database accounts. Reference: https://cwe.mitre.org/data/definitions/89.html

## CWE-79: Cross-Site Scripting (XSS)
CWE-79 (Improper Neutralization of Input During Web Page Generation), known as Cross-Site Scripting or XSS, occurs when an application includes untrusted data in a web page without proper escaping, allowing attackers to inject client-side scripts into pages viewed by other users. OWASP Category: A03 (Injection). Consequences include session hijacking, credential theft, and defacement. Mitigation: Contextually output-encode all untrusted data, use Content Security Policy (CSP), sanitize HTML with vetted libraries, and set HttpOnly cookies. Reference: https://cwe.mitre.org/data/definitions/79.html

## CWE-787: Out-of-bounds Write
CWE-787 (Out-of-bounds Write) occurs when software writes data past the end, or before the beginning, of an intended buffer. OWASP Category: A03. This is frequently caused by functions like strcpy that copy without bounds checking. Consequences include memory corruption, crashes, and arbitrary code execution. Mitigation: Use bounded functions (strncpy, snprintf), validate buffer sizes before writing, ensure null termination, and enable compiler protections like stack canaries. Reference: https://cwe.mitre.org/data/definitions/787.html

## CWE-119: Improper Restriction of Operations within the Bounds of a Memory Buffer
CWE-119 is the parent class for buffer errors, where software performs operations on a memory buffer but reads from or writes to a location outside the buffer's intended boundary. OWASP Category: A03. It encompasses buffer overflows and over-reads. Mitigation: Use memory-safe languages or libraries, perform bounds checking, and use safe string-handling functions. Reference: https://cwe.mitre.org/data/definitions/119.html

## CWE-125: Out-of-bounds Read
CWE-125 (Out-of-bounds Read) occurs when software reads data past the end, or before the beginning, of the intended buffer. OWASP Category: A03. It can leak sensitive memory contents (as in Heartbleed) or cause crashes. Mitigation: Validate indices and lengths before reading, use safe APIs, and apply bounds checking. Reference: https://cwe.mitre.org/data/definitions/125.html

## CWE-20: Improper Input Validation
CWE-20 occurs when a product does not validate or incorrectly validates input that affects control flow or data handling. OWASP Category: A03. It is a root cause for many injection and memory-safety issues. Mitigation: Validate input against strict allowlists for type, length, format, and range; reject rather than sanitize where possible. Reference: https://cwe.mitre.org/data/definitions/20.html

## CWE-94: Code Injection
CWE-94 (Improper Control of Generation of Code) occurs when software constructs code from externally-influenced input without neutralizing special elements, allowing attackers to execute arbitrary code. OWASP Category: A03. Often seen with eval() on untrusted input. Mitigation: Avoid dynamic code execution, use safe sandboxing, and validate input strictly. Reference: https://cwe.mitre.org/data/definitions/94.html

## CWE-416: Use After Free
CWE-416 (Use After Free) occurs when a program continues to use a pointer after the memory it points to has been freed, leading to crashes, data corruption, or code execution. OWASP Category: A03. Mitigation: Set pointers to NULL after freeing, use smart pointers or memory-safe languages, and employ tools like AddressSanitizer. Reference: https://cwe.mitre.org/data/definitions/416.html

## CWE-476: NULL Pointer Dereference
CWE-476 occurs when an application dereferences a pointer it expects to be valid but is NULL, typically causing a crash or denial of service. OWASP Category: A03. Mitigation: Check pointers for NULL before use, and validate return values of allocation and lookup functions. Reference: https://cwe.mitre.org/data/definitions/476.html

## CWE-502: Deserialization of Untrusted Data
CWE-502 occurs when an application deserializes untrusted data without sufficient verification, allowing attackers to manipulate object state or execute code. OWASP Category: A08 (Software and Data Integrity Failures). Mitigation: Avoid deserializing untrusted data, use signed/encrypted serialization, and prefer simple data formats like JSON with schema validation. Reference: https://cwe.mitre.org/data/definitions/502.html

## CWE-190: Integer Overflow or Wraparound
CWE-190 occurs when an arithmetic operation produces a value too large for the integer type, wrapping around to an unexpected value. OWASP Category: A03. It can lead to undersized buffer allocation and subsequent overflows. Mitigation: Use safe arithmetic libraries, check for overflow before operations, and validate sizes. Reference: https://cwe.mitre.org/data/definitions/190.html

## CWE-200: Exposure of Sensitive Information
CWE-200 occurs when software exposes sensitive information to an actor not explicitly authorized to access it. OWASP Category: A01 (Broken Access Control). Mitigation: Minimize sensitive data in responses and logs, enforce access controls, and review error messages for leakage. Reference: https://cwe.mitre.org/data/definitions/200.html

## CWE-362: Race Condition
CWE-362 (Concurrent Execution using Shared Resource with Improper Synchronization) occurs when a system's behavior depends on the timing of concurrent operations on a shared resource. OWASP Category: A04. It can lead to TOCTOU bugs and data corruption. Mitigation: Use proper locking/synchronization primitives, atomic operations, and avoid shared mutable state. Reference: https://cwe.mitre.org/data/definitions/362.html

## CWE-264: Permissions, Privileges, and Access Controls
CWE-264 covers weaknesses related to improper management of permissions, privileges, and other security features. OWASP Category: A01. Mitigation: Apply least privilege, enforce strong access controls, and validate authorization on every sensitive operation. Reference: https://cwe.mitre.org/data/definitions/264.html

## CWE-399: Resource Management Errors
CWE-399 covers weaknesses related to improper management of system resources such as memory, file handles, and connections, often leading to resource exhaustion or leaks. OWASP Category: A04. Mitigation: Release resources reliably (RAII, try-with-resources), set limits, and monitor usage. Reference: https://cwe.mitre.org/data/definitions/399.html
