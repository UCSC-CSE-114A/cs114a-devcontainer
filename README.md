# CSE 114A Dev Container

A repository for a VS Code Development Container for implementing UCSC CSE 114A programming assignments.
For some general info on making your own devcontainers see here: https://benmatselby.dev/post/vscode-dev-containers/
## Prereq: Make sure docker is installed and running
See here for installation directions: https://docs.docker.com/get-docker/

## Quick start: How to use
The main purpose of a devcontainer is to have a simple way of getting a usable
and predictable development environment regardless of the underlying operating
system.

1. Download the latest release here: https://github.com/UCSC-CSE-114A/cs114a-devcontainer/releases/latest
2. Unzip archive to create a directory `cs114a-devcontainer-<version>`
3. In VS Code, open the CS114A workspace by selecting `File -> Open Workspace` and selecting the file `CS114A.code-workspace` in the new directory.
4. Click on 'Yes I trust the authors' at the popup.
5. At the bottom right, a dialog will ask if you want to install recommended extensions. Click 'Install'
4. You may get a popup that says: "Workspace contains a Dev Container configuration file." Click `Reopen in Container` and then `Continue` to dismiss the warning about a workspace with no folders.
5. Wait while Docker builds the devcontainer.  This could take a while, and might benefit from a good internet connection.
6. Once the container is built, you should be able to get a terminal window on the container, probably with a prompt like `vscode ➜ ~ $`.  If you don't see one, you can try opening one by selecting `Terminal -> New Terminal` from the menu.
7. Now, in the exlporer tab (`View -> Explorer` if you are lost), select the button `Clone Repository` and paste the URL to your assignment repository into the field at the top of the window. Select `/workspaces/cs114a-devcontainer-<version>` as the location to clone into.
8. You should get a popup that says: "Would you like to open the cloned repository, or add it to the current workspace?" Click `Add to Workspace`
9. Now you may get a popup that says: "Working out the project GHC version. This might take a while." This should complete in a few minutes.
10. The cloned repository should now be available in `/workspaces/cs114a-devcontainer-<version>` inside the container and the `cs114a-devcontainer-<version>` directory on the container's host.
## Troubleshooting
#### `ExitFailure (-9) (THIS MAY INDICATE OUT OF MEMORY).`
This probably means that your docker container does not have enough memory allocated to build the Haskell dependencies.  GHC is known to be a memory hog!  You will probably have better luck by increasing the maximum memory Docker is permitted to use by going to Preferences -> Resources and increasing the Memory slider to at least 8GB. 

If your machine has <= 8GB in physical memory, you might be able to get by with less by repeatedly re-running the failed `stack install ...` command until all the packages manage to install.  See [this SO post](https://stackoverflow.com/questions/56496852/problem-building-a-docker-container-with-haskell-stack-how-can-i-ensure-that-ha) for inspiration.

