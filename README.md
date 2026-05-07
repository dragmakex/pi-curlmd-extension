# pi-curlmd

A [pi](https://github.com/badlogic/pi-mono) extension that brings [curl.md](https://curl.md) into pi.

It recreates the upstream `@curl.md/pi` plugin as a standalone pi package, in the same lightweight package style as `pi-fff`.

## What it does

- Registers `read_web_page` to fetch URLs as markdown
- Registers `curl_md` as a compatibility alias
- Adds `/curl_md_login`, `/curl_md_logout`, `/curl_md_org`, and `/curl_md_status`
- Supports anonymous, API key, and session-based auth
- Uses curl.md's focused extraction modes (`rush`, `smart`), `objective`, and `keywords`

## Install

Requirements:
- pi

### Local package

From this repo:

```bash
pi install /absolute/path/to/extensions/pi-curlmd-extension
```

Or for one-off testing:

```bash
pi -e /absolute/path/to/extensions/pi-curlmd-extension
```

### Published package

If you just want the upstream package, install it directly:

```bash
pi install npm:@curl.md/pi
```

## Configuration

Optional environment variables:

- `CURLMD_API_KEY` - API key for curl.md
- `CURLMD_BASE_URL` - override curl.md base URL

`npm i -g curl.md` installs the CLI, which is useful, but it does not load the pi extension by itself.

## Tools

### `read_web_page`

Fetch a URL as markdown.

Parameters:
- `url` - HTTP(S) URL or bare domain
- `objective` - question to answer from the page
- `keywords` - terms to focus extraction
- `mode` - `rush` or `smart`
- `fresh` - bypass cache

### `curl_md`

Alias for `read_web_page`.

## Commands

- `/curl_md_login` - log in to curl.md
- `/curl_md_logout` - log out
- `/curl_md_org` - switch organization
- `/curl_md_status` - show auth/tool status

## License

MIT
