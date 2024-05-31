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

    echo "[info] => Cloning template repo"
    /usr/bin/git clone https://github.com/dualfade/Engagement_Template.git "Documents/vault/$PROJECT"

    echo "[info] Done."

  else
    echo "[Error] => $dir not found or is symlink to $(readlink -f ${dir})."
    echo "[Error] => Usage: mkdir <directory> ; create_projectStruct <directory>"
fi
}
```

- screenshots --

![image](https://github.com/dualfade/Engagement_Template/assets/2522757/7e6b3f49-9791-4fd0-abc2-42a2e147f26c)
![image](https://github.com/dualfade/Engagement_Template/assets/2522757/5f1f3f93-2afc-422a-9e27-abe9ac158f02)


