# o9 Solutions

o9 Solutions is an enterprise AI platform for integrated planning and decision-making, founded in 2009 by Sanjiv Sidhu (previously founder of i2 Technologies) and Chakri Gottemukkala, and headquartered in Dallas, Texas. Its o9 Digital Brain platform unifies supply chain, commercial and financial planning on a patented Enterprise Knowledge Graph (EKG).

- Website — https://o9solutions.com
- Developer / API guide — https://guide.o9solutions.com/
- Documentation portal — https://documents.o9solutions.com/
- Security & compliance — https://o9solutions.com/security
- Vulnerability disclosure policy — https://o9solutions.com/security/vulnerability-disclosure-policy
- Forge Global profile — https://forgeglobal.com/o9-solutions_stock/

## API surface

o9 publishes two API references, both **gated** behind the o9 customer/partner OAuth login:

| API | Reference | Access |
|---|---|---|
| o9 Platform API | https://guide.o9solutions.com/Resources/ApiDocs | OAuth-gated |
| o9 Reference Model API (SAP + inbound staging) | https://guide.o9solutions.com/Resources/RefModelApiDoc | OAuth-gated |

Base URLs are tenant-scoped per-customer o9 platform hosts; no public non-tenant base URL is
advertised, so none is recorded here rather than fabricated.

## Contract discovery (2026-07-31)

No public machine-readable contract exists. Probed on `o9solutions.com`, `www.o9solutions.com`,
`guide.o9solutions.com`, `documents.o9solutions.com` and `api.o9solutions.com` (does not resolve):

- **OpenAPI/Swagger** — `/openapi.json`, `/openapi.yaml`, `/swagger.json`, `/swagger/v1/swagger.json`,
  `/api-docs`, `/docs`, `/redoc`: all 403 (marketing WAF), 404, or a JS docs shell. No spec.
- **GraphQL** — no `/graphql` surface on any host.
- **MCP** — no hosted server advertised in the docs, `llms.txt`, or the MCP registries.
- **A2A Agent Card** — `/.well-known/agent-card.json` and `/.well-known/agent.json` miss everywhere
  (403 or 404, never an `AgentCard` JSON object). Nothing written, per the search-only rule.
- **`/.well-known/*`** — no discovery document served on any host; the OAuth server publishes no
  `openid-configuration` or `oauth-authorization-server` metadata.

What **is** public: a real, well-formed `llms.txt` (saved verbatim), an
[AI/LLM fact page](https://o9solutions.com/ai-info), a named security-compliance page, and a
responsible-disclosure policy.

## Artifacts

| Dir | File | Method |
|---|---|---|
| `llms/` | `o9-solutions-llms.txt` | searched (verbatim from https://o9solutions.com/llms.txt) |
| `authentication/` | `o9-solutions-authentication.yml` | probed (live OAuth authorize requests) |
| `scopes/` | `o9-solutions-scopes.yml` | probed (`openid email profile` observed) |
| `security/` | `o9-solutions-domain-security.yml` | probed (TLS/HSTS/DNSSEC/SPF/DMARC) |
| `security/` | `o9-solutions-vulnerability-disclosure.yml` | searched |
| `security/` | `o9-solutions-trust-center.yml` | searched |
| `conformance/` | `o9-solutions-conformance.yml` | searched |
| `lifecycle/` | `o9-solutions-lifecycle.yml` | probed |
| `well-known/` | `o9-solutions-well-known.yml` | probed (negative record) |

Not applicable / nothing published: `openapi/`, `asyncapi/`, `mcp/`, `a2a/`, `skills/`, `packages/`,
`cli/`, `sandbox/`, `changelog/`, `components/`, `overlays/`, `errors/`, `data-model/`, `grpc/`.
No GitHub organization, no npm/PyPI packages, no public status page (`o9.statuspage.io` is inactive).
