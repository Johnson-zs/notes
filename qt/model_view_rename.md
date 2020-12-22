# Qt Model/View 实现文件重命名功能分析

以 dde-file-manager 中文件重命名功能进行分析，结合 Qt 源码分析文件重命名功能的实现。

## 功能需求解析

1. 重命名唤起方式
   - 右键菜单
   - 选中已选择的文件
   - 快捷键 F2
2. 重命名生效方式
   - Enter
   - 鼠标点击空白处
3. 视图
   - 列表视图
   - 图标视图

![rename_ways](./resources/model_view_rename/rename_ways.gif)



## 参考资料

- [model-view-programming](https://doc.qt.io/qt-5/model-view-programming.html)