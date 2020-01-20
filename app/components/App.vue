<template>
   <Page>
      <ActionBar title="My App" />
      <StackLayout>
         <Button text="GO TO LIST VIEW" @tap="goto('LIST_VIEW')" />
         <TextView class="textView" editable="false" v-model="result" />
         <TextView :text="equation" class="textView" editable="false" />
         <FlexboxLayout height="50%">
            <GridLayout width="80%" rows="*,*,*,*" columns="*,*,*">
               <Button @tap="equation+=7" text="7" row="0" col="0" />
               <Button @tap="equation+=8" text="8" row="0" col="1" />
               <Button @tap="equation+=9" text="9" row="0" col="3" />
               <Button @tap="equation+=4" text="4" row="1" col="0" />
               <Button @tap="equation+=5" text="5" row="1" col="1" />
               <Button @tap="equation+=6" text="6" row="1" col="3" />
               <Button @tap="equation+=1" text="1" row="2" col="0" />
               <Button @tap="equation+=2" text="2" row="2" col="1" />
               <Button @tap="equation+=3" text="3" row="2" col="3" />
               <Button @tap="equation+='.'" text="." row="3" col="0" />
               <Button @tap="equation+=0" text="0" row="3" col="1" />
               <Button @tap="calculateResult" text="=" row="3" col="3" />
            </GridLayout>
            <GridLayout width="20%" rows="*,*,*,*,*" columns="*">
               <Button @tap="equation=result=''" text="DEL" row="0" col="0" />
               <Button @tap="equation+='/'" text="/" row="1" col="0" />
               <Button @tap="equation+='*'" text="*" row="2" col="0" />
               <Button @tap="equation+='+'" text="+" row="3" col="0" />
               <Button @tap="equation+='-'" text="-" row="4" col="0" />
            </GridLayout>
         </FlexboxLayout>
      </StackLayout>
   </Page>
</template>

<script >
import ListView from "./ListView";
export default {
   data() {
      return {
         result: "",
         equation: ""
      };
   },
   methods: {
      calculateResult() {
         let result = "";
         let operators = ["*", "/", "+", "-"];
         let splittedEq = this.equation.split("");
         let operatorsInEq = splittedEq.filter(l => operators.includes(l));
         splittedEq = this.equation
            .split("")
            .map(l => (operators.includes(l) ? "_" : l))
            .join("");
         let equationArray = splittedEq.split("_");
      
         if( splittedEq.includes("*") ){
            
         }


      },
      goto(to) {
         if (to === "LIST_VIEW") {
            this.$navigateTo(ListView);
         }
      }
   }
};
</script>

<style scoped>
ActionBar {
   background-color: #53ba82;
   color: #ffffff;
}

StackLayout {
   padding: 16px;
   background-color: #212121;
}
.textView {
   border: none;
   color: white;
}

button {
   margin: 0;
}

GridLayout {
   grid-gap: 0;
}

.message {
   vertical-align: center;
   text-align: center;
   font-size: 20;
   color: #333333;
}
</style>
