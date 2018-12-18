# VS Code Dvajs/React snippets README

基于DvaJs的自动补全插件,补全命令默认以ad开头，意为Ant Dvajs的简写;

这是一个未完善版本插件，依据现有基于DvaJs的项目结构和语法，补全需要的语法结构，所以，您有什么更好的建议，请通过邮箱联系我：byzhkc3@gmail.com

## Supported languages (file extensions)[支持的语言及文件后缀]
- JavaScript (.js)
- JavaScript React (.jsx)


## Extension Settings(插件设置)

~~因为目前没有发布到vs code的官方应用商店，所以需要您手动安装并启用本插件，步骤如下:~~

~~1,下载邮件中 名为 DvaJs-Snippets 的附件文件 ~~

~~2,打开终端执行 cd .vscode/extensions/ && open .~~

~~3,将解压出来的 DvaJs-Snippets 目录放到 弹出来的 extensions 文件夹下~~

~~4,打开 vs code，选择插件管理（也可以 shift+ command + x 快捷打开）,在DISABLED 选项里找到 DvaJs Snippets 激活并重载即可使用~~


## Basic Methods(基础语法)

| Prefix  | Method                                              |
| ------: | --------------------------------------------------- |
| `cs→`   | `const {  } = this.state;`                          |
| `cp→`   | `const {  } = this.props;`                          |
| `sst→`  | `this.setState({ });`                               |


## Dva模版生成指令 使用方式:指令+tab键，或者 指令 + 回车键;

### `adcc` 快速创建普通组件
```javascript
import React,{ Component } from 'react';
import PropTypes from 'prop-types';

class FileName extends Component{
  render(){
   return (
       <div>
       FileName
       </div>
     );
   }
};

FileName.propTypes = {

};

export default FileName;

```

### `adcpc` 快速创建PureComponent组件
```javascript
import React,{ PureComponent } from 'react';
import PropTypes from 'prop-types';

class FileName extends PureComponent{
  render(){
   return (
       <div>
         FileName
       </div>
     );
   }
};

FileName.propTypes = {

};

export default FileName;

```

### `adcrpc` 快速创建路由页面组件带connect连接
```javascript
import React,{ PureComponent, Fragment } from 'react';
import PropTypes from 'prop-types';
import { connect } from 'dva';
import styles from './FileName.less';

class FileName extends PureComponent{
  render(){
     return (
       <Fragment>
         FileName
       </Fragment>
     );
   }
}

FileName.propTypes = {

};

const mapStateToProps = (state) => {
   const { loading } = state['NAMESPACE'];
   return {
       loading
   };
}

const mapDispatchToProps = {

};

export default connect(mapStateToProps,mapDispatchToProps)(FileName);

```


### `adcnrpc` 快速创建非路由页面组件带connect连接
```javascript
import React,{ PureComponent, Fragment } from 'react';
import { connect } from 'dva-no-router';
import styles from './FileName.less';

class FileName extends PureComponent{
  render(){
       return (
         <Fragment>
           FileName
         </Fragment>
       );
   }
}

FileName.propTypes = {
};

const mapStateToProps = (state) => {
 const { loading } = state['NAMESPACE'];
 return {
     loading
 };
}

const mapDispatchToProps = {

};

export default connect(mapStateToProps,mapDispatchToProps)(FileName);

```

### `admodel` 快速创建model
```javascript
export default {

  namespace: '',

  state: {},

  reducers: {
    save(state, action) {
      return { ...state, ...action.payload };
    },
  },

  effects: {
    *fetch({ payload }, { call, put }) {
      yield put({ type: 'save' });
    },
  },

  subscriptions: {
   init({dispatch}){
      dispatch({ });
   }
  },

};

```

### `admrd` 快速创建model reducers对象
```javascript
reducers: {
    NAME(state, action) {
      return { ...state, ...action.payload };
    },
  }
```

 ### `admrdm` 快速创建model reducers 方法
```javascript
NAME(state, action) {
    return { ...state, ...action.payload };
},
```

### `admrd` 快速创建model reducers 方法
```javascript
reducers: {
    NAME(state, action) {
      return { ...state, ...action.payload };
    },
  }
```

### `admef` 快速创建model effects 对象
```javascript
effects: {
    *NAME({ payload }, { call, put }) {
      yield put({ type: 'save' });
    },
}
```

### `admefm` 快速创建model effects 方法
```javascript
*NAME({ payload }, { call, put }) {
    yield put({ type: 'save' });
},
```

### `adcs` 快速创建services模板
```javascript
import request from '../utils/request';
import qs from 'qs';

export async const getMethods = () => {
  return request('URL');
};
export async const postQuery = (params) => {
  return request('URL', {
    method: 'post',
    data: qs.stringify(params),
  });
}
export async const jsonPost = (params) => {
  return request('URL', {
    method: 'post',
    contentType: 'application/json; charset=UTF-8',
    data: JSON.stringify(params),
  });
}
```

### `adcsfp` 快速创建form post 方法
```javascript
export async const postQuery = (params) => {
    return request('URL', {
        method: 'post',
        data: qs.stringify(params),
    });
}
```

### `adcsfp` 快速创建 coontentType 为json的post请求方法
```javascript
export async const jsonPost = (params) => {
  return request('URL', {
    method: 'post',
    contentType: 'application/json; charset=UTF-8',
    data: JSON.stringify(params),
 });
}
```

### `adcmss` 快速创建model subscriptions 对象
```javascript
subscriptions: {
  setup({ dispatch, history }) {

  },
}
```

### `constructor` 快速创建constructor 方法
```javascript
constructor(props) {
    super(props);
    this.state = {

    };
}
```

-----------------------------------------------------------------------------------------------------------

**Enjoy!**
