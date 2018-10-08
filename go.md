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

- slice

      // cap tells you the capacity of the underlying array. len tells you how many items are in the array.
      // The slice abstraction in Go is very nice since it will resize the underlying array for you,
      // plus in Go arrays cannot be resized so slices are almost always used instead.
      s := make([]int, 0, 3)
      for i := 0; i < 5; i++ {
        s = append(s, i)
        fmt.Printf("s: %v, cap: %v, len: %v, p: %p\n", s, cap(s), len(s), s)
      }
      // Slices support a “slice” operator with the syntax slice[low:high].
      // For example, this gets a slice of the elements s[2], s[3], and s[4], excluding s[5]
      l := s[2:5]
      fmt.Printf("cap %v, len %v, %p\n", cap(l), len(l), l)
      // s: [0], cap: 3, len: 1, p: 0xc420014480
      // s: [0 1], cap: 3, len: 2, p: 0xc420014480
      // s: [0 1 2], cap: 3, len: 3, p: 0xc420014480
      // s: [0 1 2 3], cap: 6, len: 4, p: 0xc4200182a0
      // s: [0 1 2 3 4], cap: 6, len: 5, p: 0xc4200182a0
      // l: [2 3 4], cap: 4, len: 3, p: 0xc4200182b0

- How to Write Go Code

      - Go programmers typically keep all their Go code in a single workspace.
      - A workspace contains many version control repositories.
      - Each repository contains one or more packages.
      - Each package consists of one or more Go source files in a single directory.
      - The path to a package's directory determines its import path.

- pointer

      package main
      
      import "fmt"
      
      func main() {
        i, j := 42, 2701
      
        // The & operator generates a pointer to its operand.
        p := &i         // point to i
        // The * operator denotes the pointer's underlying value.
        fmt.Println(*p) // read i through the pointer
        *p = 21         // set i through the pointer
        fmt.Println(i)  // see the new value of i
      
        p = &j         // point to j
        *p = *p / 37   // divide j through the pointer
        fmt.Println(j) // see the new value of j
      }

- define multiple name tags in a struct

      type Page struct {
        PageId string                 `bson:"pageId" json:"pageId"`
        Meta   map[string]interface{} `bson:"meta" json:"pageId"`
      }

- install etcd

    $ go get -v go.etcd.io/etcd
    $ $GOPATH/bin/etcd
    $ ./build
    $ ETCDCTL_API=3 ./bin/etcdctl put foo bar
