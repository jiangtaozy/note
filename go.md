- unable to deduce repository and source type for "golang.org/x/oauth2"

      $mkdir -p $GOPATH/src/golang.org/x/
      $cd $GOPATH/src/golang.org/x/
      $git clone https://github.com/golang/net.git net 
      $go install net 

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
