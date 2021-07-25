# demo-1
vue项目引入elementUI组件库
1.npm安装npm i element-ui -S
（react项目引入:npm i element-react --save）
2.main.js中引入elementUI(完整引入）：
import ElementUI from 'element-ui';
import 'element-ui/lib/theme-chalk/index.css';
Vue.use(ElementUI);
 
 按需引入：
 安装 babel-plugin-component：npm install babel-plugin-component -D
 将 .babelrc 修改为：
 {
  "presets": [["es2015", { "modules": false }]],
  "plugins": [
    [
      "component",
      {
        "libraryName": "element-ui",
        "styleLibraryName": "theme-chalk"
      }
    ]
  ]
}
main.js中引入：
import Vue from 'vue';
import { Button, Select } from 'element-ui';
import App from './App.vue';

Vue.component(Button.name, Button);
Vue.component(Select.name, Select);
/* 或写为
 * Vue.use(Button)
 * Vue.use(Select)
 */

new Vue({
  el: '#app',
  render: h => h(App)
});
最后选择所需组件引入.vue文件中就可以了
