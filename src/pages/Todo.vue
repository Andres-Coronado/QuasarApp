<template>
  <q-page class="bg-grey-3 column">
    <q-list class="bg-white" separator bordered>
      <q-item v-for="task in tasks" :key="task.title" @click="task.done =! task.done" v-ripple clickable>
        <q-item-section avatar>
          <q-checkbox v-model="task.done" color="primary" class="no-pointer-events"/>
        </q-item-section>
        <q-item-section v-if="task.done" >
          <q-item-label>{{ task.title }}</q-item-label>
        </q-item-section>
        <q-item-section v-if="task.done" side >
          <q-btn flat round color="primary" icon="delete" dense />
        </q-item-section>
      </q-item>
    </q-list>
  </q-page>
</template>
<script>
export default {
  data () {
    return {
      tasks: [
        {
          title: 'Get bannanas',
          done: falsehttp://localhost:8080/#/
        },
        {
          title: 'Eat bananas',
          done: true
        },
        {
          title: 'poo bananas',
          done: false
        }
      ]
    }
  }
}
</script>
<style lang="scss">
  .done{
    .q-item__label{
      text-decoration: line-through;
      color: #bbb;
    }
  }
</style>
