# 541nty/fenlight.github.io

Distribution / packages repo for the FenLight Kodi addon. Used by the in-addon updater (`modules/updater.py`) and by the addon-icon picker dialog (`indexers/dialogs.py`).

The actual addon source is at **[541nty/plugin.video.fenlight](https://github.com/541nty/plugin.video.fenlight)**.

## Layout

```
packages/
├── fenlight_version          # plain text — current published version
├── fenlight_changes          # plain text — recent changelog
├── plugin.video.fenlight-X.X.X.zip   # one per release
├── addon_icons/              # full-size addon-icon PNGs
│   └── minis/                # corresponding small/menu thumbnails
└── media/                    # icons + flags + posters used by the addon UI
    ├── icons/
    ├── flags/
    ├── network_icons/
    └── ...
```

`fenlightam_version` and `fenlightam_changes` are duplicates of the above kept around because some downstream addons request them under that name.

## Configuring FenLight to use this repo

In FenLight: **Settings → General → Manage Updates**:

- **GitHub Username:** `541nty`
- **GitHub Repo Address:** `fenlight.github.io`

Then **Tools → Update Utilities → Check For Updates**.

## Auto-sync

`.github/workflows/sync-release.yml` polls `541nty/plugin.video.fenlight` releases hourly and on each new release commits the zip + version manifest here automatically. Manual runs via the Actions tab if needed.
