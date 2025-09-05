### Checkout single directory


If you want to get a single directory from the [Upstream](https://github.com/mbadolato/iTerm2-Color-Schemes)
use this command *git clone --filter + git sparse-checkout downloads only the required files*

E.g., to clone only files in subdirectory termux/ from the source repository: [iTerm2-Color-Schemes](https://github.com/mbadolato/iTerm2-Color-Schemes.git)

```
git clone --no-checkout --depth=1 --filter=tree:0 \
  https://github.com/mbadolato/iTerm2-Color-Schemes.git
cd iTerm2-Color-Schemes
git sparse-checkout set --no-cone /termux
git checkout
```

You could also select multiple directories for download with:

`git sparse-checkout set --no-cone /termux /tools` or `/vscode`

The slash in `/termux` is required, if you do just `termux` then git also downloads any other directory with basename `termux`.

**Note**: This method doesn't work for individual files.

License see [LICENSE]