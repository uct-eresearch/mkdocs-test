# How to contribute to eResearch Docs on MkDocs 

The steps below describe how to install and set up all the software necessary to contribute to the UCT eResearch Documentation site using GitHub. The site is built with [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/).
If you have any suggestions to improve this file, please create an Issue or email [eresearch@uct.ac.za](mailto:eresearch@uct.ac.za). If the change is minor, you are welcome to contribute suggested updates to this file via a GitHub pull request. 


### 1. Create a GitHub account
- https://github.com/  

### 2. Install `git` locally
- Read more and download: https://git-scm.com/ 

### 3. Set `git` up locally (using the commandline interface, shell, or terminal)
- Read more: https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup  
- `git config --global user.name "John Doe"`
- `git config --global user.email johndoe@example.com`

### 4. Set up git/GitHub authentication with SSH key (using the commandline interface, shell, or terminal)
- Read more: https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent  
- `ssh-keygen -t ed25519 -C "your_email@example.com"`
- Depending on your operating system, type the following command to capture the key in your clipboard:
   - Windows: `clip < ~/.ssh/id_ed25519.pub`
   - Mac: `pbcopy < ~/.ssh/id_ed25519.pub`
   - Linux: `cat ~/.ssh/id_ed25519.pub`
      - Then select and copy the contents of the id_ed25519.pub file displayed in the terminal to your clipboard

- Add the SSH key to Github by following the instructions at https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account
   - In the upper-right corner of any page on GitHub, click your profile picture, then click  Settings.
   - In the "Access" section of the sidebar, click  SSH and GPG keys.
   - Click New SSH key or Add SSH key.
   - In the "Title" field, add a descriptive label for the new key. For example, if you're using a personal laptop, you might call this key "Personal laptop".
   - Select the type of key, either authentication or signing. For more information about commit signing, see [About commit signature verification](https://docs.github.com/en/authentication/managing-commit-signature-verification/about-commit-signature-verification).
   - In the "Key" field, paste your public key.
   - Click Add SSH key.
   - If prompted, confirm access to your account on GitHub. For more information, see [Sudo mode](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/sudo-mode).

### 5. Install an editor of your choice e.g. VS Code
- https://code.visualstudio.com/download  

### 6. Install Python locally
- https://www.python.org/downloads/  

### 7. Check if  `pip` is installed locally or install `pip` locally if the command below gives an error (using the commandline interface, shell, or terminal)
- Read more: https://pip.pypa.io/en/stable/installation/
- To check if `pip` is installed, run the following command on the command prompt `pip --version` 

### 8. Create a virtual Python environment where `mkdocs` and other relevant software can be installed (using the commandline interface, shell, or terminal)
- Read more: https://docs.python.org/3/library/venv.html  
- Windows: `python -m venv C:\path\to\new\virtual\environment` 
- Linux/Mac: `python -m venv /path/to/new/virtual/environment`

### 9. Activate the newly created virtual environment (using the commandline interface, shell, or terminal)
- Read more: https://www.w3schools.com/python/python_virtualenv.asp
- Windows: `path\to\new\virtual\environment\Scripts\activate`
- Linux: `source path/to/new/virtual/environment/bin/activate`
   
### 9. Install Material for MkDocs (__ensure you have activated the newly created environment before commencing with the installation__) (using the commandline interface, shell, or terminal)
- Read more: https://t.pxeger.com/mkdocs-material/getting-started/
- `pip install mkdocs-material`

### 10. Install GLightBox plugin for MkDocs (using the commandline interface, shell, or terminal)
- This plugin allows for image zooming in documentation
- Read more: https://blueswen.github.io/mkdocs-glightbox/
- `pip install mkdocs-glightbox`
 
### 11. Fork the UCT eResearch Documentation repo on GitHub
- Our repo: https://github.com/uct-eresearch/mkdocs-test  

### 12. Clone the UCT eResearch Documentation repo to your local computer (using the commandline interface, shell, or terminal)
- `git clone [your repository using ssh]`
   
### 13. Change directories to the newly cloned repository (using the commandline interface, shell, or terminal)
- cd [name of the cloned repository]

### 15. Add the remote upstream repository (using the commandline interface, shell, or terminal)
- Read more: https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/configuring-a-remote-repository-for-a-fork
- `git remote add upstream git@github.com:uct-eresearch/mkdocs-test.git`

### 16.  Build and serve the site locally (using the commandline interface, shell, or terminal)
- Read more: https://www.mkdocs.org/user-guide/cli/
- `mkdocs serve`
- to run this process in the background, you can run `mkdocs serve &`

### 17. View the site on your localhost
- The output from the previous command should include a link to view the site on localhost, typically `http://127.0.0.1:8000/[name of repo]`
   
### 18. To contribute changes to the upstream repo follow the relevant step below

####    a) Contributing major changes 

- If you would like to contribute a more significant change (e.g. correct outdated or erroneous content, add missing or new content), start here 
- Create an Issue on the GitHub repository to suggest your edits/additions
   - __IMPORTANT__: Create one issue per suggested edit. If you want to suggest multiple edits, create an issue for each edit to ensure they can be discussed and tracked separately.
   - Read more: https://docs.github.com/en/issues/tracking-your-work-with-issues/configuring-issues/quickstart  
   - To create an `Issue`, click on the link: https://github.com/uct-eresearch/mkdocs-test/issues
   - Click on the green `New Issue` button in the upper right corner
   - Give the Issue a short but descriptive title
   - Describe your suggested change (1 change per issue)
   - We can discuss the suggested change to ensure the documentation flow makes sense and documentation isn’t duplicated. This may mean that another section of the documentation has to be restructured or changed to make the suggested changes fit logically within the documentation structure.
   - Once consensus has been reached about the change, or the documentation owner has given the go-ahead, follow the next steps. 

####    b) Contributing approved/minor changes 

- Make changes to the local repository in VSCode or another IDE
- Open the folder that contains the repo files
- Make edits and save locally
- Please make sure the changes render as you expected them to and nothing else is broken.
     - If you are already running `mkdocs server`, the changes will automatically be rendered on the localhost – no need to rebuild.
     - Alternatively, run `mkdocs server` again from the command line interface. 
     - If you are happy with your changes proceed to the next step 

- Stage edits on the local git repo (using the commandline interface, shell, or terminal) 
     - Read more: https://git-scm.com/docs/git-add
     - `git add –A`   \[-A if you want to stage all changes\] 

- Commit changes (using the commandline interface, shell, or terminal)
   - Read more: https://git-scm.com/docs/git-commit 
   - `git commit –m “Git commit message”`

- Push changes to the remote ‘origin’ repository (this is the fork in your own GitHub account) (using the commandline interface, shell, or terminal)
   - Read more: https://docs.github.com/en/get-started/using-git/pushing-commits-to-a-remote-repository 
   - `git push origin main` (if `main` is the branch you want to push to. Please note this workflow is currently under review and will be updated to ensure we follow best practices)

- In GitHub, create a Pull Request
  - Read more: https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request  
  - The documentation team will review the Pull Request before merging into the main documentation. 
