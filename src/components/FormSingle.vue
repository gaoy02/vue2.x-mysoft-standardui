<template>
  <div class="form-single">
    <group>
      <x-input title="字段名称"
               placeholder="预设内容"
               v-model="value1"></x-input>
      <x-input title="字段名称"
               placeholder="预设内容"
               :show-clear="false"
               v-model="value2">
        <i class="icon iconfont icon-information"
           slot="right"
           @click="showAlert"></i>
      </x-input>
      <datetime v-model="value3"
                placeholder="请选择日期"
                :min-year=2000
                :max-year=2016
                format="YYYY年MM月DD日"
                @on-change="change"
                title="日期"
                year-row="{value}年"
                month-row="{value}月"
                day-row="{value}日"
                confirm-text="确定"
                cancel-text="取消"></datetime>
      <x-textarea title="字段名称"
                  placeholder="预设内容"
                  :show-counter="false"
                  :rows="3"
                  v-model="value4"></x-textarea>
      <x-input title="字段名称"
               placeholder="预设内容"
               v-model="value5"></x-input>
    </group>
    <box gap="30px 20px 20px">
      <x-button class="btn-black"
                type="primary"
                action-type="button">按钮</x-button>
    </box>
  </div>
</template>

<script>
import { Alert, PopupPicker, Box, XButton, XTextarea, XInput, Datetime, Group, Cell } from 'vux'

export default {
  name: 'FormSingle',
  components: {
    Alert,
    PopupPicker,
    Box,
    XButton,
    XTextarea,
    XInput,
    Datetime,
    Group,
    Cell
  },
  data () {
    return {
      value1: '',
      value2: '',
      value3: '',
      value4: '',
      value5: '默认值'
    }
  },
  methods: {
    change (value) {
      console.log('change', value)
    },
    showAlert () {
      this.$vux.alert.show({
        title: '标题',
        content: '告知当前状态，信息和解决方法'
      })
    }
  }
}
</script>

<style scoped>
.form-info{
  width: 25px;
}

.icon-information {
  color: #09BB07;
  font-size: 18px;
}

.btn-black {
  background-color: #333;
}

.btn-black:active {
    color: #fff;
    background-color: #555;
}
</style>
