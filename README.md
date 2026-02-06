# aggregator-token-sync

This repo includes a GitHub Actions workflow that keeps a single, fixed URL up-to-date by extracting the latest `token` from https://github.com/wzdnzd/aggregator/issues/91 and writing the resulting subscription content to `issues_91_latest.yml`.

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
