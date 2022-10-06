- xlsx 处理合并单元格

      const workbook = XLSX.readFile(xlsxPath, {
        cellText: false,
        cellDates: true,
      });
      const worksheet = workbook.Sheets[workbook.SheetNames[0]];
      // 拆分单列合并单元格
      const merges = worksheet['!merges'];
      if(merges && merges.length > 0) {
        for(let i = 0; i < merges.length; i++) {
          const { s, e } = merges[i];
          // 只处理单列合并单元格
          if(s.c === e.c) {
            for(let row = s.r + 1; row <= e.r; row++) {
              const startCell = worksheet[XLSX.utils.encode_cell({r: s.r, c: s.c})];
              worksheet[XLSX.utils.encode_cell({r: row, c: s.c})] = startCell;
            }
          }
        }
      }
