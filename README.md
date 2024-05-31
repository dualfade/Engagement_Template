#### README.md

```zsh
# projects.zsh
# @dualfade --

# create pentest dir struct --
create_projectStruct() {
  dir="$1"
  date=$(/usr/bin/date "+%m%d%Y%M%S")
  PROJECT="$dir-$date"

  if [ -d "$dir" -a ! -h "$dir" ]
  then
    echo "[info] => $dir found; creating project struct"
    cd "$dir" && \
      /bin/mkdir -p {Documents/{sow,roe,scope,vault},Misc,Findings/{recon,post,persist,exploit,enum},Downloads/{bin,src},Sploits/{www,tmp},Reports/{draft,final},Proxy}; \
      /bin/tree -a "${PWD}"

    echo "[info] => Cloning six2dez teplate repo"
    /usr/bin/git clone https://github.com/dualfade/Engagement_Template.git "Documents/vault/$PROJECT"

    echo "[info] Done."

  else
    echo "[Error] => $dir not found or is symlink to $(readlink -f ${dir})."
    echo "[Error] => Usage: mkdir <directory> ; create_projectStruct <directory>"
fi
}
```

![image](https://github.com/dualfade/Engagement_Template/assets/2522757/4ac1dab7-0237-4849-bc47-4e88d086cdd8)
![image](https://github.com/dualfade/Engagement_Template/assets/2522757/a266e8b0-8fd2-4a79-847d-ef691099e9cc)
![image](https://github.com/dualfade/Engagement_Template/assets/2522757/c2cc39e3-4b61-4c1f-a5d6-c172a3bce060)
![image](https://github.com/dualfade/Engagement_Template/assets/2522757/cf91d7ac-13a2-4eac-9106-6d6c53d8a6db)

