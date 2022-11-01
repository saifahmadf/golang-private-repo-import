# How to import private golang repository and use as an import module 

#### using https
```
  - This command must be ran only once in a server to setup github through https
    - git config --global --add url."https://<github-username>:<password>@github.com/".insteadOf "https://github.com/" 
  - go env -w GOPRIVATE=github.com/<github-username>/* 
  - env GIT_TERMINAL_PROMPT=1 go get github.com/<github-username>/<repo-name>
  - go mod tidy
  - env  GIT_TERMINAL_PROMPT=1 go mod vendor
```

#### using private token
```
  - This command must be ran only once in a server to setup github through private token
    - git config --global --add url."https://<github-username>:<private-token>@github.com".insteadOf "https://github.com/"
  - go env -w GOPRIVATE=github.com/<github-username>/* 
  - go get github.com/<github-username>/<repo-name>
  - go mod tidy
  - go mod vendor
```

#### using ssh
```
  - This command must be ran only once in a server to setup github through ssh
    - git config --global --add url."git@github.com:".insteadOf "https://github.com/" 
  - go env -w GOPRIVATE=github.com/<github-username>/* 
  - go get github.com/<github-username>/<repo-name>
  - go mod tidy
  - go mod vendor
```

#### to download specific tag
```
  - go get -d -v github.com/<github-username>/<repo-name>@v0.0.9
```

#### git create a new tag
```
  - git tag -a v0.1.0 -m "to test old tags while importing"
  - git push origin v0.1.0
```


#### docker build with no-cache
```
  - docker-compose up -d --no-deps --build <service_name>
```

#### import private repo through ssh(https://medium.com/swlh/go-modules-with-private-git-repository-3940b6835727)
```
  - This command must be ran only once in a server to setup github through ssh
    - git config --global --add url."git@github.com:".insteadOf "https://github.com/"         
  - Now check ~/.gitconfig file should only have url like given below format
    [url "git@github.com:"]
        insteadOf = https://github.com/
  - go env -w GOPRIVATE=github.com/<github-user-name>
  - go get github.com/<github-user-name>/<repo-name>
  - go mod tidy
  - go mod vendor
```
