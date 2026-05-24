# DNS records for abrutin.ru on GitHub Pages

Configure these records at the DNS provider for `abrutin.ru`.

```text
A      @      185.199.108.153
A      @      185.199.109.153
A      @      185.199.110.153
A      @      185.199.111.153
CNAME  www    iabrutin.github.io
```

Optional IPv6 records:

```text
AAAA   @      2606:50c0:8000::153
AAAA   @      2606:50c0:8001::153
AAAA   @      2606:50c0:8002::153
AAAA   @      2606:50c0:8003::153
```

In the GitHub repository, open `Settings -> Pages`, set the source to
`GitHub Actions`, and set the custom domain to `abrutin.ru`. Enable
`Enforce HTTPS` after GitHub finishes issuing the certificate.

Verify after DNS propagation:

```bash
dig abrutin.ru +noall +answer -t A
dig www.abrutin.ru +noall +answer
```

