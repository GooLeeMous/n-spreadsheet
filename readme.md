# n-spreadsheet 更新文档

---
## 更新日志
  

0.0.6
---
可扩展行列可分开配置
> extensible.enableAll  控制扩展  
> extensible.enableRow  控制行扩展  
> extensible.enableCol  控制列扩展

0.0.7
---
增加权限控制
> privileges.editable 控制文档可编辑  
> privileges.dataEdit 控制文档数据可编辑  
> privileges.editable 控制文档格式可编辑  

0.0.8
---
1. 增加导出工具 xlsx-exporter 位于 /utis/excel/xlsx-exporter 
2. 导入工具更名为 xlsx-importer 位于/utis/excel/xlsx-importer 
    - 相关API
    ```javascript
        import ExcelParser from '/utils/excel/xlsx-importer';
        import ExcelExport from '/utils/excel/xlsx-exporter';
        
        const parser = new ExcelParser();
        parser.parse(arrayBuffer).then(data => {
          // do something with data
        });
        
        const exporter = new ExcelExport();
        exporter.setData(data).exportWithBuffer().then(arrayBuffer => {
          // do something with arraybuffer
        });
    ```
3. 增加sheet编辑权限
     > privileges.sheetEdit 控制文档sheet可增删、重命名
4. 修复一些bug

0.0.9
---
1. 修复更改行高、列宽、隐藏行、隐藏列不触发onchange和历史记录的bug
2. spreadsheet对象增加setData方法，用于用户对onchange获取的sheets数据的回设

0.0.10
---
1. 修复因exceljs库无法读取indexedColor表导致的读取indexedColor颜色不正确的问题

0.0.11
---
1. 新功能: 增加自定义菜单功能。
    - 相关API
    ```JavaScript
      new Spreadsheet().setCustomMenu([
              {
                key:'test',
                title:'测试',
                handler:(key, target, sheet)=>{
                  console.log(key,target,sheet)
                  }
              }
            ]);
    ```
