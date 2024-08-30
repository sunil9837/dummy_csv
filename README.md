# Directory Structure and CSV File Details

The directory structure for storing the CSV files is organized as follows:

```
dummy_csv/
└── app-name1
    ├── repos.csv
    ├── serviceCD.csv
    └── serviceCI.csv
└── app-name2
    ├── repos.csv
    ├── serviceCD.csv
    └── serviceCI.csv
```

Here, `dummy_csv` denotes the code directory where the CSV files are stored for each application.

### Sample CSV Files

**1. repos.csv**

This file contains information about the repositories. The columns are:

- `reponame`: The name of the repository.
- `git_provider`: The Git hosting service (e.g., GitHub, GitLab).
- `url`: The URL of the repository.
- `git_credential`: The credentials used to access the repository (can be null).

**Sample:**

```
reponame,git_provider,url,git_credential
TestDummy,github,https://github.com/laracasts/TestDummy.git,null
```

**2. serviceCD.csv**

This file contains data related to Continuous Deployment (CD) configuration. The columns are:

- `application`: The name of the application.
- `service`: The name of the service.
- `application_env`: The environment in which the service is deployed.
- `desired_replication`: The desired number of replicas.
- `requests_memory_quota`: The memory quota requested for the service.
- `requests_cpu_quota`: The CPU quota requested for the service.
- `limits_cpu_quota`: The maximum CPU quota for the service.
- `limits_memory_quota`: The maximum memory quota for the service.
- `environment_master`: The master environment.
- `target_port`: The target port for the service.
- `app_port`: The application port.
- `readiness_probe_path`: The path for the readiness probe.
- `readiness_probe_port`: The port for the readiness probe.
- `readiness_initial_delay_seconds`: The initial delay before the readiness probe starts.
- `readiness_period_seconds`: The period between readiness probes.
- `readiness_timeout_seconds`: The timeout for the readiness probe.
- `readinesss_failure_threshold`: The failure threshold for the readiness probe.
- `job_template`: The job template used for deployment.

**Sample:**

```
application,service,application_env,desired_replication,requests_memory_quota,requests_cpu_quota,limits_cpu_quota,limits_memory_quota,environment_master,target_port,app_port,readiness_probe_path,readiness_probe_port,readiness_initial_delay_seconds,readiness_period_seconds,readiness_timeout_seconds,readinesss_failure_threshold,job_template
app-name1,test-dummy,dev-test,1,1000,500,2000,1000,dev,8093,9080,'/test/healthCheck',8093,30,5,10,5,app-name1-v2
```

**3. serviceCI.csv**

This file contains data related to Continuous Integration (CI) configuration. The columns are:

- `application`: The name of the application.
- `service`: The name of the service.
- `application_env`: The environment in which the service is built.
- `repo_id`: The ID of the repository.
- `repo_branch`: The branch of the repository used for the service.
- `job_template`: The job template used for CI.
- `dockerfile`: The Dockerfile used for building the service.
- `context`: The context directory for Docker.
- `environment_master`: The master environment.

**Sample:**

```
application,service,application_env,repo_id,repo_branch,job_template,dockerfile,context,environment_master
app-name1,test-dummy,uat-test,TestDummy,master,app-name1-v2,Dockerfile,.,uat
```