<template>
   <Page>
      <ActionBar title="List View" />
      <Label text="Hello"/>
      <!-- <ListView if="show" for="item in items">
         <v-template>
            <Label :text="item.text" />
         </v-template>
      </ListView> -->
   </Page>
</template>

<script>
export default {
   name: "ListView",
   data() {
      return {
         show: false,
         items: [
            { id: 1, text: "Anik" },
            { id: 2, text: "Rasel" },
            { id: 3, text: "Ratul" }
         ]
      };
   }
};
</script>