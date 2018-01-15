# linux-unix

1. rsync specific files & their folder:
```bash
rsync -avz --include=*/ --include='*myfilenameishere*' 
--exclude=* --prune-empty-dirs * /media/javidi/data/Dropbox/kotted-analysis/
```
