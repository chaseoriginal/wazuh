# wazuh

Single-node Wazuh deployment (indexer + manager + dashboard) for
ore-dock-104-2.

Adapted from https://github.com/wazuh/wazuh-docker/tree/v4.14.6/single-node

## Notes

Every volume is pinned by its exact live name (`name:` under each logical
volume). Without that, a redeploy would resolve to fresh empty volumes and
the indexer data, wazuh config and manager state would silently reset.

## Secrets

The three passwords live in `.env` (git-ignored). `.env.example` shows the
required keys. Portainer reads the values from the stack environment.
