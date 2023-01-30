---
date: 2023-01-30 16:04:45
layout: post
---

# gisquest-components(v0.4.0)

## 项目介绍
**组件开发**
使用 vue-cli3 搭建的vue-vuex-router-element 开发模版，结合项目需求,集成常用组件，功能模块
### 系统组件
#### 组件版本:0.4.0
  1. 新增了门户组件用户绑定浙政钉功能
  2. 新增了办件列表组件
#### 1.门户组件  PortalComponent

```
 <PortalComponent ref="portal" :config="config"></PortalComponent>
```
##### 组件属性

config 对象参数
<table>
  <tr>
    <th>参数</th>
    <th>说明</th>
     <th>类型</th>
    <th>具体值</th>
    <th>可选值</th>
    <th>默认值</th>

  </tr>
  <tr>
    <td>subGuids</td>
    <td>应用id</td>
    <td>Array</td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td rowspan="2">layoutConfig</td>
    <td rowspan="2">布局配置参数</td>
    <td rowspan="2">Object</td>
    <td>menuMode:布局类型</td>
    <td>factory:厂字布局/ top:上下布局/ left:左右布局</td>
    <td>factory</td>
  </tr>
  <tr>
    <td></td>
    <td ></td>
    <td></td>
  </tr>
  <tr>
    <td rowspan="2">systemInfo</td>
    <td rowspan="2">应用相关信息</td>
    <td rowspan="2">Object</td>
    <td>logoImage:系统logo</td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>title:系统名称</td>
    <td ></td>
    <td></td>
  </tr>
 <tr>
    <td rowspan="2">menuConfig</td>
    <td rowspan="2">菜单配置</td>
    <td rowspan="2">Object</td>
    <td>shrinkMode:左边菜单收缩方式</td>
    <td>button:按钮点击收缩/scroll:滚动/不传 </td>
    <td>button</td>
  </tr>
  <tr>
    <td>navMode:内容上方页面导航方式</td>
    <td>tabs:tab页签/breadcrumb:面包屑/不传</td>
    <td>tabs</td>
  </tr>
   <tr>
    <td rowspan="2">userInfo</td>
    <td rowspan="2">当前登录用户信息</td>
    <td rowspan="2">Object</td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>urlPathNameBi</td>
    <td>区分是否是bi的设计器页面，处理密码/锁屏等弹窗的显示</td>
    <td>String</td>
    <td></td>
    <td>editor:设计器页面；view:预览页面</td>
    <td></td>
  </tr>
  <tr>
    <td rowspan="6">commonConfig</td>
    <td rowspan="6">账号信息/锁屏/修改用户信息/修改密码等功能是否显示及位置</td>
    <td rowspan="6">Array</td>
    <td>账户信息</td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>锁屏</td>
    <td></td>
    <td></td>
  </tr>
    <tr>
    <td>修改用户信息</td>
    <td></td>
    <td></td>
  </tr>
    <tr>
    <td>修改密码</td>
    <td></td>
    <td></td>
  </tr>
    <tr>
    <td>帮助文档</td>
    <td></td>
    <td></td>
  </tr>
    <tr>
    <td>退出系统</td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td rowspan="3">themeConfig</td>
    <td rowspan="3">主题配色信息</td>
    <td rowspan="3">Object</td>
    <td>lockTheme:锁定配色</td>
    <td>true/false</td>
    <td>false</td>
  </tr>
   <tr>
    <td>themeColors:主题</td>
    <td>default:默认/light:浅色系/dark:深色系/custom:自定义主题色</td>
    <td>default</td>
   </tr>
   <tr>
    <td>color</td>
    <td>色值</td>
    <td></td>
   </tr>
</table>

```
常用配置 参数示例：
 key：固定key，
 text：文字，
 showMode：展现形式   out/inner/""：外部/收起/固定放右边
 icon：图标  iconType为icon时显示
 iconType:图标类型  icon/img
 iconImg: 图片  当iconType为img时显示
 如：
      const commonConfig=[
      {
       key:"account",
       text:"账户信息",
       showMode:"",
       icon:"",
       isShowIcon:true,//帐号图标是否显示
       iconType:'icon', //图标类型   icon-图标  img-图片
       accountName:"name" //账号内容   name-用户名   nickName-账号名字
     },
     {
       key:"lock",
       text:"锁屏",
       showMode:"",
       icon:"",
       iconType:'icon',
     },
     {
       key:"updateUser",
       text:"修改用户信息",
       showMode:"out",
       icon:"",
       iconType:'icon',
     },
     {
       key:"updatePassWord",
       text:"修改密码",
       showMode:"out",
       icon:"",
       iconType:'img',
       iconIm:""
     },
     {
       key:"logout",
       text:"退出系统",
       showMode:"inner",
       icon:"",
       iconType:'icon',
     },
     {
       key:"help",
       text:"帮助文档",
       showMode:"inner",
       icon:"",
       iconType:'icon',
     },
      ]
```

##### 样式类名

|  名称   | 说明  | 可选值  |默认值  |
|  ----  | ----  |  ----  |----  |
|  header-nav-page | 头部class |  ----  |----  |
|  factory-header-nav | 厂字布局头部class |  ----  |----  |
|  systemInfologoImage | 系统图标 |  ----  |----  |
|  systemInfoClassName | 系统名称 |  ----  |----  |

##### 事件名称

|  事件名称   | 说明  | 回调参数  |
|  ----  | ----  |  ----  |
|  handleUnauthorized | 组件内请求时401回调 |  ----  |
|  jumpToLoginPage | 跳转到登录页面 |  ----  |
#### 2.办件列表组件  GisqTaskComponent
compConfig 对象参数

| 参数  | 说明  | 类型  |可选值  |默认值  |
|  ----  | ----  |  ----  |----  |----  |
|  componentName | 办件列表组件的类型 |  string |新收办件:NewTaskComponent；在办办件:OpenedTaskComponent ;应办办件：ActiveAndOpenedTaskComponent;办件查询：QueryTaskComponent;完成办件：EndTaskComponent;环节超期:ExceedTaskComponent；流程超期：ExceedProcessComponent；流程或环节超期：ExceedProcessOrTaskComponent |----  |
|  tableConfig | 列表样式 |string  |默认："";斑马线：'stripe'  |""  |
|  columnSort | 启用标题的排序功能 |  Boolean  |----  |false  |
|  instantQuery | 值变化即时查询:针对查询框，是否值变化就激发查询功能  |  Boolean  |----  |----  |
|  urlPathNameBi | 区分是否是bi的设计器页面,处理设置显示列  |  string  |editor:设计器页面；view:预览页面  |----  |
|  filebagUrl | 档案袋地址ip配置  |  string  |如:http://192.XXX.XXX.XXXX:19012 |----  |
|  tableButtonList | 按钮配置-按钮列表数据  |  Array  |----  |----  |
|  tableColumnList | 列名显示配置-列名配置数据  |  Array  |----  |----  |
|  tableSearchList | 查询条件配置-查询条件配置数据  |  Array  |----  |----  |
##### 事件名称

|  事件名称   | 说明  | 回调参数  |
|  ----  | ----  |  ----  |
|  showColumnSetting | 列名显示配置 |  ----  |
|  showSearchSetting | 查询条件配置 |  ----  |
|  showButtonSetting | 按钮功能配置 |  ----  |
|  refreshTableData | 刷新表格方法|    |
|  getButtonList | 按钮配置确定回调方法  获取按钮列表 |  data：按钮列表数据  |
|  getTableColumnList | 列名显示配置确定回调方法  获取列名配置 |  data：列名配置数据  |
|  getTableSearchList | 查询条件配置确定回调方法  获取查询条件配置 |  data：查询条件配置数据  |
#### 3.档案袋组件  GisqFilebagComponent
compConfig 对象参数

<table>
  <tr>
    <th>参数</th>
    <th>说明</th>
     <th>类型</th>
    <th>具体值</th>
    <th>可选值</th>
    <th>默认值</th>

  </tr>
  <tr>
    <td>subGuid</td>
    <td>应用id</td>
    <td>String</td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td rowspan="2">userInfo</td>
    <td rowspan="2">当前登录用户信息</td>
    <td rowspan="2">Object</td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>operateMode</td>
    <td>操作模式</td>
    <td>String</td>
    <td></td>
    <td>鼠标悬浮:"mouseFloat",右键:"mouseRight"</td>
    <td>mouseFloat</td>
  </tr>
    <tr>
    <td>nodePosition</td>
    <td>节点树位置</td>
    <td>String</td>
    <td></td>
    <td>页面左侧："left"，页面右侧："right"</td>
    <td>left</td>
  </tr>
   <tr>
    <td rowspan="3">lock</td>
    <td rowspan="3">锁屏功能配置</td>
    <td rowspan="3">Object</td>
    <td>isOpen:是否启用</td>
    <td></td>
    <td>true</td>
  </tr>
  <tr>
    <td>tip:提示名</td>
    <td ></td>
    <td>锁屏</td>
  </tr>
   <tr>
    <td>icon:图标</td>
    <td ></td>
    <td></td>
  </tr>
  <tr>
    <td rowspan="3">navigationTitle</td>
    <td rowspan="3">导航标题配置</td>
    <td rowspan="3">Object</td>
    <td>isOpen:是否启用</td>
    <td></td>
    <td>true</td>
  </tr>
  <tr>
    <td>name:名称</td>
    <td ></td>
    <td>业务导航</td>
  </tr>
   <tr>
    <td>icon:图标</td>
    <td ></td>
    <td></td>
  </tr>
 <tr>
    <td rowspan="2">taskTipMessage</td>
    <td rowspan="2">导航下拉配置</td>
    <td rowspan="2"></td>
    <td>isOpen:是否启用</td>
    <td> </td>
    <td>true</td>
  </tr>
  <tr>
    <td>contents:显示内容</td>
    <td>流程名称：processName，办件编号：taskNumber，环节名称：linkName，办件名称：taskName</td>
    <td>["processName","taskNumber"]</td>
  </tr>
  <tr>
    <td>urlPathNameBi</td>
    <td>区分是否是bi的设计器页面，处理密码/锁屏等弹窗的显示</td>
    <td>String</td>
    <td></td>
    <td>editor:设计器页面；view:预览页面</td>
    <td></td>
  </tr>
  <tr>
    <td>filebagButtonList</td>
    <td>档案袋顶部操作按钮列表</td>
    <td>Array</td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
</table>

##### 事件名称

|  事件名称   | 说明  | 回调参数  |
|  ----  | ----  |  ----  |
|  showFilebagButtonSetting | 按钮功能配置 |  ----  |
|  getFilebagButtonList | 按钮配置确定回调方法  获取按钮列表 |  data：按钮列表数据  |
#### 安装教程
1. 安装node环境
2. 安装vue-cli

#### 使用说明

1. git clone http://192.168.1.132/gisquest-middleplatform/gisquest-components.git
2. 切换为公司私服 npm run config:npm
3. 安装依赖 npm install
4. 启动程序 npm run serve
