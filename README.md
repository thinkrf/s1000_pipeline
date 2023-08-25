# S1000 Pipeline Tool

This repoistory is the CI/CD tool working as pipeline to build and release S1000 componentes. Please see below the steps for each component.
## S1000 Frontend Component

### _Pipeline Steps_ 
---------------
#### Tag the Release
- Go to the repository [S1000_Frontend](https://bitbucket.org/thinkrfsoftware/s1000_frontend)
- In the left side, click in **Commits**
- Click in the **commit id** you would like to tag for a release (You can skip this step if the commit you want is tagged already)
- In right side, click in the **+** signal to add a tag for this commit id
- Add a tag in the format 0.0.0 and click in **create**

#### Build and Deploy
- Go to the [S1000 pipeline tool](https://github.com/thinkrf/s1000_pipeline)
- Click in **Actions**
- In the left menu, click in **S1000 Frontend Pipeline**
- Click in **Run workflow** button
- Fill the fields:
    - Release Tag: The s1000 frontend tag that you would like to create a release. Ex: 1.3.0
    - App Environment: options (dev, test, prod)
- Click in **Run workflow**


## S1000 Backend (Agent) Component

### _Pipeline Steps_ 
---------------
#### Tag the Release
- Go to the [S1000_Backend](https://bitbucket.org/thinkrfsoftware/s1000_backend) repository
- Tag a commit, ideally in the format 0.0.0 (see above for more detailed instructions)

#### Build Packages and Installers
- Go to this repository
- Head to **Actions**
- Click **S1000 Backend Pipeline**
- Click **Run workflow**
- Fill the three fields as prompted, and indicate the stability of the package in the dropdown. Be sure version number is in format 0.0.0
    - Note: the Branch option refers to this repository, not the s1000 repository.
- Click **Run workflow**

The pipeline will build for windows and for linux debian/ubuntu. If it has been more than a week since the last run, the windows side will likely take significantly longer than linux (~45 mins) due to a large dependency that needs to build. Otherwise, both will finish in 7-15 mins.

At the end of the run, two "artifacts" will be created (in zip format), one containing the windows installer file and the other containing the debian .deb file. They can be found under **Artifacts** in the **Summary** section of that run of the pipeline. Be sure to download them and save/upload them elsewhere, as the artifacts on Github Actions will dissappear after a few weeks.
