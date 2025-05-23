---
sidebar_label: Snaps CLI
sidebar_position: 3
toc_max_heading_level: 4
description: See the Snaps CLI subcommands reference.
---

import Tabs from "@theme/Tabs";
import TabItem from "@theme/TabItem";

# Snaps CLI

This reference describes the syntax of the Snaps command line interface (CLI) subcommands and
subcommand options.

You can specify subcommands and their options using the `yarn mm-snap` command:

```bash
yarn mm-snap [SUBCOMMAND] [SUBCOMMAND OPTIONS]
```

:::note
This documentation assumes you created your Snap using the [`@metamask/create-snap`](https://github.com/MetaMask/snaps/tree/main/packages/create-snap) starter kit, which includes the Snaps CLI.
You can also install the CLI directly using the [`@metamask/snaps-cli`](https://github.com/MetaMask/snaps/tree/main/packages/snaps-cli) package.
:::

### `b`, `build`

```bash
yarn mm-snap build
```

Builds a Snap from source.

`b` is an alias for `build`.

#### `analyze`

<Tabs>
<TabItem value="Syntax">

```bash
yarn mm-snap build --analyze
```

</TabItem>
</Tabs>

Enables analyzing the Snap [bundle](../learn/about-snaps/files.md#bundle-file).
This uses [`webpack-bundle-analyzer`](https://github.com/webpack-contrib/webpack-bundle-analyzer) under the hood,
which creates an interactive visualization of the contents of your bundle.
The visualization is located at the URL displayed in the command line output (for example, `http://localhost:8888`).

:::info
This option requires [`@metamask/snaps-cli`](https://github.com/MetaMask/snaps/tree/main/packages/snaps-cli) version 6.7.0 or later.
:::

#### `c`, `config`

<Tabs>
<TabItem value="Syntax">

```bash
yarn mm-snap build --config <FILE>
```

</TabItem>
<TabItem value="Example">

```bash
yarn mm-snap build --config ./snap.config.build.ts
```

</TabItem>
</Tabs>

Path to the [configuration file](../learn/about-snaps/files.md#configuration-file),
which specifies [options](config-options.md) with which to the build the Snap.

`-c` is an alias for `--config`.

### `e`, `eval`

```bash
yarn mm-snap eval
```

Attempts to evaluate the Snap bundle in
[Secure ECMAScript (SES)](../learn/about-snaps/execution-environment.md#secure-ecmascript-ses).

`e` is an alias for `eval`.

### `m`, `manifest`

```bash
yarn mm-snap manifest
```

Validates the Snap [manifest file](../learn/about-snaps/files.md#manifest-file).

`m` is an alias for `manifest`.

#### `fix`

<Tabs>
<TabItem value="Syntax">

```bash
yarn mm-snap manifest --fix
```

</TabItem>
</Tabs>

Enables making any changes to fix the manifest file.

### `sandbox`

```bash
yarn mm-snap sandbox
```

Starts a [Snaps sandbox](../how-to/test-a-snap.md#test-in-the-sandbox) server, where you can interact with and test a Snap.

:::info
This option requires [`@metamask/snaps-cli`](https://github.com/MetaMask/snaps/tree/main/packages/snaps-cli) version 7.1.0 or later.
:::

### `s`, `serve`

```bash
yarn mm-snap serve
```

Locally serves Snap files for testing.

`s` is an alias for `serve`.

#### `p`, `port`

<Tabs>
<TabItem value="Syntax">

```bash
yarn mm-snap serve --port <PORT>
```

</TabItem>
<TabItem value="Example">

```bash
yarn mm-snap serve --port 9000
```

</TabItem>
</Tabs>

The local server port for testing.
The default is `8081`.

`-p` is an alias for `--port`.

### `w`, `watch`

```bash
yarn mm-snap watch
```

Rebuilds a Snap from source upon changes.

`w` is an alias for `watch`.

#### `p`, `port`

<Tabs>
<TabItem value="Syntax">

```bash
yarn mm-snap watch --port <PORT>
```

</TabItem>
<TabItem value="Example">

```bash
yarn mm-snap watch --port 9000
```

</TabItem>
</Tabs>

The local server port for testing.
The default is `8081`.

`-p` is an alias for `--port`.

## Global options

#### `h`, `help`

```bash
-h, --help
```

Displays the help message and exits.
You can use this option with `mm-snap` or any subcommand.

`-h` is an alias for `--help`.

#### `version`

```bash
--version
```

Displays the version number and exits.
