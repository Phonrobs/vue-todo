<template>
   <v-app>
     <v-app-bar app color="teal">
       <v-toolbar-title>Vue Todo App</v-toolbar-title>
     </v-app-bar>

     <v-content>
       <v-container>
         <v-card>
           <v-card-text>
             <v-text-field v-model="newText" solo label="กรอกข้อความที่ต้องการเพิ่ม" append-outer-icon="mdi-plus" @click:append-outer="addItem()"></v-text-field>
           </v-card-text>

           <v-list>
             <v-list-item v-for="(item, index) in items" :key="index">
               <v-list-item-action>
                 <v-icon>mdi-file-settings-outline</v-icon>
               </v-list-item-action>
               <v-list-item-content>
                 <v-list-item-title>{{ item }}</v-list-item-title>
               </v-list-item-content>
               <v-list-item-action>
                 <v-btn @click="deleteItem(index)" color="red">ลบ</v-btn>
               </v-list-item-action>
             </v-list-item>
           </v-list>
         </v-card>
       </v-container>
     </v-content>
   </v-app>
</template>

<script>
export default {
  name: 'App',
 
  data: () => ({
    items: ['Apple', 'Banana', 'Mango'],
    newText: ''
  }),

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
