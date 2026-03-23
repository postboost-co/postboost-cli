# PostBoost Bash CLI

Official Bash CLI for the [PostBoost API](https://postboost.co/docs/api), auto-generated from the OpenAPI spec.

## Install

Download the latest release from GitHub:

```bash
# Download latest release
curl -LO https://github.com/postboost-co/postboost-cli/releases/latest/download/postboost-cli.tar.gz
tar xzf postboost-cli.tar.gz

# Or clone
git clone https://github.com/postboost-co/postboost-cli.git
```

| | |
|---|---|
| **Releases** | [github.com/postboost-co/postboost-cli/releases](https://github.com/postboost-co/postboost-cli/releases) |
| **GitHub** | [postboost-co/postboost-cli](https://github.com/postboost-co/postboost-cli) |
| **Docs** | [postboost.co/docs/api](https://postboost.co/docs/api) |
| **Version** | v1.2.0 |

## Quick start

```bash
export POSTBOOST_API_TOKEN="YOUR_API_TOKEN"

./postboost-cli listPosts --workspaceUuid "YOUR_WORKSPACE_UUID"
```

## License

MIT
