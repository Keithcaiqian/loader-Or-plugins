1. lodash 处理各种数据的已封装的方法

2. vue-quill-editor vue的富文本

3. vue-table-with-tree-grid vue的树形表格组件

4. nprogress 进度条
   用法示例 
// 引入nprogress及样式
import NProgress from 'nprogress'
import 'nprogress/nprogress.css'

axios.defaults.baseURL = 'http://127.0.0.1:8888/api/private/v1/'
// 添加请求拦截器
axios.interceptors.request.use(function (config) {
  // 进度条开始
  NProgress.start()
  config.headers.Authorization = window.sessionStorage.getItem('token')
  return config
}
axios.interceptors.response.use(function (config) {
  // 进度条结束
  NProgress.done()
  return config
})
