# tong-tools
为新版本大瞳引擎提供的ui工具库，包括了右击菜单等
技术选型采用
Vue+ElementUI
 ![image](http://tong3d.oss-cn-shenzhen.aliyuncs.com/rightClick.png)
# 使用
import Tools from "./tong-tools"
Vue.use(Tools)
# 右击菜单显示为例
菜单对显示的层数没有限制,对v-for循环进行取巧处理，实现类似函数自调用的循环遍历
<tong-popup-menu ref="popupContext" @select="onPopupSelect" :data="popupDatas"></tong-popup-menu>
//显示菜单
this.$refs.popupContext.open(clientX,clientY)
//右击菜单数据
 popupDatas:{
   color:'#aaa',
   children:[
       {
         label:'新增',
         icon:'el-icon-plus',
         callback:null,
         children:[
             {
               label:'JavaScript',
               icon:'iconfont tong-iconjs'
             },
             {
               label:'Glsl',
               icon:'iconfont tong-icons'
             },
             {
               label:'Animation',
               icon:'iconfont tong-iconrunlog'
             },
             {
               label:'Json',
               icon:'iconfont tong-iconjsongeshihua'
             },
             {
               label:'Text',
               icon:'iconfont tong-iconTEXT'
             },
             {
               label: 'Folder',
               icon: 'iconfont tong-iconfolder1'
             }
         ]}
       ,
       {
         label:'删除',
         icon:'el-icon-delete',
         disabled:false
       },
       {
         label:'修改',
         icon:'el-icon-edit',
         disabled:false,
         children:[]
       },
       {
         label:'导入',
         icon:'el-icon-more-outline',
         disabled:false,
         children:[]
       },
       {
         label:'上传',
         icon:'el-icon-upload',
         disabled:false,
         children:[]
       }
   ]
 }
 //选择菜单按钮响应
  onPopupSelect(data,itemCom){
     let selectType=data.label
     if(selectType==="删除"){
       //.....
     }
  }
