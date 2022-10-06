- 处理换行符问题

      const csv = XLSX.utils.sheet_to_csv(worksheet, {
          RS: '|',
          blankrows: false,
          dateNF: 'yyyy-mm-dd',
      });
      const ctlStr = `
          OPTIONS (skip=${importSkip}, rows=200)
          LOAD DATA
          CHARACTERSET UTF8
          INFILE '${csvPath}' "str '|'"
          BADFILE '${badPath}'
          INTO TABLE MAINTAIN_BILL
          APPEND
          FIELDS TERMINATED BY ',' OPTIONALLY ENCLOSED BY '"'
          TRAILING NULLCOLS(
            SERIAL_NUMBER,
          )
      `

      data_xlsx.to_csv(csv_path, encoding="utf-8", index=False, header=False, line_terminator="|")
      ctl_str = f"""
          OPTIONS (skip={import_skip}, rows=200)
          LOAD DATA
          CHARACTERSET UTF8
          INFILE '{csv_path}' "str '|'"
          BADFILE '{bad_path}'
          APPEND
          INTO TABLE ZJTTPOWER.{table_name}
          FIELDS TERMINATED BY ','
          OPTIONALLY ENCLOSED BY '"'
          TRAILING NULLCOLS(
            {import_columns}
          )
      """

