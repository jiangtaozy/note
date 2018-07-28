- set innerHTML img max-width

      import { css } from 'glamor';
      css.insert('img { max-width: 100%}')

- create-react-app Environment Variables


      npm start: process.env.NODE_ENV == 'development'
      npm build: process.env.NODE_ENV == 'production',
      npm test: process.env.NODE_ENV == 'test',

      // There is also a special built-in environment variable called NODE_ENV.
      // You can read it from process.env.NODE_ENV.  When you run npm start,
      // it is always equal to 'development', when you run npm test it is always
      // equal to 'test', and when you run npm run build to make a production
      // bundle, it is always equal to 'production'.
