- How to set NODE_ENV to production/development in OS X

      // in package.json:
      {
        ...
        "scripts": {
          "start": "NODE_ENV=production node ./app"
        }
        ...
      }
      
      // in app.js
      const env = process.env.NODE_ENV;
