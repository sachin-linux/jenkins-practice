# Jenkins CI/CD Practice

Part of my **Linux Admin / DevOps learning journey** - this repository is used to practice Jenkins CI/CD automation, GitHub webhooks, and aumtomated pipeline triggers.

---

## What This Repo Does

Every time a commit is pushed to this repository, a Jenkins pipeline is automatically triggered via a GitHub webhook. Jenkins pulls the latest code, runs build steps, and reports success or failure - no manual intervention needed.

--- 

## Flow

```
git push -> GitHub -> Webhook -> ngrok -> Jenkins -> Pull code -> Run commands -> SUCCESS
```


---

## Tools Used

| Tool | Purpose |
|------|---------|
| Jenkins | CI/CD automation server |
| GitHub Webhook | Notifies Jenkins on every push |
| ngrok | Exposes local Jenkins to the internet (homelab) |
| Ubuntu 24.04 | Jenkins host (VirtualBox VM) |
| Java 17 | Jenkins runtime dependency |

---

## Jenkins Job - Build Steps

```bash
echo "Code pulled from GitHub successfully"
echo "Branch: $(git branch --show-current)"
ls -la
```

---

## Key Concepts Practiced

- Installing and configuring Jenkins on Ubuntu
- Creating freestyle jobs
- Connecting Jenkins to a GitHub repository
- Configuring webhooks for automatic build triggers
- Using ngrok to expose a local server to the internet
- Reading Jenkins console output
- International pipeline breaking and fixing (troubleshooting practice)

---

## Troubleshooting Practiced

| Problem | Fix |
|---------|-----|
| GPG key verification failed | Used `--armor` flag when exporting key |
| Jenkins UI not loading | Added `-Dhudson.model.UpdateCenter.never=true` to JAVA_ARGS |
| Port 8080 not accessible | `sudo ufw allow 8080` |
| Webhook returning 404 | Updated Jenkins URL to ngrok URL in Manage Jenkins |
| git push auth failed | Used GitHub Personal Access Token |
| ngrok URL changed | Updated Payload URL in GitHub webhook settings |

---

## Part of 

[Linux-admin-homelab](https://(https://github.com/sachin-linux/linux-admin-homelab) - My full DevOps learning repo documenting the journey from sysadmin to DevOps/Linux Admin.

---

*Learning in Public | | #OpenToWork | Target: Junior DevOps / Linux Admin role*
