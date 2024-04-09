# hexo-themes

项目使用 git submodule 管理主题。

- [x] hexo-theme-typo：a simle theme named typo for hexo.

## 开发备忘

### 部署到子站点

如果您的网站需要部署到子目录，如部署到 github 项目站点，需要修改 hexo 部分配置：

- `url`：您的站点url
- `root`：站点根路径，默认为 `/`

假如我要将站点部署至 <https://rankangkang.github.io/hexo-theme-typo>（其中 `hexo-theme-typo` 是我的仓库名，站点是该仓库的github页面），则需进行如下配置：

```yaml _config.yaml
url: https://rankangkang.github.io/hexo-theme-typo
root: /hexo-theme-typo/

# github 部署配置
deploy:
  type: git
  repo: https://github.com/rankangkang/hexo-theme-typo.git
  branch: deploy
```

值的注意的是，若标签引用了项目内的静态资源，需要使用 hexo [辅助函数](https://hexo.io/zh-cn/docs/helpers#js)引入，辅助函数会根据配置输出正确的引用标签。

```ejs
<!-- ❌ bad -->
<script src="/js/theme.js"></script>

<!-- 👍 good -->
<%- js('js/theme.js') %>
```
