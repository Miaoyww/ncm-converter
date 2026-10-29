# NCM 格式转换

Nons 功能插件：批量将本地 NCM 恢复为原始 MP3 或 FLAC，保留歌曲信息与内嵌封面，默认保存到原文件目录。

- 权限：`ui`、`files:selected`；文件范围 `*`，无网络权限。
- 工具入口位于 Nons 的“工具”页面，也可从设置左侧打开。
- 单文件上限 256MiB，每批最多 128 个；失败后继续，可重试失败项。

## 构建

```bash
pnpm install
pnpm test
pnpm build
```

`pnpm build` 执行 TypeScript 检查、打包 `frontend/index.tsx`、校验产物并生成 `ncm-converter-<版本>.zip`。依赖 `@nonsplayer/plugin-sdk`；该 npm 包发布前无法安装依赖，首次推送前需先发布 SDK，并提交本目录的 `pnpm-lock.yaml`。

## 发布

推送 `v<版本>` tag，`Release` 工作流校验 tag 与 `manifest.json` 版本一致，构建并上传 `ncm-converter-<版本>.zip`。NonsPlayer 插件目录按该 Release 生成索引。

## 安装

在 Nons 设置 → 插件中安装 ZIP 并确认权限。
