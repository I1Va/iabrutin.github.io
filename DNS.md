# DNS records for abrutin.ru on GitHub Pages

Current authoritative nameservers:

```text
ns1.hosting.reg.ru
ns2.hosting.reg.ru
```

Make these changes in the REG.RU DNS panel for `abrutin.ru`.

Remove the existing REG.RU hosting records:

```text
A      @      31.31.196.17
AAAA   @      2a00:f940:2:2:1:1:0:256
A      www    31.31.196.17
```

Add these GitHub Pages records:

```text
A      @      185.199.108.153
A      @      185.199.109.153
A      @      185.199.110.153
A      @      185.199.111.153
CNAME  www    iabrutin.github.io.
```

Optional IPv6 records:

```text
AAAA   @      2606:50c0:8000::153
AAAA   @      2606:50c0:8001::153
AAAA   @      2606:50c0:8002::153
AAAA   @      2606:50c0:8003::153
```

In the GitHub repository, open `Settings -> Pages`, set the source to
`GitHub Actions`, and set the custom domain to `abrutin.ru`. If GitHub still
shows `NotServedByPagesError` after DNS propagates, remove the custom domain,
save, wait a few minutes, and add `abrutin.ru` again. Enable `Enforce HTTPS`
after GitHub finishes issuing the certificate.

Verify after DNS propagation:

```bash
dig abrutin.ru +noall +answer -t A
dig abrutin.ru +noall +answer -t AAAA
dig www.abrutin.ru +noall +answer
```

Expected result:

```text
abrutin.ru.      A      185.199.108.153
abrutin.ru.      A      185.199.109.153
abrutin.ru.      A      185.199.110.153
abrutin.ru.      A      185.199.111.153
www.abrutin.ru.  CNAME  iabrutin.github.io.
```

The current TTL is about 3600 seconds, so allow roughly 1 hour for DNS caches
to settle after changing the records.
