# nvd-nist-scrapper

```
$ ./nvds --keyword CMS -t 2
[05:10:16] output: nvd_dump_out.json
[05:10:16] cache dir: /tmp/nvd-dump
[05:10:16] search times: 2
[05:10:16] fetching data: range=2026-06-13T00:00:00.000-2026-10-11T00:00:00.000 | keyword='CMS' | cache_file=/tmp/nvd-dump/nvd_dump_CMS.1.json
[05:10:29] fetching data: range=2026-02-13T00:00:00.000-2026-06-13T00:00:00.000 | keyword='CMS' | cache_file=/tmp/nvd-dump/nvd_dump_CMS.2.json
[05:10:41] files: /tmp/nvd-dump/nvd_dump_CMS.1.json /tmp/nvd-dump/nvd_dump_CMS.2.json
[05:10:41] /tmp/nvd-dump/nvd_dump_CMS.1.json -> size: 1.3M
[05:10:41] /tmp/nvd-dump/nvd_dump_CMS.1.json -> totalResults: 378
[05:10:41] /tmp/nvd-dump/nvd_dump_CMS.2.json -> size: 1.4M
[05:10:41] /tmp/nvd-dump/nvd_dump_CMS.2.json -> totalResults: 361
[05:10:41] nvd_dump_out.json -> size: 4.4M
[05:10:41] nvd_dump_out.json -> totalResults: 739
[05:10:41] done.
$ jq -r '.vulnerabilities[0].cve.id' nvd_dump_out.json
CVE-2026-12202
$ jq '.vulnerabilities[0].cve | [.id, .descriptions[0].value]' nvd_dump_out.json
[
  "CVE-2026-12202",
  "A vulnerability has been found in Intelliants Subrion CMS up to 4.0.3. [...]"
]
```
