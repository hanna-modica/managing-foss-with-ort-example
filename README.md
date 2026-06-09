# Managing Open Source with ORT - Example
This is an example for the lecture at the HTW on managing open source compliance with ORT / ORT Server

## Instructions

### Run ORT Server (Apoapsis)
1. Download and install [Docker](https://docs.docker.com/get-started/) on your machine.
2. Clone [ORT Server](https://github.com/eclipse-apoapsis/ort-server).
3. Run `docker compose up` in the ORT Server directory.
4. Open in your browser [http://localhost:8082](http://localhost:8082), to access the ORT Server UI.
5. Log in as user `admin` and password `admin`.

### Setup your repository for a run
1. In the UI, click on "Add organization +" and create it with a name of your choice.
2. (optional step for private repos): 
Add to your organization a secret called `git-user` with your username 
and `git-token` with your [github token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens)
with access to your private repository. Afterwards, add to your organization .
an infrastructure service, with the url being [https://github.com](https://github.com).
For username and password select the secrets you generated earlier, leave the rest,
and hit create.
3. In the same way as (1) add a product to your organization.
4. In the same ways add a repository, where the url is the clone url.


### Start a run
1. After creating a repository, you are directly forwarded to starting a run.
2. If you want to scan a branch other then the default branch, enter a branch name in the revision.
3. The rest do not change and click the create button at the bottom

### Examine the results
Hint: The initial run can take quite some time, but consecutive runs will use cached results and be faster.

1. After the run is finished, you can see in the run overview already, if there
   are issues, rules violations or security vulnerabilities.
2. You can also access the `scan-report-web-app.html` under "Reports" > "Other" to get some visualized details on the run results.

### Add some rules
To be alerted for e.g. problematic licenses, you can add rules to the file 
located at `ort-server/scripts/compose/config/evaluator.rules.kts`.
There is an example file you can copy in the resources folder.

After editing the rules file, you do not need to restart the docker, but you
need to start a new run.


## Notice
helloworld example code from https://github.com/fredyrogez/hello-world-npm

License: MIT

Copyright (c) 2021 Fredy Rogez
