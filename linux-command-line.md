__advanced rsync__

1. rsync specific files & their folder:
```bash
rsync -avz --include=*/ --include='*myfilenameishere*' 
--exclude=* --prune-empty-dirs * /media/javidi/data/Dropbox/kotted-analysis/
```

__get rid of dead jobs that are still on qstat__
2. Force kill all jobs of a user after cluster shut down:
```bash
qselect -u javidi | xargs qdel -p
```
