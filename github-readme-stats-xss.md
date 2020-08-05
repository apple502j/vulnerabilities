# github-readme-stats Cross-site Scripting
github-readme-stats shows error page when the username is not valid, which includes the username without neutralization, causing reflected cross-site scripting.

## CVSS score (3.1)
6.1(Medium) - CVSS:3.1/AV:N/AC:L/PR:N/UI:R/S:C/C:L/I:L/A:N

## Details
The page `/api` accepts `username` parameter. If the username is not valid, an error page is returned. The error page contains the username without neutralization. Attackers can use username with `<script>` tags to cause reflected cross-site scripting.

## Links
- https://github.com/anuraghazra/github-readme-stats/pull/255

## Weaknesses
- [Improper Neutralization of Script in an Error Message Web Page](https://cwe.mitre.org/data/definitions/81.html)
