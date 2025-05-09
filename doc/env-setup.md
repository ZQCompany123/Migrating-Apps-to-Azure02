# Environment setup
1. Fork application repository
2. Add devcontainer.json to the repo to create a codespace environment with all the tooling required.

   ```json
   {
     "image": "mcr.microsoft.com/devcontainers/base:noble",
     "features": {
       "ghcr.io/devcontainers/features/powershell:1": {
         "modules": ["Az.Accounts", "Az.Resources", "Az.KeyVault"]
       },
       "ghcr.io/devcontainers/features/docker-in-docker:2": {},
       "ghcr.io/devcontainers/features/azure-cli:1": {
         "version": "latest",
         "installBicep": true
       },
       "ghcr.io/azure/azure-dev/azd:0": {},
       "ghcr.io/devcontainers/features/github-cli:1": {},
       "ghcr.io/devcontainers/features/dotnet:2": {}
     },
     "customizations": {
       "vscode": {
         "extensions": [
           "cschleiden.vscode-github-actions",
           "esbenp.prettier-vscode",
           "GitHub.copilot",
           "github.vscode-pull-request-github",
           "microsoft-dciborow.align-bicep",
           "ms-azuretools.vscode-bicep",
           "ms-vsliveshare.vsliveshare",
           "ms-azuretools.vscode-azureresourcegroups",
           "ms-vscode-remote.remote-containers",
           "zokugun.explicit-folding",
           "GitHub.copilot-labs",
           "zjffun.snippetsmanager"
         ]
       }
     },
     "postCreateCommand": "dotnet tool install -g upgrade-assistant",
     "postStartCommand": ""
   }
   ```
3. Start a new codespace in GitHub
