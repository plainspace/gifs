[![Board Status](https://dev.azure.com/plainspace/59ed3e73-2d2c-4597-b8c8-8d3aa33de809/6584a0f7-5545-44ed-9a0a-528bb1464046/_apis/work/boardbadge/41b39094-11e3-432a-a256-3076958ca41f)](https://dev.azure.com/plainspace/59ed3e73-2d2c-4597-b8c8-8d3aa33de809/_boards/board/t/6584a0f7-5545-44ed-9a0a-528bb1464046/Microsoft.RequirementCategory)

# gif storage

Storage place for all my favorite gifs.

![thumbs up](thumbs-up/thumbs-up.gif)

## Contributing

Feel free to open a pull request if you have a gif that you really think belongs in here. However, I will only accept images that I think I will personally want to use.

I'm not trying to build a comprehensive storage place for the world's best gifs, just trying to organize all the gifs I personally use. I sync these locally, so I'll be somewhat selective about adding new stuff. That said, feel free to suggest ones you think are awesome, and if I don't accept the PR just fork the repo and add to your own! :thumbsup:

## 🧪 Running the Site Locally

To run this site locally, you’ll need:

### ✅ Requirements

- **Ruby** (>= 3.0) — [Install instructions](https://www.ruby-lang.org/en/documentation/installation/)
- **Bundler** — install with:

  ```bash
  gem install bundler
  ```

---

### ▶️ Local Setup

1. **Clone the repo** and navigate to it:

   ```bash
   git clone https://github.com/your-username/your-repo.git
   cd your-repo
   ```

2. **Install dependencies**:

   ```bash
   bundle install
   ```

3. **Start the development server**:

   ```bash
   ./script/serve
   ```

   The script starts at port 4000, jumps to 4004 if 4000 is taken, then bumps to the next open port if needed. Extra flags are passed through to `jekyll serve`.

4. Open your browser to:

   ```
   http://localhost:4000 (or the next available port)
   ```

   The site will auto-reload as you make changes.

---

### 🧩 Troubleshooting

- If you see errors about native extensions (like `json` gem), make sure your Ruby version is compatible. Some older gems don’t work on the newest Ruby versions (e.g., 3.4.2).
- If `main.css` isn’t found, ensure your `_sass`, `_includes`, and layout files are configured correctly and that SCSS is being processed.
- If using `github-pages` gem, note that it may lock Jekyll to a specific version (e.g., 3.9.3). You may need to downgrade Jekyll or avoid `github-pages` if you want the latest Jekyll features.

## Curating your own gif library

You can also [fork](https://github.com/jglovier/gifs/fork) this repository to your own account, and have your own gif library. Once you fork to your own account, you can even host your own GH Pages site ([like mine](http://gifs.joelglovier.com/)) by editing or removing the [CNAME](https://github.com/jglovier/gifs/blob/gh-pages/CNAME) file in your fork accordingly.

To update the site index on the GH Pages site, you'll need to run the index build script. Just clone the project to your local machine, open Terminal, and `cd` into the repo. Then, run `script/build_site_index` and commit your changes. Once the new index is commited to your gh-pages branch, it will be live on your site as soon as the CDN updates (usually within a few minutes).

## Gifwit support

Thanks to [@orderedlist](http://github.com/orderedlist), you can quickly access all the gifs in my repo via the handy OSX app [Gifwit](http://gifwit.com/). Just download the [library.gifwit](http://gifs.joelglovier.com/library.gifwit) file and open in Gifwit. Gifwit will import all the gifs from the repo and you'll be able to easily access the production URLs via keyboard shortcuts. :zap:
