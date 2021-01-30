<template>
  <div id="task">
    <form>
      <input v-model="tarefa" type="text" placeholder="Tarefa de hoje?" />
      <button @click="addItem">Adicionar</button>
    </form>
  </div>
</template>


<script>
export default {
    name: 'Task',
    data(){
        return{
            tarefa: '',
            tarefas: [],
        }    
        },

        methods: {
            addItem(){
                if(this.tarefa !== ''){
                    this.tarefas.push({
                        text: this.tarefa,
                        key: Date.now(),
                    });
                }else{
                    alert('DIgite uma tarefa!');
                    return;
                }
                this.tarefa = '';
            }
        }
}

</script>

<style scoped>
#task {
  max-width: 700px;
  background: #fff;
  border-radius: 4px;
  padding: 20px;
  margin: 20px auto;
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.3);
}

form {
  margin-top: 30px;
  display: flex;
  flex-direction: row;
}

form button {
  cursor: pointer;
  background: #0f5959;
  border: 0;
  border-radius: 4px;
  margin-left: 10px;
  padding: 0 15px;
  display: flex;
  justify-content: center;
  align-items: center;
  color: #fff;
}

input {
  flex: 1;
  border: 1px solid #eee;
  padding: 6px 10px;
  border-radius: 4px;
  font-size: 14px;
  outline: none;
}
</style>