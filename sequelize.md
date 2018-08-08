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
