# Applications

The inventory below follows the application directories enumerated by the committed `apps/kustomization.yaml`. Descriptions identify intended purpose from the workload name and manifest layout; they are not uptime or deployment claims. Each entry links to its manifest directory. The current list contains 34 application entries. `apps/netbox/` is tracked but is not currently listed by `apps/kustomization.yaml`; it is called out separately below. `apps/base/` contains shared resources rather than a listed application.

## Home, media, and personal data

| Application | Purpose | Manifests |
| --- | --- | --- |
| Audiobookshelf | Audiobook and spoken-media library | [`apps/audiobookshelf/`](../apps/audiobookshelf/) |
| Frigate | Camera and video monitoring workload | [`apps/frigate/`](../apps/frigate/) |
| Home Assistant | Home automation platform | [`apps/home-assistant/`](../apps/home-assistant/) |
| Immich | Photo and video management | [`apps/immich/`](../apps/immich/) |
| Jellyfin | Media streaming server | [`apps/jellyfin/`](../apps/jellyfin/) |
| Navidrome | Music streaming server | [`apps/navidrome/`](../apps/navidrome/) |
| OpenCloud | Self-hosted file and collaboration service | [`apps/opencloud/`](../apps/opencloud/) |
| Paperless | Document management and archiving | [`apps/paperless/`](../apps/paperless/) |

## Productivity and automation

| Application | Purpose | Manifests |
| --- | --- | --- |
| Actual Budget | Personal finance application | [`apps/actual-budget/`](../apps/actual-budget/) |
| Affine | Collaborative workspace and knowledge management | [`apps/affine/`](../apps/affine/) |
| Linkwarden | Bookmark and link archiving | [`apps/linkwarden/`](../apps/linkwarden/) |
| n8n | Workflow automation | [`apps/n8n/`](../apps/n8n/) |
| NetBox | Network and infrastructure inventory; tracked but not currently listed in the apps composition | [`apps/netbox/`](../apps/netbox/) |
| PDF | PDF utility service | [`apps/pdf/`](../apps/pdf/) |

## Network, security, and operations

| Application | Purpose | Manifests |
| --- | --- | --- |
| AdGuard | DNS filtering service | [`apps/adguard/`](../apps/adguard/) |
| AdGuard Home Sync | Synchronization helper for AdGuard instances | [`apps/adguardhome-sync/`](../apps/adguardhome-sync/) |
| NetAlertX | Network device discovery and alerting | [`apps/netalertx/`](../apps/netalertx/) |
| Patchmon | Patch and update monitoring | [`apps/patchmon/`](../apps/patchmon/) |
| Uptime Kuma | Endpoint and service monitoring | [`apps/uptime-kuma/`](../apps/uptime-kuma/) |
| UniFi | Network management endpoint | [`apps/unifi/`](../apps/unifi/) |
| Vaultwarden | Password-manager-compatible service | [`apps/vaultwarden/`](../apps/vaultwarden/) |

## Developer, media, and utility services

| Application | Purpose | Manifests |
| --- | --- | --- |
| Arcane | Service management UI | [`apps/arcane/`](../apps/arcane/) |
| Explo | Music-oriented application delivered by Helm | [`apps/explo/`](../apps/explo/) |
| Glance | Dashboard and homepage | [`apps/glance/`](../apps/glance/) |
| Hermes | Utility service | [`apps/hermes/`](../apps/hermes/) |
| Homepage | Kubernetes application dashboard (gethomepage) | [`apps/homepage/`](../apps/homepage/) |
| ITTools | Developer and IT utilities | [`apps/ittools/`](../apps/ittools/) |
| IPTV EPG | Electronic program guide service | [`apps/iptv-epg/`](../apps/iptv-epg/) |
| Kutt | URL-shortening service | [`apps/kutt/`](../apps/kutt/) |
| Nexterm | Server management web terminal (SSH, VNC, RDP) with OIDC SSO; see `OIDC.md` in its directory for provider setup | [`apps/nextterm/`](../apps/nextterm/) |
| oMLX | Apple Silicon LLM inference server (MLX) exposed as an external endpoint | [`apps/omlx/`](../apps/omlx/) |
| OpenSpeed | Network speed-test service | [`apps/openspeed/`](../apps/openspeed/) |
| PBS | Backup-server endpoint integration | [`apps/pbs/`](../apps/pbs/) |
| pgAdmin | PostgreSQL administration UI | [`apps/pgAdmin/`](../apps/pgAdmin/) |
| Zot | OCI/container registry delivered by Helm | [`apps/zot/`](../apps/zot/) |

## Tracked but not currently composed

- [`apps/netbox/`](../apps/netbox/) contains a workload directory, but the current `apps/kustomization.yaml` does not include it.
- [`apps/base/`](../apps/base/) contains shared namespace, middleware, and secret resources rather than a standalone application entry.

## Reading an application directory

A workload directory commonly contains some combination of:

- `kustomization.yaml` for local composition.
- A Deployment or a HelmRelease.
- A Service and, where applicable, an `HTTPRoute`.
- PVC/PV resources for state.
- ConfigMaps and encrypted Secret manifests.

Before changing a workload, read its local Kustomization and check whether it is included by `apps/kustomization.yaml`. Do not assume a directory, a Service, or an HTTPRoute is currently live.
