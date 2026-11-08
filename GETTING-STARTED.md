# Publish this new repository to GitHub

This package is intentionally separate from existing SimplifyIAM, Factory Zero Trust IAM, and older Cybernoia repositories. **It does not include a Git repository or connect to your GitHub account automatically.**

## Quick start (Mac terminal)

1. Unzip the downloaded package and open Terminal in the extracted `identity-recon-security-lab` folder.
2. Review `README.md` and the two Checkpoint 2 reports before publishing.
3. Create a **new private** GitHub repository called `identity-recon-security-lab`. Do not check the GitHub boxes to add a README or `.gitignore` (they are in this package).
4. In Terminal, run:

```bash
git init
git add .
git commit -m "Initial IAM Identity Recon portfolio and Checkpoint 2 reports"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/identity-recon-security-lab.git
git push -u origin main
```

Replace `YOUR_USERNAME` with your own GitHub username. GitHub may ask you to authenticate with a credential manager, personal access token or SSH.

### GitHub CLI alternative (if `gh` is installed and authenticated)

Run these commands **instead of steps 3–4**:

```bash
git init
git add .
git commit -m "Initial IAM Identity Recon portfolio and Checkpoint 2 reports"
git branch -M main
gh repo create identity-recon-security-lab --private --source=. --remote=origin --push
```

To publish later, change the GitHub repository visibility only after sanitizing evidence and reviewing all repository files.

## Add your next milestone

When you finish a major checkpoint, add a technical report under `reports/`, a short executive summary only if the risk or decision warrants one, and supporting queries or redacted evidence. Then add a single line to the README progress table.

```bash
git add .
git commit -m "docs: report checkpoint 3 lab results"
git push
```

Do not paste the course's full lesson text into the public project. Keep personal learning notes separately.
