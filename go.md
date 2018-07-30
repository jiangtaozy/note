- unable to deduce repository and source type for "golang.org/x/oauth2"

      $mkdir -p $GOPATH/src/golang.org/x/
      $cd $GOPATH/src/golang.org/x/
      $git clone https://github.com/golang/net.git net 
      $go install net 

- go get proxy

       curl -L git.io/cow | bash

       // edit $HOME/.cow/rc
       listen = http://127.0.0.1:7777
       proxy = socks5://127.0.0.1:1080

       // edit ~/.proxy or ~/.bashrc
       export http_proxy=http://127.0.0.1:7777
       export https_proxy=http://127.0.0.1:7777
       source ~/.profile
       echo $http_proxy

       // edit .config/fish/config.fish
       set -x http_proxy http://127.0.0.1:7777
       set -x https_proxy http://127.0.0.1:7777

       cow &

       // edit $USER/.gitconfig
       [https]
         proxy = http://localhost:7777
       [http]
         proxy = http://localhost:7777



- go comments

      /* block comments */
      // line comments

- inspecting the type of variables

      import ( "reflect" )
      reflect.TypeOf(variable)

- get query or body

      query := req.URL.Query() // map[string][]string
      a := query["a"] // []string
      req.ParseForm()
      req.Form // map of key-value pairs
      b := req.FormValue("b") // string
