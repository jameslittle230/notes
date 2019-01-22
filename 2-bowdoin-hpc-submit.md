Script header:

```bash
#!/bin/bash
#$ -cwd
#$ -j y
#$ -S /bin/bash
#$ -M jlittle@bowdoin.edu -m b -m e
```

Submit a job using the GPU:

```bash
qsub -l gpuk20=1 myscript.sh
```

Interactive login into a GPU system:

```bash
qrsh -l gpuk20=1
```

Connect to the HPC Filesystem from a Mac:

- From the Finder, choose Go/Connect to Server...
- Below "Server Address", type `smb://microwave/hpc-research`
