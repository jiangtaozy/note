- sequelize bulk upsert

      
      Employee.bulkCreate(dataArray, 
        {
          // Fields to insert (defaults to all fields)
          fields:["id", "name", "address"] ,
          // Fields to update if row key already exists (on duplicate key update)?
          // (only supported by mysql). By default, all fields are updated.
          updateOnDuplicate: ["name"],
        }
      )

- Use sequelize transaction with async / await


    let transaction;    
    
    try {
      // get transaction
      transaction = await sequelize.transaction();
    
      // step 1
      await Model.destroy({where: {id}, transaction});
    
      // step 2
      await Model.create({}, {transaction});
    
      // commit
      await transaction.commit();
    
    } catch (err) {
      // Rollback transaction if any errors were encountered
      await transaction.rollback();
    }

- Ordering

      Subtask.findAll({
        order: [
          ['title', 'DESC'],
          ['name', 'ASC'],
        ],
      })

- Sequelize literal add

      User.update({
        balances: sequelize.literal('balances + ' + change),
      },
      {
        where: {
          id: userId,
          del: false,
        },
        transaction,
        lock: transaction.LOCK.UPDATE, // 加锁
      });
