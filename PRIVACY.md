# Privacy Policy

This application ("the App") is a self-hosted, single-user Model Context Protocol (MCP) server that connects the operator's own WHOOP account to their own AI assistants (such as Claude or Poke).

## Who operates this instance

This privacy policy applies to the deployment operated by the repository owner for their personal use only. The App is not offered as a service to third parties.

## What data the App accesses

When the operator authorizes the App with their WHOOP account, it accesses only the scopes granted during OAuth:

- Profile (`read:profile`)
- Body measurements (`read:body_measurement`)
- Physiological cycles (`read:cycles`)
- Recovery (`read:recovery`)
- Sleep (`read:sleep`)
- Workouts (`read:workout`)

The App does not access any other WHOOP data, and does not access data from any account other than the account that authorized it.

## How data is stored

- WHOOP API data (cycles, sleep, recovery, workouts) is cached in a local SQLite database on the server the operator controls.
- OAuth access and refresh tokens are encrypted at rest with AES-256-GCM using a key derived from a secret known only to the server operator.
- The database file lives on the operator's infrastructure (e.g., a Railway persistent volume) and is not transmitted anywhere else.

## How data is used

Data retrieved from WHOOP is returned only to MCP clients that present a valid bearer token configured by the operator. It is not shared with third parties, not used for analytics, and not used for any purpose other than answering requests from the operator's own AI assistants.

## Data retention and deletion

The operator can delete all stored data at any time by deleting the SQLite database file. Revoking WHOOP access via WHOOP's user settings will also invalidate the stored tokens.

## Contact

For questions about this specific deployment, contact the repository owner through GitHub.
