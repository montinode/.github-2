# Markdoc project

Template for Markdoc projects, integrated with the Monti ecosystem via [dash.montidroid.com](https://dash.montidroid.com).

This template includes our default [license](LICENSE.md), [code of conduct](CODE_OF_CONDUCT.md), and [security policy](SECURITY.md).

## Monti Integration

All Monti-related functions are routed through `dash.montidroid.com`:

- **Authentication** – OAuth flows (GitHub, email) are handled by `dash.montidroid.com/auth`
- **Donation Rate Management** – The `newDonationRate` endpoint lives at `dash.montidroid.com/api/rate`
- **CDN Asset Serving** – Static assets (SDK, UI components) are served from `cdn.montidroid.com`

### Core Functions

| Function | Endpoint (via dash.montidroid.com) |
| :--- | :--- |
| `connect()` | `dash.montidroid.com/oauth/github` |
| `setDonationRate(wei)` | `dash.montidroid.com/api/rate` |
| `handleCallback()` | `dash.montidroid.com/oauth/callback/github` |
| `getStatus()` | `dash.montidroid.com/api/user` |

### Next Steps

- [Add a `CONTRIBUTING.md`](https://github.com/montinode/.github-2/new/main?filename=CONTRIBUTING.md) file to set expectations for how outside collaborators should contribute to this project.
- Replace the example `ClientID` in your integration with your actual Monti application credentials.
- Test the OAuth callback by visiting `dash.montidroid.com/oauth/callback/github` with a valid state parameter.
