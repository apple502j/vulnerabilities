# Scratch VM Script Injection
A vulnerability in .sb3 file deserialization process allows arbitrary scripts to be executed as a Web Worker. CVE ID assigned: CVE-2020-14000

## CVSS score (3.1)
5.0(Medium) - CVSS:3.1/AV:L/AC:L/PR:N/UI:R/S:C/C:L/I:L/A:N

## Details
The function `getExtensionIdForOpcode` returns extension ID which is just the first part of the opcode split by underscore, without any validation. The opcode in the untruested project.json can be a string which is formatted like `URL_foo`, where FOO is the URL of the script to be injected and foo is an arbitrary string.

The returned value for getExtensionIdForOpcode is passed to `loadExtensionURL`, which first checks if the extension is built-in, and if not, it loads the script from the given URL. The script is loaded inside a Web Worker context.

## Links
- https://github.com/LLK/scratch-vm/pull/2476

## Weaknesses
- [Deserialization of Untrusted Data](https://cwe.mitre.org/data/definitions/502.html)
- [Improper Neutralization of Value Delimiters](https://cwe.mitre.org/data/definitions/142.html)
