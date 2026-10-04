# Gulshan-e-Noor Maintenance: owner control file

The software reads `status.json` when the computer has internet: at start-up, every 15
minutes, and as soon as the internet comes back. Between those times it works offline.

Edit on github.com (phone or computer): open `status.json`, tap the pencil, change it,
tap **Commit changes**. Changes reach the computer within about 15 minutes of it being online.

## Approve a new installation

A new installation shows an **Installation code** (like `UKQH-B9VS-VWCP`) and cannot be
used until its code is in the `licenses` list. When someone sends you a code, add a line:

```json
{
  "status": "active",
  "message": "",
  "licenses": {
    "UKQH-B9VS-VWCP": "active"
  }
}
```

Each further installation is one more line (put a comma after the previous line):

```json
    "UKQH-B9VS-VWCP": "active",
    "7PQ2-9XKM-3TRB": "active"
```

A note to remember which is which is optional:
`"UKQH-B9VS-VWCP": { "status": "active", "label": "Gulshan-e-Noor office PC" }`

## Block one installation

Change its `"active"` to `"disabled"`. Only that computer locks.

## Lock or unlock everyone

Top line: `"status": "disabled"` locks every installation; `"status": "active"` unlocks.
Optional message shown on the lock screen: `"message": "Please contact Aamir."`

## Turn approval off

Delete the whole `"licenses": { ... }` part. Then every copy works without approval
(the lock/unlock line still applies).

## Notes

- Nothing is ever deleted on the computer. Locking only stops use until unlocked.
- If the file has a typo, approved computers keep working as before; only new
  installations wait.
- A copy moved to a different computer gets a new code and needs approval again.
