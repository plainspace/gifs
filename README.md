# gif storage

Storage place for all my favorite gifs.

![thumbs up](thumbs-up/thumbs-up.gif)

## Features

- **Browse & preview** — hover any GIF to preview it in the sidebar
- **Click to copy** — click a GIF link to copy its URL to clipboard
- **Search Giphy** — search for GIFs and save them directly to your collection
- **Pin collections** — pin your favorite categories to the top of the page
- **Delete GIFs** — hover a GIF and hit × to remove it
- **Masonry layout** — collections display in a responsive grid

## Requirements

- **Ruby** (>= 2.6)
- **Bundler** — `gem install bundler`

## Setup

```bash
git clone https://github.com/plainspace/gifs.git
cd gifs
bundle install
```

## Running locally

You need two processes running:

### 1. Jekyll dev server

```bash
./script/serve
```

Starts at port 4000 (bumps to next available if taken). The site auto-reloads on changes.

### 2. Save server

```bash
ruby script/save_server
```

Runs on port 4005. Handles saving GIFs, deleting GIFs, and persisting pinned collections. Without this server running, search/save/delete/pin features won't persist.

You can change the port with `SAVE_PORT=5000 ruby script/save_server`.

## Usage

### Adding GIFs manually

Drop `.gif` files into a category folder (create one if needed), then rebuild the index:

```bash
script/build_site_index
```

### Adding GIFs via search

1. Make sure the save server is running
2. Type a search query in the sidebar and hit Search
3. Click **+ Add** on a result
4. Edit the filename, pick a category (or type a new one), and hit **Save to Collection**
5. Reload the page to see it

### Pinning collections

Click the pin icon on any collection to pin it to the top. Pins are saved to `_data/pins.json` via the save server and also cached in localStorage between rebuilds.

### Deleting GIFs

Hover over a GIF name and click the **×** button. Confirm the deletion. The file is removed from disk, and empty category folders are cleaned up automatically.

### Giphy API key

Search requires a Giphy API key. Get one at [developers.giphy.com](https://developers.giphy.com/) and add it to `_config.yml`:

```yaml
giphy_api_key: YOUR_API_KEY
```

## Scripts

| Script | What it does |
|--------|-------------|
| `script/serve` | Starts Jekyll dev server |
| `script/save_server` | Starts the save/delete/pin server |
| `script/build_site_index` | Rebuilds `_data/static_files.yml` and `_includes/site-index.html` from GIF files on disk |

## Troubleshooting

- **Save/delete not working?** Make sure `ruby script/save_server` is running in a separate terminal.
- **GIF not showing after save?** Reload the page. Jekyll should auto-rebuild, but sometimes you need a manual refresh.
- **Masonry layout broken?** Hard refresh (Cmd+Shift+R) to clear CSS cache.
- **Native extension errors?** Check your Ruby version is compatible. Some older gems don't work on the newest Ruby versions.

## Contributing

Feel free to open a pull request if you have a gif that you really think belongs in here. However, I will only accept images that I think I will personally want to use.

## Curating your own gif library

[Fork](https://github.com/jglovier/gifs/fork) this repository and host your own GH Pages site. Run `script/build_site_index` and commit to update the live index.
