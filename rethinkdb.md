- Create database

      r.dbCreate('classroom');

- Create table

      r.db('classroom').tableCreate('user');

- Insert data

      r.db('classroom').table('user').insert([
        {
          phone: '13888888888',
          password: '123456',
        },
      ])
