# How to upload existing code into a newly created repo

This is meant as a 'how to' guide on how to take existing code and upload it and create a github repo at the same time.

## TLDR

Run the following commands to 
- Install Github CLI via Winget

    `winget install -e --id GitHub.cli`
- Create brand new solution 

    `dotnet new sln -o UploadExistingCodeToNewRepo`
- Create new project inside new solution

    `dotnet new webapi -o .\UploadExistingCodeToNewRepo\UploadExistingCodeToNewRepo.WebApi`
- Add new project into new solution

    `dotnet sln .\UploadExistingCodeToNewRepo\UploadExistingCodeToNewRepo.sln add .\UploadExistingCodeToNewRepo\UploadExistingCodeToNewRepo.WebApi\UploadExistingCodeToNewRepo.WebApi.csproj`
- Copy ReadMe.md and .gitignore into new solution

    `Copy-Item .\ReadMe.md, .\.gitignore -Destination .\UploadExistingCodeToNewRepo\`
- Create new repo in github

    `git -C .\UploadExistingCodeToNewRepo init`
- Create new repo in github Github CLI

    `gh repo create UploadExistingCodeToNewRepo --public --source=.\UploadExistingCodeToNewRepo`    
- Change directory to UploadExistingCodeToNewRepo

    `cd .\UploadExistingCodeToNewRepo\`
- Add files to commit

    `git add --all`
- Commit files

    `git commit -m "Initial Commit"`
- Initial push and setting master branch

    `git push --set-upstream origin master`