---
title: Plausible Deniability Setup Guide
description: The plausible deniability second profile is retired; how existing profiles are migrated
slug: pdguide
last_updated: September, 7, 2026
keywords: OnlyKey, International Travel Edition, Plausible Deniability
---

## Plausible deniability is retired

The plausible deniability option for the second profile stored that profile's slots without encryption so that the device could be presented as having only one profile. As of firmware 3.1.0 it can no longer be selected: the OnlyKey App setup no longer offers it, and `onlykey-cli 2ndprofilemode 2` is refused with `Error plausible deniability profile is no longer supported`. Both profiles are encrypted under their PINs.

Reasons for retiring it: profile 2's usernames, passwords and URLs were stored in the clear on the device; the "no second profile" story does not hold against an adversary who can image the chip; and every profile-aware feature had to be tested twice. Users who need to travel without secrets on the device should take an [encrypted backup](/usersguide#backup-key-mode), wipe the device with the self-destruct PIN, and restore afterwards.

## If your OnlyKey already has a plausible deniability second profile

When you load firmware 3.1.0 or later, the device converts the profile the first time you unlock **profile 1**:

1. Load the new firmware and enter your **primary** PIN once. The conversion runs during that unlock: profile 2's slot data is encrypted, its TOTP and challenge-response keys are re-keyed, and the second profile becomes a standard second profile. On a debug build the serial console prints `Migrating plausible-deniability profile 2 to a standard profile` and `Profile 2 migration complete`.
2. From then on your second PIN unlocks profile 2 exactly as before, with the same slot contents.

Until that first primary-PIN unlock, the second PIN will **not** unlock profile 2 on the new firmware. If you cannot unlock profile 1, load the previous firmware, and everything is as it was.

If you never set a second PIN, nothing is converted and the device works as a one-profile device.

Support for reading unconverted plausible deniability profiles will be removed in the release after 3.1.0. Devices that skip 3.1.0 must install it (and unlock profile 1 once) before going further.

## Related

- [International Travel Edition Guide](/ite) - the separate non-encrypted firmware build, retired at the same time.
- [Wipe Mode](/usersguide#configurable-wipe-mode) - "Full Wipe" remains available for users who want the self-destruct PIN to erase everything.
