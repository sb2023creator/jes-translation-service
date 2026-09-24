# JESLOT88 六语言翻译服务

根据 `source-text(1).json` 的 799 条扫描文本制作。六种语言各有 779 个原始文本键：en 英语、ms 马来语、zh 中文、vi 越南语、th 泰语、bn 孟加拉语。

20 条动态手机号、时间和开奖日期不进入静态翻译字典，见 `EXCLUDED.json`。未匹配到的文字由前端保留原文。游戏品牌、玩法代码、语言选择器名称及图标标识按需保留。

## GitHub 上传

1. 解压 ZIP，新建仓库，建议命名 `jeslot88-translation-service`。
2. 上传解压后的文件内容并提交到 main；不要只上传 ZIP。
3. 查看仓库首页实际目录，以此设置 Zeabur 根目录。

## Zeabur 新项目

新建项目 → 添加 GitHub 服务 → 选择 JESLOT88 新仓库 → main → 配置根目录。

| GitHub 仓库首页显示 | Zeabur 根目录 |
| --- | --- |
| `public` 文件夹 | `/public` |
| `JESLOT88_GitHub_Zeabur_Deploy` 文件夹 | `/JESLOT88_GitHub_Zeabur_Deploy/public` |

确认构建计划为 `static` 再部署。无需 Node.js、安装依赖、构建/启动命令、数据库或 API Key。

在网络中生成独立域名，前缀可尝试 `jeslot88-translation-service`，以实际可用名称为准；绑定 HTTP 8080。

官方说明：https://zeabur.com/docs/zh-TW/guides/static

## 上线检查

将 `YOUR-DOMAIN` 替换为实际生成的域名：

- `https://YOUR-DOMAIN/health.txt` 应返回 `JESLOT88 translation service OK`。
- `https://YOUR-DOMAIN/version.json` 应返回版本 JSON。
- `https://YOUR-DOMAIN/translations/zh.json` 应返回中文词典。
- 再检查 en、ms、vi、th、bn 的 JSON。

URL 无需加 `/public`。如果返回 HTML，应检查根目录和访问路径。

`_headers` 已设置 JSON 类型、公开跨域读取与缓存重新验证。实际网站仍需检查网络请求是否成功、响应是否带 `Access-Control-Allow-Origin: *`。

## 后台 loader

词典部署后还需要在 JESLOT88 网站后台安装翻译 loader；字典本身不会自动修改网站。

- 语言文件：`https://YOUR-DOMAIN/translations/{lang}.json`
- 版本文件：`https://YOUR-DOMAIN/version.json`
- 独立缓存前缀建议：`jeslot88_translation_v1`
- 语言码：en / ms / zh / vi / th / bn

域名确认后再配置完整 loader。前端匹配键应基于原始文本；切换语言时保留原始文本映射。不要使用 BBJ 的域名或缓存前缀。

## 后续更新

更新语言 JSON 后，同步递增 `public/version.json` 的 version 并更新 updated_at。提交到 GitHub，确认新部署完成。

新增扫描文本时，跳过已存在的键，只补真正新增的内容；需要修正原文或旧译文时另行处理。

## 核对状态

已检查六语种键集合、JSON 格式、非空值、数字及百分比、跨公司名称是否被无意引入。序数可按目标语言用文字表达（例如 1st → 首次）。

未做母语人工审校、JESLOT88 实际网页切换测试或线上部署验证。原文中的金额矛盾、外公司条款和宣传声明见 `REVIEW_NOTES.md`；金额没有擅自修改。
