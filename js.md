- Get the full object in console.log(), rather than '[Object]'

      console.dir(myObject,{depth:null})

- Renaming destructured variables in ES6

      var user = {name: 'Italo', age: 10}
      var { name: Username, age: Userage } = user
       
      console.log(Username) // Italo
      console.log(Userage) // 10
