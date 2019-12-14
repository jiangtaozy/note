- sqflite count

      final int count = Sqflite.firstIntValue(
        await db.rawQuery('SELECT COUNT(*) FROM time_category')
      );
