# Android 开发者验证（上架新 App）操作说明

适用场景：在 Google Play 上架**新应用**时，需要完成 Android 开发者验证（Developer Verification / APK Signing 相关校验）。

参考仓库：`yangcai2016/security-samples`（该仓库 README 指向官方 `AndroidDeveloperVerificationAPKSigningExample` 示例）。

## 你需要做什么

1. 在你的 Android 项目中创建验证文件：`adi-registration.properties`。
2. 按官方示例的目录结构放置该文件（不要改文件名）。
3. 将平台给你的开发者唯一校验片段（snippet）写入该文件。
4. 确保该文件会被正确打包/参与构建（根据官方示例检查 placement）。
5. 使用发布签名证书重新构建 APK/AAB，并上传到 Play Console 进行验证。

## 建议检查清单（提交前）

- [ ] `adi-registration.properties` 文件名准确无误。
- [ ] 文件路径与官方示例一致。
- [ ] snippet 完整粘贴，无多余空格/换行。
- [ ] 使用的是 **release** 签名而非 debug 签名。
- [ ] 上传的是本次重新构建的包（避免上传旧产物）。

## 常见失败原因

- 文件路径放错（最常见）。
- snippet 填写错误或复制不完整。
- 上传包不是包含最新验证文件的版本。
- 签名证书和期望不一致。

## 说明

`yangcai2016/security-samples` 的 README 显示：旧样例已标注 deprecated，并建议优先参考官方 sample 与 Android Developers 样例站点。因此建议你直接对照官方示例做验证文件落位和打包检查。
