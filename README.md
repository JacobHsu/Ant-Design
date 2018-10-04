# Ant-Design

[Ant Design of Vue](https://vuecomponent.github.io/ant-design-vue/docs/vue/introduce/)    
[Vue CLI 3](https://cli.vuejs.org/)  Standard Tooling for Vue.js Development  

# Install

`yarn global add @vue/cli`  
`vue -V`  
`mkdir vue-demo`  
`cd vue-demo`  
`vue create ant-design-vue-worldcup`  

`$ cd ant-design-vue-worldcup`  
`$ yarn serve`  

[快速上手](https://vuecomponent.github.io/ant-design-vue/docs/vue/getting-started-cn/)  
`$ yarn add ant-design-vue`   

[Button](https://vuecomponent.github.io/ant-design-vue/components/button-cn/)  
App.vue components\HelloWorld.vue  

[Bootstrap](http://getbootstrap.com/)  
`$ yarn add bootstrap`   

[Navbar](http://getbootstrap.com/docs/4.1/components/navbar/)  
[Checkbox](https://vuecomponent.github.io/ant-design-vue/components/checkbox-cn/)  
[Radio](https://vuecomponent.github.io/ant-design-vue/components/radio-cn/)  
[Table](https://vuecomponent.github.io/ant-design-vue/components/table-cn/#components-table-demo-basic-usage) 
[Badge](https://vuecomponent.github.io/ant-design-vue/components/badge-cn/)  
[dropdown](https://vuecomponent.github.io/ant-design-vue/components/dropdown-cn/)  
[message](https://vuecomponent.github.io/ant-design-vue/components/message-cn/)  

`$ yarn add reqwest`   

## Deploying

Vue CLI [GitHub Pages](https://cli.vuejs.org/zh/guide/deployment.html#cors)  
Set correct baseUrl in `vue.config.js`    

`$ yarn run build`  將生成的 dist 文件 移動至根目錄  
`git subtree push --prefix dist origin gh-pages` 



### Tools

chrome [JSON Formatter](https://chrome.google.com/webstore/detail/json-formatter/bcjindcccaagfpapjjmafapmmgkkhgoa/related?hl=zh-TW)  
chrome [Vue.js devtools](https://chrome.google.com/webstore/detail/vuejs-devtools/nhdogjmejiglipccpnnnanhbledajbpd)  

### Notes

vue [Lifecycle Diagram](https://vuejs.org/v2/guide/instance.html#Lifecycle-Diagram)    
`dataIndex` 默認的無法滿足使用 `scopedSlots`  