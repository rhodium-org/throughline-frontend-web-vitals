# throughline-frontend-web-vitals

Google's **Web Vitals** performance guidance (web.dev Core Web Vitals) expressed as a
[throughline](https://pypi.org/project/throughline/) **source** — a standalone,
grounded requirements graph that a consuming project composes with
[throughline-compose](https://github.com/rhodium-org/throughline-compose).

This repository holds no code. It is a directory of small YAML items with permanent
UIDs, validated by `tl check`. Consumers import it under a namespace and reference
its rules as `webvitals:SR-0001`.

## One of three alternative frontend sources

This is a **concern** source about **runtime frontend performance**. It is one of
**three alternative frontend sources**, alongside:

- `throughline-frontend-mdn` — the MDN web guidance, and
- `throughline-frontend` — the general frontend concern source.

A project typically **picks the one matching its priority** — choose
`throughline-frontend-web-vitals` when the driving concern is runtime performance and
Core Web Vitals. The three *can* be composed together, but they are offered as
**choices** rather than a stack, so a project is not forced to reconcile three
overlapping frontend framings at once.

## Status

<!-- tl:count type == 'user_requirement' -->
8
<!-- tl:end --> sections and
<!-- tl:count type == 'system_requirement' -->
54
<!-- tl:end --> performance rules, published to [`docs/spec.md`](docs/spec.md):

- `INT-0001` — the root intent (why the guidance exists), `normative: false`.
- Each Core Web Vital and optimisation area as a `user_requirement` that
  `derives_from` the intent.
- Every individual recommendation as a `system_requirement` that `implements` its
  section, carrying the guide reference in `attrs.source_ref`.

The counts above are rendered from the live graph by the `tl:count` directive, so
they cannot drift.

## Editions — dated tags

The guidance is a living document. A material revision is cut as a dated tag on this
repo (e.g. `v2026-08`); a consumer pins the ref it wants.

## Composing it

```toml
[[sources]]
namespace = "webvitals"
url = "https://github.com/rhodium-org/throughline-frontend-web-vitals"
ref = "v2026-08"
```

Then reference a rule from your own items:

```yaml
links:
- target: webvitals:SR-0006      # Google Web Vitals: preload the LCP resource
  type: satisfies
```

`tl-compose check` resolves the reference; bare `tl check` fails fast and points you
at `tl-compose`.

## Local checks

```sh
pip install throughline
tl check --strict     # the graph must stay sound
tl docs --check       # docs/spec.md must match the graph
```

## Provenance

Google's Web Vitals / web.dev content is © Google, licensed CC BY 4.0 (code samples
Apache 2.0). See [NOTICE](NOTICE) and https://web.dev/articles/vitals. This repository
is Apache-2.0 for its structure and tooling; the reproduced rule text remains Google's.
