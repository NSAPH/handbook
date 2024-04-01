# Efficient Resource Utilization on FASSE

As members of our research group, we share the responsibility to ensure that our computational resources on the Slurm cluster are used efficiently. To promote fair and effective use, please take a moment to review the following guidelines on resource requests and usage.

## Fairshare Policy

Fairshare determines the fraction of system resources allocated to users, assigning scores to users based on their resource usage, and establishing priority levels for users based on these scores. Given that FASSE users come from different groups that have different resource needs, Fairshare aims to establish a method for prioritizing job allocation. This allows users who haven't fully utilized their allocated resources to receive higher priority for their jobs, ensuring that groups that have exceeded their resource allocation do not monopolize the system.

Read more about the Farishare policy [here](https://docs.rc.fas.harvard.edu/kb/fairshare/).

You can check which accounts are associated with your username by running the following command:

```bash 
sacctmgr show assoc user=$USER format=account
```

These are all accounts that you can use to submit jobs. Please use the appropriate account when submitting jobs to the cluster.    
Each lab has a seperate account, and the fairshare is calculated based on the usage of all users in that account.
You can take a look at the lab's fairshare using the following command:

```bash
sshare --account=dominici_lab
```

The fairshare score is a number between 0 and 1. According to FASRC documentation:

- **1.0**: Unused. The Account has not initiated any jobs recently.
- **1.0 > f > 0.5**: Underutilization. The Account is not fully utilizing their allocated Share. 
- **0.5**: Average utilization. The Account is utilizing resources exactly in proportion to their allocated Share.
- **0.5 > f > 0**: Over-utilization. The Account has exceeded their allocated Share. 
- **0**: Exhausted Share. The Account has significantly exceeded their allocated Share. However, if there is no competition for resources, their jobs will still be initiated.

Execute the command below to display a list of the lab's users by their usage.

```bash
sshare --account=dominici_lab --all
```

Please note that the fairshare score recovers with time. This happens with attenuting the raw usage based on 3 days halflife. Thus work done in the last 3 days counts at full cost, work done 6 days ago costs half, work done 9 days ago one fourth, and so on. So, if the lab wants to recover the fairshare, they need to stop submitting job for a couple of days. The exact number of days for reaching a taget value can be computed using the `scalc` command. 

- Enter `scalc` and press enter. This will ask the several questions, please responde it as follows:
  - Select: 3 and press enter. (`3) Projected Time to Reach FairShare Score Assuming No New Jobs`)
  - Enter `dominici_lab` and press enter.
  - Enter traget fairshare (e.g., 0.9)

```{note}
The fairshare score is determined by the accumulated raw usage specific to your lab, rather than the broader NSAPH group. Every Principal Investigator (PI) oversees their respective lab and maintains an independent fairshare account.  
```

## Monitoring the Jobs Efficiency

It is the responsibility of each lab member to ensure their computations are efficient. Your fair share is calculated based on the resources you request (excluding time), not on the resources actually used. Please consider the following scenario:

- A request is made for 250 GB of memory and 24 CPU cores for a duration of 10 hours.
- The application consumes 16 GB of memory and 1 CPU core over 1.5 hours.

Your lab will be charged for:

- 250 GB of Memory, 24 CPU cores for 1.5 hours.

As you can observe, you won't be charged for 10 hours; however, your job is likely to receive lower priority due to its extended duration. In this scenario, requesting resources for 2 hours could result in quicker access compared to a 10-hour request. 

Each partition node has different unit price. Please read the Trackable RESources(TRES) section of the [Fairshare and Job Accounting](https://docs.rc.fas.harvard.edu/kb/fairshare/). 

A direct method to assess the efficiency of a job is to utilize the `seff` command. When the job is completed, run:

```bash
seff <job id>
```

This measures your job's efficiency based on %CPU and %Memory usage compared to the resources requested. Low values indicate an overestimation of needed resources, leading to inefficient resource utilization. This not only depletes resources unnecessarily but also increases wait times for upcoming lab jobs.

Lab moderators can use the `sreport` command to see the usage of the resources by the team in the specific period of time, for example: 

```bash
sreport cluster AccountUtilizationByUser account=dominici_lab Start=2024-03-21 End=2024-03-28
```

## Best Practices in Using FASSE

- **FASSE is for L3 data**
  - Utilize FASSE exclusively for handling sensitive and L3 data. For other computations, such as those involving simulated data, please transition to Cannon.
- **Understanding your needs**
  - Ensure you fully understand the resource requirements of your job before submission.
  - Conduct small-scale tests or pilot runs to assess the CPU and memory requirements. For instance:
    - For bootstrap analysis, initially run 10 iterations instead of 100. Afterwards, utilize the `seff <job-id>` command to evaluate job efficiency.
- **Monitoring your jobs** 
  - To monitor resource usage in real-time for a running job on a computation node, use `ssh node_name` followed by `htop`.
  - Integrate timing into your code for various segments and opt for logging to review code efficiency more effectively.
  - Begin with lower memory allocations if unsure of requirements. Jobs exceeding memory limits will be terminated by SLURM.
  - Profile your code’s CPU and memory usage by initiating an interactive session with salloc or through Open OnDemand, then use ssh login_node and htop for real-time performance monitoring.
    - More resources for R: [Measuring Performance](https://adv-r.hadley.nz/perf-measure.html)
    - More resources for Python: [The Python Profilers](https://docs.python.org/3/library/profile.html)
- **Array jobs**  
  - If running an array-type job (for example bootstrap or multiple models) consider limiting the maximum number of simultaneous jobs. E.g. `--array=1-100%20` will limit to 20 array jobs running at once.
- **Test partitions**
  - Use the `test` partition for testing the code and profiling activities. It does not affect you fairshare. 
- **Communication** 
  - If you anticipate a large or unusual resource request, consider discussing it with the group. This can help ensure that your needs are met without adversely impacting others.
- **Other resources**
  - FASSE (and Cannon) documentation provides a wealth of knowledge on best practices and available resources. Familiarize yourself with it to ensure efficient utilization.
    - Fairshare documentation: https://docs.rc.fas.harvard.edu/kb/fairshare/ 
    - FASSE partitions: https://docs.rc.fas.harvard.edu/kb/fasse/#SLURM_and_Partitions 
    - SLURM: https://docs.rc.fas.harvard.edu/kb/running-jobs/












