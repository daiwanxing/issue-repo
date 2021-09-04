<script lang="tsx">
import { defineComponent, ref } from "vue";
import { Switch as ASwitch } from "ant-design-vue"

export default defineComponent({
  components: {
    ASwitch
  },
  setup () {
    const checked = ref(false);
    return function () {
      return <div>
        <ASwitch 
          checked={checked.value}
          // 此处check的类型被推断成了any
          onChange={function (check) {
            checked.value = check;
          }}
        ></ASwitch>
      </div>
    }
  }
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
