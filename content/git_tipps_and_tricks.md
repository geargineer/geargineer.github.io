---
tags:
  - git
  - github
draft: "true"
title: "Git and Github: Tipps and Tricks"
date: 2026-03-07T09:57:18.209Z
lastmod: 2026-03-18T10:01:32.764Z
---
# Everything messed up? How to reset your local dir

Something of the below worked ... :-)

```
507  git status  
 508  git rm --cached  
 509  1163  
 510  git rm --cached -r *  
 511  git rm --cached *  
 512  git rm --cached * -r  
 513  ls  
 514  rm -rf config  
 515  cd assets  
 516  ls -lrtg  
 517  cd ..  
 518  git reset -had HEAD  
 519  git reset -hard HEAD  
 520  git reset --hard HEAD  
 521  ls -lrt  
 522  git status  
 523  git reset --hard origin/main  
 524  git reset --hard origin/master  
 525  git fetch --all  
 526  git reset --hard origin/master  
 527  git stash  
 528  git stash pop  
 529  git status  
 530  git clean -df  
 531  git clean -dfx  
 532  git pull  
 533  git remote  
 534  git remot url  
 535  git remote url  
 536  git remote -v  
 537  git remote set-url git@github.com:geargineer/geargineer.github.io.git  
 538  git remote set-url -add git@github.com:geargineer/geargineer.github.io.git 
 539  git remote set-url --add git@github.com:geargineer/geargineer.github.io.git  
 540  git pull  
 541  hugo server  
 542  ls -lrt  
 543  cd themes/  
 544  ls  
 545  cd ..  
 546  history
```

 \
 \
 
