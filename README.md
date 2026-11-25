# FROSTCORE updates

Where installed copies of FROSTCORE look for new versions. Nothing here needs to be opened by hand.

- `route.json` is the first file every app reads. It lists where each platform's manifest lives (here,
  read directly and through jsDelivr). To move the updates to another host, publish the files there and
  replace this file with `{"moved": "<url of the new route.json>"}`. Apps follow it and remember the new place.
- `manifest-<platform>.json` (`win`, `win7`, `linux`) names the newest version, what is new, the patch packs
  and the full installer.
- Releases hold the files: `FROSTCORE-<from>-to-<to>-<platform>.fcpk` packs carry only the files that changed,
  Brotli-compressed, each checked by SHA-256 before and after it is put in place. Anything more than three
  versions behind gets the full installer.

Made by `tools/desktop/publish_update.sh` in the FROSTCORE source.
