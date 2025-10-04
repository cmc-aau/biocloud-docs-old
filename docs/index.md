# Introduction
Welcome to the documentation website for the BioCloud HPC at the section of biotechnology at Aalborg University. Here you will find everything you need to use the cluster for large scale bioinformatic workflows and other things that require more compute resources and storage than normal computers have. The current setup consists of data center servers with dual socket AMD Epyc CPU's of various sizes (from 2022) with a total of **1848 vCPUs** and **12 TB RAM**, all connected to a **2.3 PB+ storage** cluster ([Ceph](https://ceph.com/)).

The cluster is a shared resource for more than a hundred users, so to effectively manage the compute resources and allow many simultaneous users to run jobs concurrently in a completely isolated manner the cluster is set up with the [SLURM workload manager](https://slurm.schedmd.com/archive/slurm-23.02.6/overview.html).

To gain access you must first ask an administrator to allow you to login using your AAU email, and then you will be able to use the cluster resources through either the web portal, or by submitting SLURM batch jobs through a remote shell on a login node.

## New documentation website
**This is the documentation website for the old cluster only**. The old cluster is planned to be shut down some time in October/November 2025, and then all compute nodes will be moved to the new cluster, but until then we will be running two separate clusters, and the documentation for the new cluster is available at [https://cmc-aau.github.io/biocloud-docs/](https://cmc-aau.github.io/biocloud-docs/).
