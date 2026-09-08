---
title: International Travel Edition Guide
description: The International Travel Edition firmware is retired; what to do with a device running it
slug: ite
last_updated: September, 7, 2026
keywords: OnlyKey, International Travel Edition, Plausible Deniability
---

## The International Travel Edition is retired

The International Travel Edition was a separate OnlyKey firmware build that did not use encryption, intended for countries where encryption is banned or restricted. It was a fully functional password manager without PGP, SSH, backup encryption, or the second (encrypted) profile.

As of firmware 3.1.0 there is one OnlyKey firmware edition, and every profile is encrypted under its PIN. The Travel Edition build is no longer produced, and the standard firmware no longer contains the non-encrypted mode it relied on.

## If your OnlyKey is running the International Travel Edition

Your device keeps working as it is; nothing changes until you load new firmware. When you are ready to move to the standard firmware:

1. Take a backup of your slots with the [OnlyKey App](/app) (backups made on the Travel Edition are not encrypted - treat the file accordingly).
2. Load the standard firmware following the [firmware loading guide](/firmware).
3. Set the device up again with the App (PINs, backup passphrase) and restore your backup.

There is no in-place upgrade path from the Travel Edition, because the device has no encryption keys to migrate.

## Related

- [Plausible Deniability Setup Guide](/pdguide) - the plausible deniability second profile, which used the same non-encrypted mode, is retired at the same time and is migrated automatically.
