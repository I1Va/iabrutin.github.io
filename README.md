# abrutin.ru

Personal website for `abrutin.ru`, built with [Zola](https://www.getzola.org/)
and the [Particle Zola theme](https://www.getzola.org/themes/particle/).

## Local preview

Install Zola 0.22.x, then run:

```bash
zola serve
```

The generated output goes to `public/`, which is intentionally ignored because
GitHub Pages builds the site from source using GitHub Actions.

The custom domain is also committed as [`static/CNAME`](static/CNAME) so every
deployment publishes the Pages domain binding in the generated artifact.

## Publish on GitHub Pages

1. Create a GitHub repository and push this project to its `main` branch.
2. Open the repository settings.
3. Go to `Settings -> Pages`.
4. Set `Build and deployment -> Source` to `GitHub Actions`.
5. Set the custom domain to `abrutin.ru`.
6. Enable `Enforce HTTPS` after GitHub finishes issuing the certificate.

DNS records are documented in [DNS.md](DNS.md).
