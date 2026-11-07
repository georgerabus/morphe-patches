# Morphe Patches with Loop count

This branch publishes [Morphe Patches](https://github.com/MorpheApp/morphe-patches) with the **Loop count** patch added.

Loop count adds a **Loop count** item next to **Loop video** in the YouTube player menu (gear → More). It sets how many times a video plays, then Loop video turns off and the next video plays. In a playlist, the count is saved for each video. Pull request to Morphe Patches: [#4516](https://github.com/MorpheApp/morphe-patches/pull/4516).

## Use it in Morphe Manager

1. **Sources** → **Add** → `https://github.com/georgerabus/morphe-patches`
2. Turn off the official Morphe Patches source, so only one of the two bundles patches YouTube.
3. Leave **Pre-release** off for this source.

Morphe Manager then shows the updates of this source, as it does for the official one.

## How it is built

Every Monday, the [workflow](.github/workflows/build-loop-count.yml):

1. Takes the latest release of Morphe Patches (its `main` branch).
2. Adds the Loop count commits of the [`feat/loop-count`](https://github.com/georgerabus/morphe-patches/tree/feat/loop-count) branch on top.
3. Builds the bundle and publishes it as a [release](https://github.com/georgerabus/morphe-patches/releases), with `patches-bundle.json` in this branch for Morphe Manager.

If nothing changed since the last release, nothing is published. If the Loop count commits conflict with a new version of Morphe Patches, or the build fails, the workflow fails and nothing is published.
It can also be started by hand: **Actions** → **Build Morphe Patches with Loop count** → **Run workflow**.

The bundle is not signed. If Morphe Patches adds Loop count, use the official source again.

## License

Morphe Patches and Loop count are licensed under the [GPLv3](https://github.com/georgerabus/morphe-patches/blob/feat/loop-count/LICENSE), see the [NOTICE](https://github.com/georgerabus/morphe-patches/blob/feat/loop-count/NOTICE). The source code of each release is in the `feat/loop-count` branch and in Morphe Patches.
