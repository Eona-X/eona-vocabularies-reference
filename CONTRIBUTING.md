# Contributing

Thanks for considering a contribution to the Eona-X vocabulary sources. This
repository holds the reference Turtle for the ontologies/vocabularies the
[Eona Vocabulary Hub](https://github.com/Eona-X/eona-vocabulary-services)
publishes, plus the metadata describing each one.

## What lives here

One directory per ontology, named by its slug:

```
<slug>/
├── ontology.ttl          # the vocabulary itself — owl:versionInfo is its version of record
├── catalog-fragment.ttl  # optional: additional catalog/display metadata
├── metadata.toml         # title, description, upstream attribution
└── TERMS.md              # optional: field-by-field documentation
```

`metadata.toml`:

```toml
title = "Example Vocabulary"
description = "One-line description shown in the catalog."

# Optional — omit entirely for an Eona-X original with no external upstream.
[upstream]
name = "Standards Body Name"
logo = "logo-filename.png"
```

## Kinds of contribution

- **Fix an error** in an existing ontology (a wrong domain/range, a missing
  label, a broken `owl:versionInfo`) — open a PR against the relevant
  `<slug>/ontology.ttl`.
- **Update to a newer upstream release** — bump the bundled Turtle and
  `owl:versionInfo` together, and note the upstream version in your PR
  description.
- **Add a new vocabulary** — open an issue first describing what it is and
  why it belongs here; once agreed, add a new `<slug>/` directory following
  the layout above.
- **Improve metadata** — a better description, a missing upstream logo, a
  `TERMS.md` write-up.

## Guidelines

- Keep each ontology's Turtle **self-contained**: no `owl:imports` of
  something not itself vendored here or resolvable without network access at
  build time (downstream builds are offline by design).
- Validate your Turtle parses before opening a PR (any RDF library will do,
  e.g. `python3 -c "import rdflib; rdflib.Graph().parse('slug/ontology.ttl')"`
  or `riot --validate slug/ontology.ttl` from Apache Jena).
- One logical change per PR — a metadata fix and an ontology content change
  are easier to review separately.
- By contributing, you agree your contribution is licensed under this
  repository's [Apache 2.0 license](./LICENSE). If you're contributing an
  upstream standard's own Turtle, make sure its license permits
  redistribution here and note that in `metadata.toml`/`TERMS.md`.

## Questions

Open an issue — for a question about a specific vocabulary, tag it with the
ontology's slug.
