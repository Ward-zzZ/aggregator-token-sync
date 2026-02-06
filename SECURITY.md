# Security Policy / 安全政策

## Supported Versions / 支持的版本

This project uses GitHub Actions workflows. Security updates are applied to the latest version of the workflow files.

本项目使用GitHub Actions工作流。安全更新将应用于工作流文件的最新版本。

| Version | Supported          |
| ------- | ------------------ |
| latest  | :white_check_mark: |

## Reporting a Vulnerability / 报告安全漏洞

### English

If you discover a security vulnerability in this repository, please report it by:

1. **DO NOT** create a public GitHub issue
2. Send a private message through GitHub's security advisory feature:
   - Go to the repository's "Security" tab
   - Click "Report a vulnerability"
   - Fill in the details

We will respond to security reports within 48 hours and work with you to understand and resolve the issue.

### 中文

如果您在本仓库中发现安全漏洞，请通过以下方式报告：

1. **请勿**创建公开的GitHub issue
2. 通过GitHub的安全建议功能发送私密消息：
   - 进入仓库的"Security"标签
   - 点击"Report a vulnerability"
   - 填写详细信息

我们将在48小时内回复安全报告，并与您合作了解和解决问题。

## Security Considerations / 安全注意事项

### Data Source / 数据来源

This repository automatically fetches proxy configuration data from a **public third-party source** (https://github.com/wzdnzd/aggregator/issues/91). The data is already publicly available and is not considered sensitive information.

本仓库自动从**公开的第三方来源**（https://github.com/wzdnzd/aggregator/issues/91）获取代理配置数据。这些数据本身就是公开的，不被视为敏感信息。

### Disclaimer / 免责声明

- We do not control or verify the proxy servers listed in the configuration files
- We are not responsible for the availability, security, or legality of these proxy services
- Use the proxy configurations at your own risk
- Always verify the trustworthiness of proxy servers before use

---

- 我们不控制或验证配置文件中列出的代理服务器
- 我们不对这些代理服务的可用性、安全性或合法性负责
- 使用代理配置需自行承担风险
- 使用前请务必验证代理服务器的可信度

### Automated Workflow / 自动化工作流

This repository uses GitHub Actions with the following security measures:

本仓库使用GitHub Actions，并采取以下安全措施：

- **Limited Permissions**: Workflows only have `contents: write` permission
- **GITHUB_TOKEN**: Uses GitHub's automatically provided token, not custom credentials
- **Secure Triggers**: Only triggered by schedule or manual dispatch, not by pull requests
- **Error Handling**: Implements `set -euo pipefail` for safe script execution

---

- **有限权限**：工作流仅具有`contents: write`权限
- **GITHUB_TOKEN**：使用GitHub自动提供的token，而非自定义凭据
- **安全触发器**：仅由计划任务或手动触发，不接受pull request触发
- **错误处理**：实现`set -euo pipefail`以确保脚本安全执行

## Known Limitations / 已知限制

1. **Third-Party Dependency**: This project relies on external APIs which may become unavailable
2. **Data Accuracy**: We cannot guarantee the accuracy or validity of the proxy configurations
3. **Rate Limits**: GitHub API calls may be subject to rate limiting

---

1. **第三方依赖**：本项目依赖外部API，这些API可能会不可用
2. **数据准确性**：我们无法保证代理配置的准确性或有效性
3. **速率限制**：GitHub API调用可能受到速率限制

## Best Practices for Users / 用户最佳实践

If you fork or use this repository:

如果您fork或使用本仓库：

- ✅ Review the generated configuration files before use
- ✅ Verify proxy server addresses and credentials
- ✅ Use secure connections (TLS/SSL) when possible
- ✅ Be aware of privacy implications when using third-party proxies
- ✅ Keep your fork's workflows and dependencies updated

---

- ✅ 使用前请审查生成的配置文件
- ✅ 验证代理服务器地址和凭据
- ✅ 尽可能使用安全连接（TLS/SSL）
- ✅ 使用第三方代理时注意隐私问题
- ✅ 保持您fork的工作流和依赖项更新

## Contact / 联系方式

For security-related questions or concerns, please use GitHub's security advisory feature or contact the repository maintainer through GitHub.

如有安全相关问题或疑虑，请使用GitHub的安全建议功能或通过GitHub联系仓库维护者。
