#### README.md

- inspired by six2dez; props --
- updated for my needs --

```zsh
# zsh_projects.zsh
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

    echo "[info] => Cloning teplate repo"
    /usr/bin/git clone https://github.com/dualfade/Engagement_Template.git "Documents/vault/$PROJECT"

    echo "[info] Done."

  else
    echo "[Error] => $dir not found or is symlink to $(readlink -f ${dir})."
    echo "[Error] => Usage: mkdir <directory> ; create_projectStruct <directory>"
fi
}
```

- screenshots --

![image](https://github.com/dualfade/Engagement_Template/assets/2522757/4ac1dab7-0237-4849-bc47-4e88d086cdd8)
![image](https://github.com/dualfade/Engagement_Template/assets/2522757/a266e8b0-8fd2-4a79-847d-ef691099e9cc)

