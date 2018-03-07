## Input

输入框组件。支持使用`v-model`对数据双向绑定，支持一键清空内容。

### 示例

- 基本用法

  使用`v-model`对输入内容双向绑定。

  ```html
  <cube-input v-model="value" ></cube-input>
  ```

  ```javascript
  export default {
    data() {
      return {
        value: ''
      }
    }
  }
  ```

- 多项配置

  支持原生组件的大部分配置，另外可通过`clearable`切换清空按钮以及`pwdEye`设置密码眼睛。

  ```html
  <cube-input
    v-model="value"
    :placeholder="placeholder"
    :type="type"
    :maxlength="maxlength"
    :readonly="readonly"
    :disabled="disabled"
    :autofocus="autofocus"
    :autocomplete="autocomplete"
    :clearable="clearable"
    :pwd-eye="pwdEye"
  ></cube-input>
  ```
  ```javascript
  export default {
    data() {
      return {
        value: '',
        placeholder: '请输入内容',
        type: 'password',
        readonly: true,
        maxlength: 100,
        disabled: true,
        autofocus: true,
        autocomplete: true,
        clearable: false,
        pwdEye: '' // true false ''
      }
    }
  }
  ```

### Props 配置

| 参数 | 说明 | 类型 | 可选值 | 默认值 |
| - | - | - | - | - |
| type | input类型 | String | text/number/password/date | text |
| v-model | 绑定的值 | String | - | 空 |
| disabled | 禁用状态 | Boolean | true/false | false |
| readonly | 只读状态 | Boolean | true/false | false |
| maxlength | 最大输入长度 | Number | - | 60 |
| placeholder | 占位文本 | String | - | 空 |
| autofocus | 自动对焦 | Boolean | true/false | false |
| autocomplete | 自动补全 | Boolean | true/false | false |
| clearable | 是否使用清空按钮 | Boolean | true/false | false |
| pwd-eye | 如果是字符串值且为真，则使用密码眼睛；如果是布尔值，则默认使用密码眼睛，且决定密码是否可见 | String/Boolean | ''/true/false | '' |

### 事件

| 事件名 | 说明 | 参数 |
| - | - | - |
| focus | 输入框聚焦后触发此事件，如果禁用状态，则不触发 | e - 事件对象 |
| blur | 输入框失焦后触发此事件 | e - 事件对象 |
