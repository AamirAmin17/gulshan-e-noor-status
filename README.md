# Gulshan-e-Noor Maintenance: on/off switch

The maintenance software reads `status.json` whenever the society computer has internet
(at start-up, every 15 minutes, and when the window is used).

## Lock the software (from your phone or home)

1. Open `status.json` in this repository and tap the pencil (Edit).
2. Change `"active"` to `"disabled"`. Optionally write a message, for example:
   `{"status":"disabled","message":"Please contact Aamir."}`
3. Tap **Commit changes**.

The society computer locks the next time it is online (normally within 15 minutes).
It stays locked even if the internet is then disconnected. No data is deleted.

## Unlock

Edit `status.json` back to `{"status":"active","message":""}` and commit.
The computer unlocks the next time it is online.

## Notes

- Only the word `active` or `disabled` matters. If the file is missing or unreadable,
  the software keeps its last state, so a typo here never breaks daily work.
- Raw link used by the software:
  `https://raw.githubusercontent.com/AamirAmin17/gulshan-e-noor-status/main/status.json`
