<template>
  <section>
    <h1>{{ title }}</h1>   

    <form>
      <input v-model="newText" type="text" placeholder="กรอกข้อความที่ต้องการเพิ่ม" />
      <button type="button" @click="addItem()">เพิ่ม</button>
    </form>
    
    <ul>
      <li v-for="(name, index) in items" :key="index">
        <span>{{ name }}</span>
        <button type="button" @click="deleteItem(index)">ลบ</button>
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  name: 'App',

  data() {
    return {
      title: 'Hello World',
      style: 'color:red',
      items: ['ไปดูหนัง', 'ซื้อไข่ไก่', 'ล้างห้องน้ำ', 'ดู Netflix'],
      newText: ''
    };
  },

  methods: {
    deleteItem(index) {
      this.items.splice(index, 1);
    },

    addItem() {
      this.items.push(this.newText);
      this.newText = '';
    }
  }
};
</script>

<style>
</style>