# aggregator-token-sync

This repo includes a GitHub Actions workflow that keeps a single, fixed URL up-to-date by extracting the latest `token` from https://github.com/wzdnzd/aggregator/issues/91 and writing the resulting subscription content to `issues_91_latest.yml`.

## ⚠️ Important Disclaimer / 重要声明

**English:**
- This repository fetches proxy server configurations from a **public third-party source** (https://github.com/wzdnzd/aggregator/issues/91)
- We do **NOT** own, control, or verify these proxy servers
- We are **NOT** responsible for the availability, security, legality, or reliability of these services
- Use these configurations **at your own risk**
- Always verify the trustworthiness of proxy servers before use
- Review [SECURITY.md](SECURITY.md) for security considerations

**中文：**
- 本仓库从**公开的第三方来源**获取代理服务器配置 (https://github.com/wzdnzd/aggregator/issues/91)
- 我们**不拥有、不控制、不验证**这些代理服务器
- 我们**不对**这些服务的可用性、安全性、合法性或可靠性**负责**
- 使用这些配置需**自行承担风险**
- 使用前请务必验证代理服务器的可信度
- 请查看 [SECURITY.md](SECURITY.md) 了解安全注意事项

## How to run it

1. Push this repository to GitHub (Actions only run on GitHub-hosted repos).
2. Ensure **Actions** are enabled for the repository.
3. Run the workflow manually:
   - Go to **Actions** → **Update token link** → **Run workflow**.
4. Or wait for the scheduled run (every 4 hours).

> **Note:** The workflow uses `GITHUB_TOKEN` to authenticate API requests. This token is **automatically provided** by GitHub Actions and does **not** require any manual setup or configuration. GitHub creates this token for each workflow run automatically.

After it runs, the updated content will be committed into `issues_91_latest.yml`. You can access that file via the raw GitHub URL:

```
https://raw.githubusercontent.com/<owner>/<repo>/<branch>/issues_91_latest.yml
```

Replace `<owner>`, `<repo>`, and `<branch>` with your repository values.

## Troubleshooting: no "Run workflow" button

If you don't see the **Run workflow** button:

- Click into the **Update token link** workflow (not the **All workflows** list).
- Make sure the workflow file exists on the repository **default branch**.
- Check **Settings → Actions → General** and ensure Actions are enabled for the repository.
- Confirm you have **write** permissions on the repo (required to dispatch workflows and push updates).

## Troubleshooting: no `issues_91_latest.yml` after a successful run

- Confirm you are viewing the **default branch** (the workflow pushes there).
- Open the workflow run logs and look for `No changes to commit.` If present, the downloaded content matched the existing file.
- If you still cannot find it, verify the repository allows **read/write** workflow permissions in **Settings → Actions → General**.

## FAQ

### Do I need to manually configure GITHUB_TOKEN?

**No.** The `GITHUB_TOKEN` used in the workflow is **automatically provided** by GitHub Actions. You don't need to:
- Create a personal access token
- Add it to repository secrets
- Configure anything manually

GitHub automatically creates a unique `GITHUB_TOKEN` for each workflow run with the necessary permissions. The workflow uses this token to:
- Authenticate API requests to avoid rate limits
- Push commits back to the repository

The only permission setting you may need to verify is in **Settings → Actions → General → Workflow permissions**, where "Read and write permissions" should be selected (this is usually the default).

## Security / 安全

For security-related information and reporting vulnerabilities, please see [SECURITY.md](SECURITY.md).

关于安全相关信息和漏洞报告，请参阅 [SECURITY.md](SECURITY.md)。

For a comprehensive security analysis of this repository, see [SECURITY_ANALYSIS.md](SECURITY_ANALYSIS.md).

有关本仓库的全面安全分析，请参阅 [SECURITY_ANALYSIS.md](SECURITY_ANALYSIS.md)。

## License / 许可证

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

本项目采用 MIT 许可证 - 详见 [LICENSE](LICENSE) 文件。
