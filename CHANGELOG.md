# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.7.2] - 2026-06-16

### Highlights / 亮点

- 编辑连接时密码字段重新支持切换显示 / Password toggle (eye icon) restored in edit-mode connection dialog.
- 密码为空时自动轮询预设密码列表 / Automatic fallback password rotation when the auth field is blank.

### Fixed 修复

- 编辑已有连接时密码眼睛图标被 `hidepass` 隐藏的问题 / Eye icon of the password input was hidden when editing an existing connection due to `:hidepass="editMode"`.

### Added 新增

- `ConnectionWrapper.vue`: 密码为空时依次尝试 4 个预设密码 (`8DxYFFln`、`1p5ig7725w`、`1p5ig7725wQ!`、`A9WpeJAe`),成功后自动写回 localStorage / Fallback password list of 4 presets; successful match is persisted back to localStorage.
- `redisClient.js`: 新增 `testAuth()` 轻量级密码探测方法（`retryStrategy: null`、`maxRetriesPerRequest: 1`）/ New lightweight `testAuth()` helper (`retryStrategy: null`, `maxRetriesPerRequest: 1`).
