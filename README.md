# nvd-nist-scrapper

```
$ ./nvds --keyword CMS -t 2
[00:00:00] output: nvd_dump_out.json
[00:00:00] cache dir: /tmp/nvd-scrapper
[00:00:00] search times: 2
[00:00:00] search range: 2025-11-28T00:00:00.000 - 2026-03-28T00:00:00.000
[00:00:00] search range: 2025-07-31T00:00:00.000 - 2025-11-28T00:00:00.000
[00:00:00] files: /tmp/nvd-scrapper/nvd_dump_1.json /tmp/nvd-scrapper/nvd_dump_2.json
[00:00:00] /tmp/nvd-scrapper/nvd_dump_1.json -> size: 928K
[00:00:00] /tmp/nvd-scrapper/nvd_dump_1.json -> totalResults: 253
[00:00:00] /tmp/nvd-scrapper/nvd_dump_2.json -> size: 308K
[00:00:00] /tmp/nvd-scrapper/nvd_dump_2.json -> totalResults: 111
[00:00:00] nvd_dump_out.json -> size: 1.9M
[00:00:00] nvd_dump_out.json -> totalResults: 364
[00:00:00] done.
$ jq .vulnerabilities[0].cve.id nvd_dump_out.json
"CVE-2025-66297"
$ jq '.vulnerabilities[0].cve | [.id, .descriptions[].value]' nvd_dump_out.json
[
  "CVE-2025-66297",
  "[...] a user with admin panel access and permissions to create or edit pages in Grav CMS [...]"
]
```
