# kenny2automate Path Traversal
Improper handling of locale names in kenny2automate resulted in path traversal, allowing arbitrary JSON files to be read.

## CVSS score (3.1)
5.3(Medium) - CVSS:3.1/AV:N/AC:L/PR:N/UI:N/S:U/C:L/I:N/A:N

## Details
The `lang` command passed lang parameter given by the attacker to `os.path.join` without validation, which allows saving settings with locale name which resolves to relative path pointing to non-locale file. The setting is later used to read the locale file, which allows the attacker to read arbitrary JSON files stored in the computer.

## Links
- https://github.com/Kenny2github/kenny2automate/commit/99ac3dbcb50a056eb716889eb78038cdd06ed503

## Weaknesses
- [Relative Path Traversal](https://cwe.mitre.org/data/definitions/23.html)
