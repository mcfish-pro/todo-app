<template>
  <div class="input-add">
    <input 
      type="text"
      name="todo"
      v-model="todoContent"
      placeholder="輸入待辦事項"
      @keyup.enter="emitAddTodo"/>
      
      <button @click="emitAddTodo">
          <i class="plus"></i>
        </button>
      </div>
</template>

<script>
import { ref } from "vue";

export default {
    name: "TodoAdd",
    setup(props, context) {
      const todoContent = ref("");

      const emitAddTodo = () => {
        const todo = {
          id: props.tid,
          content: todoContent.value,
          completed: false,
        };
        context.emit("add-todo", todo);
        todoContent.value = "";
      };
      return {
        todoContent,
        emitAddTodo,
      };
    },
};
</script>

<style>
/* 添加框 */
.input-add {
  position: relative;
  display: flex;
  align-items: center;
}

.input-add input {
  padding: 16px 52px 16px 18px;
  border-radius: 48px;
  border: none;
  outline: none;
  box-shadow: 0px 0px 24px rgba(0, 0, 0, 0.08);
  width: 100%;
  font-size: 16px;
  color: #626262;
}

.input-add button {
  width: 46px;
  height: 46px;
  border-radius: 50%;
  /* 以上三個組合能將 + 變成圓型 */

  background: linear-gradient(#C0A5F3, #7F95F7);
  border: none; /* 去邊線 */
  outline: none; /* 去外邊線 */
  color: white;
  position: absolute; /* 使用絕對定位 */
  right: 0px; /* 放置 input 最右邊 */
  cursor: pointer; /* 鼠標設置為小手 */
}

input-add .plus {
  display: block;
  width: 100%;
  height: 100%;
  /* 完成直線與橫線，成為一個加號 */
  background: linear-gradient(#fff, #fff), linear-gradient(#fff, #fff);
  background-size: 50% 2px, 2px 50%;
  background-position: center;
  background-repeat: no-repeat;
}

</style>