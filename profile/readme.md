## Local
`dotnet nuget add source "https://nuget.pkg.github.com/silvester-io-libraries/index.json" --name "silvester-io-libraries" --username "{SOME_GITHUB_USERNAME}" --password "{SOME_PAT_WITH_PACKAGES_READ_PERMISSIONS}"`

## Actions
Workflows need the service-account PAT secrets. Because free organizations can't have organization-wide secrets, we need to add them to each repository that want's to restore. 

##### Add Repository Secrets
```bash
gh secret set NUGET_RESTORE_TOKEN -R silvester-io-libraries/library-dotnet-client-one-password --body "ghp_K..."
gh secret set NUGET_RESTORE_USERNAME -R silvester-io-libraries/library-dotnet-client-one-password --body "ghp_K..."
```

##### Verify Repository Has Secret
To check if the repository alreayd has it:  
`gh secret list -R {ORGANIZTION_NAME}/{REPO_NAME} | grep NUGET_RESTORE`
e.g.
`gh secret list -R silvester-io-libraries/library-dotnet-client-one-password | grep NUGET_RESTORE`