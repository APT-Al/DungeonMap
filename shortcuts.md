# Put here to some helpful information

# One click commands

## Download all repositories
```
curl -H "Authorization: token <github-token>" -s https://api.github.com/orgs/APT-Al/repos | grep -e 'ssh_url*' | cut -d \" -f 4 | xargs -L1 git clone
```

## Update all repositories 