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

      // autorun cow after login
      edit ~/.profile
      /home/jemo/cow &



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

- structs

      import "fmt"
      type person struct {
        name string
        age int
      }
      func (p *person) getAge() int {
        return p.age
      }
      func main() {
        s := person{name: "Sean", age: 50}
        fmt.Printf("s: %v\n", s) // s: {Sean 50}
        fmt.Printf("s.getAge(): %d\n", s.getAge()) // s.getAge(): 50
        sp := &s
        fmt.Printf("sp: %v\n", sp) // sp: &{Sean 50}
      }

- json

      import (
        "fmt"
        "encoding/json"
      )
      
      // only fields with a capital first letter are visible
      // to external programs like the JSON Marshaller.
      type person struct {
        Name string `json:"name"`
        Age int `json:"age"`
      }

      func main() {
        data := []byte(`
          {
            "Name": "jemo",
            "Age": 30
          }
        `)
        var p person
        err := json.Unmarshal(data, &p)
        if err != nil {
          panic(err)
        }
        fmt.Printf("p: %v\n", p) // p: {jemo 30}
        s := person{Name: "Sean", Age: 50}
        data, err = json.Marshal(s)
        if err != nil {
          panic(err)
        }
        fmt.Printf("data: %s\n", data) // data: {"name":"Sean","age":50}
      }
