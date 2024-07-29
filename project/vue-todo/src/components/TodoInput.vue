<template>
    <!-- vue template 은 단일 루트를 가져야 한다 -->
    <div class="inputBox shadow">
        <input type="text" v-model="newTodoItem" placeholder="Type what you have to do" v-on:keyup.enter="addTodo">
        <span class="addContainer" v-on:click="addTodo">
            <i class="addBtn fas fa-plus" aria-hidden="true"></i>
        </span>
    </div>
</template>

<script>
export default {
    data() {
        return {
            newTodoItem: ''
        }
    },

    methods: {
        addTodo() {
      if (this.newTodoItem !== "") {
        var value = this.newTodoItem && this.newTodoItem.trim();
        this.$emit('addTodo', value);
        this.clearInput();
      }
    },
        clearInput() {
            this.newTodoItem = '';
        }
    }
}
</script>

<style scoped>
input:focus {
    /* 인풋박스 선 스타일 지정 */
    outline: none;
}

.inputBox {
    background: white;
    height: 50px;
    line-height: 50px;
    /* 인풋박스 둥근 테두리 속성 */
    border-radius: 5px;
}

.inputBox input {
    border-style: none;
    font-size: 0.9rem;
}

.addContainer {
    /* 추가 버튼 표시 위치 정의 */
    float: right;
    background: linear-gradient(to right, #6478FB, #8763FB);
    display: block;
    width: 3rem;
    border-radius: 0 5px 5px 0;
}

.addBtn {
    color: white;
    /* 추가 아이콘 수직 정렬 정의 */
    vertical-align: middle;
}
</style>