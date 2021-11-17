# Datatable_log

## Datatable editor 仅提交 changed 的内容

Datatable 中的 editor from 会默认提交整行数据，即便只有个别Cell进行了更新

解决方案: 

在editor的构造器中设置参数, formOptions:

```
editor = new $.fn.dataTable.Editor({
  ajax: "Your url",
  table: "#example",
  formOptions: {
    main: {
      submit: 'changed'
      }
   }
})
```

参见:
https://editor.datatables.net/reference/option/formOptions.main

笔记:
Datatable 的 editor 提供了三种更新方式：

`formOptions.main` - Main editor      （这个是表单）

`formOptions.bubble` - Bubble editor

`formOptions.inline` - Inline editor

在设置更新方式的时候，要确定修改的是哪一种
