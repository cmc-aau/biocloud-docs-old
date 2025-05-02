# Other software
In rare cases, some software is not readily available through conda or biocontainers. Below are some guides on how to run some of them.

## ARB
ARB version 6.0 can be installed through conda from the [bioconda](https://anaconda.org/bioconda/arb-bio) channel, however it is not maintained anymore, and the latest version 7.0 is not available. To run version 7.0 on BioCloud you can run the following in a terminal in either a [virtual desktop](../guides/webportal/apps/virtualdesktop.md) started from the web portal, or through an [interactive shell session](../slurm/jobsubmission.md#graphical-apps-gui) through `salloc` or `srun`, in which case windows will show on your own computer, but everything is running inside a SLURM job on a BioCloud compute node:

```
# create tmp folder for arb in our home folder and create the file
arbtmp="${HOME}/.tmp/arb7"
filename="names_start.dat"
file_path="${arbtmp}/${filename}"
mkdir -p "$arbtmp"
touch "${file_path}"
srun --cpus-per-task 2 --mem 4G --time 0-3:00:00 --x11 apptainer run \
  -B ${file_path}:/opt/arb/lib/nas/names_start.dat \
  -B ~/.Xauthority \
  -B /projects /shared_software/biocloud-software/arb/arb-7.0.sif
```

As mentioned in the [job submission guide](../slurm/jobsubmission.md#graphical-apps-gui) ensure you have X11 forwarding enabled for your SSH connection if you don't run things in a virtual desktop.

## CLC
CLC is licensed to a single machine and is only available through a [virtual desktop](../guides/webportal/apps/virtualdesktop.md) on `axomamma`. You can find it in the menus.

## AlphaFold
[AlphaFold](https://github.com/google-deepmind/alphafold) is quite complex to install and run. It runs through containers, but through a python wrapper script. Copy the SLURM sbatch script from `/shared_software/biocloud-software/alphafold_singularity/sbatch_example.sh` and adjust to suit your needs. `AlphaFold` benefits from GPU-accelerated servers, but can also run on regular CPUs. So submit to the appropriate partition.

## usearch11
`usearch11` is made available on all servers by simply running `usearch11` or `usearch`.
