- orderBy

      knex('users').orderBy('email')
      Outputs:
      select * from `users` order by `email` asc

      knex('users').orderBy('name', 'desc')
      Outputs:
      select * from `users` order by `name` desc

      Multiple Columns:

      knex('users').orderBy(['email', { column: 'age', order: 'desc' }])
      Outputs:
      select * from `users` order by `email` asc, `age` desc

      knex('users').orderBy([{ column: 'email' }, { column: 'age', order: 'desc' }])
      Outputs:
      select * from `users` order by `email` asc, `age` desc

- update

      knex('books')
        .where('published_date', '<', 2000)
        .update({
          status: 'archived',
          thisKeyIsSkipped: undefined
        })
      Outputs:
      update `books` set `status` = 'archived' where `published_date` < 2000

      // Returns [1] in "mysql", "sqlite", "oracle"; [] in "postgresql" unless the 'returning' parameter is set.
      knex('books').update('title', 'Slaughterhouse Five')
      Outputs:
      update `books` set `title` = 'Slaughterhouse Five'

      // Returns [ { id: 42, title: "The Hitchhiker's Guide to the Galaxy" } ]
      knex('books')
        .where({ id: 42 })
        .update({ title: "The Hitchhiker's Guide to the Galaxy" }, ['id', 'title'])
      Outputs:
      update `books` set `title` = 'The Hitchhiker\'s Guide to the Galaxy' where `id` = 42


- and where

      const subquery = knex('users')
        .where('votes', '>', 100)
        .andWhere('status', 'active')
        .orWhere('name', 'John')
        .select('id');
