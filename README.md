# aggregator-token-sync

This repo includes a GitHub Actions workflow that keeps a single, fixed URL up-to-date by extracting the latest `token` from https://github.com/wzdnzd/aggregator/issues/91 and writing the resulting subscription content to `issues_91_latest.yml`.

## How to run it

1. Push this repository to GitHub (Actions only run on GitHub-hosted repos).
2. Ensure **Actions** are enabled for the repository.
3. Run the workflow manually:
   - Go to **Actions** → **Update token link** → **Run workflow**.
4. Or wait for the scheduled run (every 4 hours).

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
