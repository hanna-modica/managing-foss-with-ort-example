# Managing Open Source with ORT - Example
This is an example for the lecture at the HTW on managing open source compliance with ORT / ORT Server

## Run this example in ORT Server

### Run ORT Server (Apoapsis)
This part follows the official documentation from [Apoapsis](https://eclipse-apoapsis.github.io/ort-server/docs/admin-guide/getting-started/docker-compose)
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

## Adding rules to ORT Server
To be alerted for e.g. problematic licenses, you can add rules to the file 
located at `ort-server/scripts/compose/config/evaluator.rules.kts`.

This repository contains an example for a rule that does not allow GPL-2.0 at [resources/evaluator.rules.kts](./resources/evaluator.rules.kts)

After editing the rules file in ORT Server, you do not need to restart the docker container.
Just start a new run to verify the rule is effective.

## Tasks for students

1. Find an alternative solution to that in the lecture to eliminate the GPL license.
2. Take care of the vulnerability.
3. Let the reporter generate a Disclosure Document.


## Notice
helloworld example code from https://github.com/fredyrogez/hello-world-npm

License: MIT

Copyright (c) 2021 Fredy Rogez
