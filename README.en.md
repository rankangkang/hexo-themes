# hexo-themes | 👉🏻 [zh_CN](./README.md)

The project uses git submodule to manage themes.

- [x] hexo-theme-typo: a simple theme named typo for hexo.

## Quick start

```bash
pnpm i

pnpm start

pnpm deploy # if you want to
```

## Development Notes

### Deploy to Subdirectory

If your site needs to be deployed to a subdirectory, such as deploying to a GitHub project site, you need to modify some hexo configurations:

- `url`: Your site URL
- `root`: Site root path, default is `/`

Suppose I want to deploy the site to <https://rankangkang.github.io/hexo-theme-typo> (where `hexo-theme-typo` is my repository name, and the site is the GitHub page of that repository), the configuration should be as follows:

```yaml _config.yaml
url: https://rankangkang.github.io/hexo-theme-typo
root: /hexo-theme-typo/

# GitHub deployment configuration
deploy:
  type: git
  repo: https://github.com/rankangkang/hexo-theme-typo.git
  branch: deploy

```

It is worth attention that if tags reference static resources within the project, you need to use hexo helper functions to include them. The helper functions will output the correct reference tags based on the configuration.

```html
<!-- ❌ bad -->
<script src="/js/theme.js"></script>

<!-- 👍 good -->
<%- js('js/theme.js') %>
```
