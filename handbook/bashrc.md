# .bashrc

The `.bashrc` file is a script executed whenever a new terminal session starts in an interactive, non-login shell. It's used to configure the environment, define aliases, set environment variables, and customize the command prompt. This is important, especially when working on data analysis to ensure reproducibility. Even more so when working in CANNON, as certain configurations must be made to allow you to use common tools like Python, Git, and VS Code. 

## Setting up a `.bashrc` file in CANNON:
1. Log into CANNON and open Terminal
2. Navigate to your home directory. There should already be a `.bashrc` file in this directory.
3. Open and edit it with at least the following configurations to allow you to use Python, Git, and VS Code, manage conda environments, and submit VS Code jobs to the CANNON cluster.

```bash
# .bashrc
# Source global definitions
if [ -f /etc/bashrc ]; then
    . /etc/bashrc
fi

function mm() {
    module load vscode
    module load git
    module load python
}

submit_vscode_job() {
    local output
    local p=$1
    local mem=$2
    local cpus=$3
    local time=$4
    echo "sbatch -p $p --mem=$mem -c $cpus --time=$time /n/home##/<your-username>/vscode.job"
    output=$(sbatch -p $p --mem=$mem -c $cpus --time=$time /n/home##/<your-username>/vscode.job)
    export VSCODEJOBID=$(echo "$output" | awk '{print $4}')
    echo "Job submitted with ID: $VSCODEJOBID"
    log_file=~/vscode/logs/vscode-sbatch_${VSCODEJOBID}.out
    echo -n "Waiting for log file: $log_file "
    spin_chars='|/-\'
    while [ ! -f "$log_file" ]; do
        for i in {0..3}; do
            echo -ne "\b${spin_chars:$i:1}"
            sleep 0.2
        done
    done
    echo -e "\b✔ Log file detected, VSCode started!"
    cat "$log_file"
    echo "Job in process."
}
alias launch='submit_vscode_job'

export WORK="/n/dominici_lab/lab"
export CONDA_PKGS_DIRS=/n/dominici_lab/lab/data_processing/conda/pkgs
export CONDA_ENVS_PATH=/n/dominici_lab/lab/data_processing/conda/envs
```

4. Load the modules configured in the `.bashrc` by running your function in Terminal (e.g., `mm`)
5. To submit a VS Code job to the cluster, use the `launch` alias with your desired partition, memory, CPUs, and time:
```bash
   launch short 8G 4 0-02:00
```
   NSAPH members also have access to the `hsph` partition:
```bash
   launch hsph 8G 4 0-02:00
```
   For instructions on setting up your `vscode.job` file, see the [Harvard RC VS Code documentation](https://docs.rc.fas.harvard.edu/kb/vscode-remote-development-via-ssh-or-tunnel/).