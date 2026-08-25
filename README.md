# Eona-X Vocabularies (reference sources)

Reference Turtle and metadata for the ontologies/vocabularies published by
the [Eona Vocabulary Hub](https://github.com/Eona-X/eona-vocabulary-services)
— vendored here as its own independently-versioned, publicly contributable
repository (see that project's
[ADR-006](https://github.com/Eona-X/eona-vocabulary-services/blob/main/docs/adr/006-ontology-source-repository.md)
for why). Consumed there as a git submodule at `pipelines/vocabularies/`.

## Layout

One directory per ontology, named by its slug — see
[CONTRIBUTING.md](./CONTRIBUTING.md) for the full shape of each and how to
propose a change.

## License

[Apache License 2.0](./LICENSE). Some vocabularies here are bundled copies
of external standards published under their own license — see the
`metadata.toml`/`TERMS.md` in that vocabulary's own directory for details.
