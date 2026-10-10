# Puntjes OpenAPI

The OpenAPI 3.1 document of the [Puntjes](https://puntjes.app) public API v1, one tagged version per release.

| File | What it holds |
|---|---|
| `api.json` | The OpenAPI document at this version |
| `CHANGELOG.md` | What changed in each version, written by [oasdiff](https://github.com/oasdiff/oasdiff) |

A version appears here after the Puntjes release that puts it live. Nobody edits this repository by
hand: `puntjes-sdk-bot` writes every commit and tag.

## Versions

Each version is a tag, such as `v1.2.0`. The number says what the change does to a client:

| The change | The version |
|---|---|
| Breaks an existing client: a removed endpoint, a removed field every response carries, a new required input | Major (`2.0.0`) |
| Any other change to the API: a new endpoint, a field, a deprecation | Minor (`1.3.0`) |
| Only a description or an example changes | Patch (`1.2.1`) |

To generate a client, read `api.json` at a tag, not at `main`:
`https://raw.githubusercontent.com/PuntjesApp/puntjes-openapi/v1.2.0/api.json`.

## SDKs

| Package | Repository |
|---|---|
| `puntjes/php-sdk` | [PuntjesApp/puntjes-php-sdk](https://github.com/PuntjesApp/puntjes-php-sdk) |
| `puntjes/laravel` | [PuntjesApp/puntjes-laravel](https://github.com/PuntjesApp/puntjes-laravel) |

Each new version sends a `spec-published` `repository_dispatch` to every SDK repository, with
`client_payload: { tag, level, url }`. `level` is `major`, `minor` or `patch`, and `url` is the raw
`api.json` at the tag.

The guides are at [docs.puntjes.app](https://docs.puntjes.app/docs/sdks).
