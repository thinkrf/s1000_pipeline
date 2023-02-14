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

#### Buidl and Deploy
- Go to the [S1000 pipeline tool](https://github.com/thinkrf/s1000_pipeline)
- Click in **Actions**
- In the left menu, click in **S1000 Frontend Pipeline**
- Click in **Run workflow** button
- Fill the fields:
--- Release Tag: The s1000 frontend tag that you would like to create a release. Ex: 1.3.0
--- App Environment: options (dev, test, prod)
- Click in **Run workflow**

