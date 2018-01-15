# linux-unix

Rsync specific files & their folder:
```bash
rsync -avz --include=*/ --include='*rmsd-rgyr-com-sp-tmd-pull.dat.merged*' --exclude=* --prune-empty-dirs * /media/javidi/data/Dropbox/kotted-analysis/
```
