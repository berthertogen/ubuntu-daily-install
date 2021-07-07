
alias edit-bash="code  ~/.bashrc"
alias edit-installs="code  ~/Documents/installed-tooling"

alias cd-koala="cd  ~/Ferm/Repositories/Koala/Koala"
alias cd-nala="cd  ~/Ferm/Repositories/Nala/Nala"
alias cd-wombat="cd  ~/Ferm/Repositories/Koala/Wombat"
alias cd-docker="cd  ~/Docker/mssql/ferm"
alias cd-localdevops="cd  ~/Ferm/Repositories/SharedComponents/LocalDevOps"
alias cd-devops="cd  ~/Ferm/Repositories/SharedComponents/DevOpsDashboard"
alias cd-locatieplanner="cd  ~/Ferm/Repositories/SharedComponents/LocatiePlanner"
alias cd-presto="cd  ~/Ferm/Repositories/SharedComponents/PresTo"
alias cd-taco="cd  ~/Ferm/Repositories/SharedComponents/TaCo"
alias cd-auto="cd  ~/Ferm/Repositories/SharedComponents/AuTo"

alias do-koala="pwsh  ~/Ferm/Repositories/Koala/Koala/.local-devops/do-koala.ps1"
alias do-wombat="pwsh  ~/Ferm/Repositories/Koala/Wombat/.local-devops/do-wombat.ps1"
alias do-presto="pwsh  ~/Ferm/Repositories/SharedComponents/PresTo/.local-devops/do-presto.ps1"
alias do-taco="pwsh  ~/Ferm/Repositories/SharedComponents/TaCo/.local-devops/do-taco.ps1"
alias do-locatieplanner="pwsh  ~/Ferm/Repositories/SharedComponents/LocatiePlanner/.local-devops/do-locatieplanner.ps1"

alias dotnet-test-units='dotnet test --filter FullyQualifiedName\!~IntegrationTests'
alias dotnet-test-integration='dotnet test --filter FullyQualifiedName~IntegrationTests'
alias dotnet-test-coverage='dotnet test --collect:"XPlat Code Coverage"; reportgenerator "-reports:TestResults/*/coverage.cobertura.xml" "-targetdir:coveragereport" -reporttypes:Html; chromium coveragereport/index.html'
alias dotnet-hard-clean="find . -type d \( -name node_modules -o -name dir2 -o -path name \) -prune -false -o -iname \"bin\" -o -iname \"obj\"  | xargs rm -rf"

alias git-branch-clean="git fetch --prune --all && git branch --merged | grep -v develop | grep -v master | xargs -n 1 git branch --delete"

alias npm-run-e2e="npm run e2e -- --env dbServer=192.168.1.18"
alias npm-run-e2e-open="npm run e2e:open -- --env dbServer=192.168.1.18"

alias ga="git add ."
alias gc="git commit -m"
alias gch="git checkout"
alias gchd="git checkout develop && git pull"
alias gpl="git pull"
alias gplo="git pull origin"
alias gps="git push"
alias gpsu="git push --set-upstream origin"

alias shitsonfire="~/Documents/liquidcfg.sh"
