# Learning Notes Repository  

Documenting all knowledge in a cloud based storage system  

## Topics  

### GitHub  

Run the following in powershell to delete all failed workflow runs:  

```powershell
# Commands to delete workflows
# https://cli.github.com/manual/gh_run_delete
foreach ($run in (gh run list -s failure -R "owner/repo" --json databaseId | ConvertFrom-JSON -Depth 100)) {
  write-output $run.databaseId;
}
```

How to set aliases:

```powershell
gh alias set co "pr checkout"
gh alias set sd "pr merge -s -d"
gh alias set vw "pr view --web"
```
