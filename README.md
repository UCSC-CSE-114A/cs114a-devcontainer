# CSE 114A Dev Container

A repository for a VS Code Development Container for implementing UCSC CSE 114A programming assignments.
For some general info on making your own devcontainers see here: https://benmatselby.dev/post/vscode-dev-containers/

# How to use
The main purpose of a devcontainer is to have a simple way of getting a usable
and predictable development environment regardless of the underlying operating
system.

1. Download the latest release here: https://github.com/UCSC-CSE-114A/cs114a-devcontainer/releases/latest
2. Unzip archive to create a directory `cs114a-devcontainer-<version>`
3. In VS Code, open the CS114A workspace by selecting `File -> Open Workspace` and selecting the file CS114A.code-workspace in the new directory.
4. You should get a popup that says: "Workspace contains a Dev Container configuration file." Click `Reopen in Container` and then `Continue` to dismiss the warning about a workspace with no folders.
5. Wait while Docker builds the devcontainer.  This could take a while, and might benefit from a good internet connection.
6. Once the container is built, you should be able to get a terminal window on the container, probably with a prompt like `vscode ➜ ~ $`.  If you don't see one, you can try opening one by selecting `Terminal -> New Terminal` from the menu.
7. Now, in the exlporer tab (`View -> Explorer` if you are lost), select the button `Clone Repository` and paste the URL to your assignment repository into the field at the top of the window. Select `/home/vscode` as the location to clone into.
8. You should get a popup that says: "Would you like to open the cloned repository, or add it to the current workspace?" Click `Add to Workspace`
9. Now you may get a popup that says: "Working out the project GHC version. This might take a while." This should complete in a few minutes.
10. The cloned repository should now be available in `/home/vscode`. 
