- Get the full object in console.log(), rather than '[Object]'

      console.dir(myObject,{depth:null})

- Renaming destructured variables in ES6

      var user = {name: 'Italo', age: 10}
      var { name: Username, age: Userage } = user
       
      console.log(Username) // Italo
      console.log(Userage) // 10

- Default values in destructuring

      var {a = 10, b = 5} = {a: 3};

      console.log(a); // 3
      console.log(b); // 5

- Deep nested object destructuring

      let obj = {
        p: [
          'Hello',
          { y: 'World' }
        ]
      };
      
      let { p, p: [x, { y }] } = obj;
      x // "Hello"
      y // "World"
      p // ["Hello", {y: "World"}]

- Move array

      let arr = [ { a: 0 }, { a: 1 }, { a: 2 } ];
      let index = 1;
      let item = arr[index];
      // remove an element from index, return an array containing the deleted elements
      arr.splice(index, 1);
      // adds one or more elements to the beginning of an array
      // and returns the new length of the array.
      arr.unshift(item);

- Transform a moment object into a date object

      moment().toDate();

- Get a moment object

      //This parses the given date using the given format. Returns a moment object.
      m = moment("2013-03-01", "YYYY-MM-DD")

- Moment format

      const now = moment().format('YYYY-MM-DD HH:mm:ss');

- Check if object is array

      Array.isArray(obj)

- Get Query String Parameters with JavaScript

      var urlParams = new URLSearchParams(window.location.search);
      console.log(urlParams.has('post')); // true
      console.log(urlParams.get('action')); // "edit"
      console.log(urlParams.getAll('action')); // ["edit"]
      console.log(urlParams.toString()); // "?post=1234&action=edit"
      console.log(urlParams.append('active', '1')); // "?post=1234&action=edit&active=1"

- Optional destructuring

      const where = {
        del: false,
        ...(phone && {phone}),
        ...(version && {version}),
        ...(company && {company: { [Op.like]: `%${company}%` }}),
        ...(name && {name: { [Op.like]: `%${name}%` }}),
      };
      const array = [
        ...(isTrue ? ['data'] : []),
      ];

- Get front location

      window.location.origin

- Destructuring default value null bug

      let obj = { a: null }
      let { a = {} } = obj
      console.log('a: ', a) // a: null not a: {}

- Keep two decimals

      10.989.toFixed(2) // '10.99'
      Math.round(5/2) // 3
      Math.ceil(7/2) // 4
      Math.floor(7/2) // 3

- Object keys

      let obj = { a: 1, b: 2 }
      Object.keys(obj) // [ 'a', 'b' ]

- 2 decimal float

      Math.round(number * 100) / 100

- Phone number regex pattern

      /^1[3-9](\d{9})$/

- Password regex pattern

      /^[a-zA-Z0-9!@#$%^&*]{6,16}$/
      // 特殊字符<202c> 13836885581‬
