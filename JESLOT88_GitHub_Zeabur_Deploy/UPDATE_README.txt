JESLOT88 扫描补漏更新 v1.0.1

适用服务：https://jes-translation-service.zeabur.app
扫描来源：translation-scan (3).json，jeslot88.org，共 632 条。

结果：
- 原有 779 条 key/value 完整保留，未覆盖旧翻译。
- 103 条漏项已补齐：87 条旧词、标点等变体，16 条新增翻译。
- 389 条已存在的译文或大小写形式加入精确匹配别名，帮助页面切换语言。
- 每种语言现有 1,271 条，六种语言键集合一致。
- 75 条金额、动态时间、网址、游戏标识等保留原样，不属于待翻译文本。
- version.json 升级到 1.0.1，触发现有 Loader 重新下载语言包。

如何更新：
1. 解压此 ZIP。
2. 打开 GitHub 的 jes-translation-service 仓库根目录。
3. 上传解压后的 JESLOT88_GitHub_Zeabur_Deploy 文件夹，保持名称和路径不变，提交更改。
   重要：不要上传 ZIP 本身；不要把文件夹再次套在同名文件夹里面。
   若逐个上传：在原 public/translations 文件夹替换 en/ms/zh/vi/th/bn.json；在原 public 文件夹替换 version.json。
4. 等待 Zeabur 的 GitHub 自动部署完成；若未触发，在服务页重新部署。
5. 根目录保持 /JESLOT88_GitHub_Zeabur_Deploy/public。
6. 打开 https://jes-translation-service.zeabur.app/version.json，确认 version 为 1.0.1。
7. 刷新 JESLOT88 网站，再切换六种语言，检查登录、优惠条件、最高提款等文本。

后台 JS：继续使用之前的 JESLOT88_Translation_Loader_Final.txt，无需修改。
此补丁只有六个完整语言文件、版本文件和补漏报告；不会替换 index.html、health.txt 或 _headers。

验证范围：本地 JSON、原键值保留、六语言完整性、Loader 模拟加载、缓存、快速切换和离线回退检查通过。
尚未上传到 GitHub，未在真实网站验证。扫描只有 text/page/time，不能判断图片文字、iframe、被排除节点或未访问页面；这些不在本次完整性保证范围内。
后续若仍有漏项，请在对应页面重新扫描，最好使用原始语言并展开弹窗、优惠详情后扫描。
