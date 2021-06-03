# git-github

[Curso git github curso em vídeo](https://www.cursoemvideo.com/course/curso-de-git-e-github/)  
[Repositorio do curso no github](https://github.com/gustavoguanabara/git-github)

Git - Software de controle de versão  
Github - Plataforma de rede social para programadores  

VCS - Version Control Software  

o Git é um VCS distribuido, ou seja, permite que você faça o versionamento local, e em seguida suba o versionamento para o repositório remoto, não necessáriamente ao mesmo tempo.  

![](/images/exemplo-git-github.png)  

Editado direto pelo github  
! + Enter no arquivo HTML já é criada uma estrutura base de HTML.  
lorem + Enter já é disponibilizado o texto.  
Ctrl + Enter faz o commit no github desktop.  
Ctrl + P faz o push  
Ctrl + Shift + P faz o pull  


COMANDOS GIT  
Create | Clone
	Create new repository 
		git init
	Clone local repository
		git clone /path/to/repository
	Clone remote repository
		git clone urlRepository
	Set repository or change repository
		git remote set-url origin urlRepository
	Show remote repository
	git remote
	git remote -v
Link local repository to remote repository
	git remote add origin urlRepository
Show informations about remote repository
	git remote show origin
Unlink remote repository
	git remote rm urlRepository



Credentials | Security
	Remove credentials
		git config --system --unset credential.helper
Set credentials
git config --global user.name userName
git config --global user.email userEmail
git config --global user.password userPassword
Save credentials to not ask again before each commit
git config credential.${remote}.username userName
git config credential.${remote}.password userPassword
git config credential.helper store 


Add | Remove changes
	Add changes to index
		git add fileName
	Add all changes to index
		git add --all
	Remove changes locally
		git rm fileName
	Remove changes
		git checkout fileName
	Remove directory
		git rm -r pathOrName


Commit | synchronize
	Show status
		git status
	Commit changes
		git commit -m “commit message”
	Push changes to remote repository
		git push origin branchName
	Connect local repository to remote repository
		git remote add origin urlRepository
	Update local repository with remote changes
		git pull
	Change commit message without change files on local repository
		git reset --soft HEAD~1
		git push -f origin HEAD^:branchName // Remove the commit from branch
		git commit -m “New Commit message”
		git push origin master
	Eliminate the last 3 commits keeping files changes
		git reset --soft HEAD~3
	Eliminate the last 3 commits keeping files changes with interactive mode
		git rebase -i HEAD~3		
	Remove files to stage (git add fileName) and send beck to untracked files
		git reset HEAD fileName
	Verify code in older versions
		git checkout commitCode
		git checkout branchName // go back to actual code eg. git checkout master
	Delete commit with all changes
		git reset --hard
	Follback Return commit 
git reset --hard {hash-do-commit-desejado}
	Show difference of changes before commit
		git diff fileName
		git diff --name only // Shows only file Names
	Change last commit message
git commit -m “New commit message” --amend	





Log
	See commit log
		git log --pretty=oneline
	Show history with two last changes
		git log -p -2
	Show history log from specific file
		git log fileNameOrPath
	Show history of file modifications
		git log --diff-filter=M --finleNameOrPath // A-added | C-coppied | D-deleted | M-modified | R-renamed
	Show history from author
		git log --author=username
		git log --author=username --pretty=oneline
	Search commit log by commit message
		git log --grep=”123456” --pretty=oneline
		git log --grep=”WordOfCommit” --pretty=oneline
		

Branches
	Create new branch
		git checkout -b branchName
	Switch to master branch
		git checkout master
	Delete branch
		git branch -d branchName
	Push branch to remote repository
		git push origin branchName
	Merge changes in two branches
		git checkout branchName1
		git merge branchName2
	List branches
		git branch


Configurations
	FIle where configs are saved
		.gitconfig e.g: C:\Users\userName\.gitconfig
	Set editor
		git config --global core.editor vscode
	Set merge tool
		git config --global merge.tool meld
		Or vscode
		git config --global  diff.guitool meld

or		
git config --global mergetool.meld.path 'C:\Program Files (x86)\Meld\meld\meld.exe'

	Or set on config file
	https://faun.pub/using-vscode-as-git-mergetool-and-difftool-2e241123abe7 
		# Add this to you gitconfig
# Comment: Start of "Extra Block"
# Comment: This is to unlock VSCode as your git diff and git merge tool
[merge]
    tool = vscode
[mergetool "vscode"]
    cmd = code --wait $MERGED
[diff]
    tool = vscode
[difftool "vscode"]
    cmd = code --wait --diff $LOCAL $REMOTE
# VSCode Difftool
## End of extra block



	Set ignored files
		git config --global core.excludesfile ~/.gitignore
	List configs
		git config --list


Tips | Help
	Show help
		git help
	Show help to specific command
		git help add
		git help commit
		git help anyGitCommand
		git help config
	Show actual branch on linux terminal	
		https://glaucocustodio.github.io/2013/03/15/exibir-branch-atual-em-repositorios-git-no-terminal/
	Link with tips
		https://ohshitgit.com/ 
	Fabio Akita
		https://www.youtube.com/watch?v=6OokP-NE49k&feature=youtu.be&t=101
