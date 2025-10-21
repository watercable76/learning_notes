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

### Azure  

When setting up an org, custom roles will be limited by custom rules that limit the role to be assigned  

Also, there should be a role that allows a managed identity permission to deploy resources and make role assignments. The role assignments might be separated out from the resource deployments, but that depends
