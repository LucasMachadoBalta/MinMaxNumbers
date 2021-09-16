<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title>Min | Max</ion-title>
      </ion-toolbar>
    </ion-header>
    
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Min | Max</ion-title>
        </ion-toolbar>
      </ion-header>
      <ion-content>

      </ion-content>
          <ion-grid id="app">
              <ion-row id="container" class="ion-justify-content-center">
                <ion-col>
                    <strong>Maior e menor números</strong>
                    <ion-input class="input-number" type="number" id="number01" placeholder="digite 1º número" v-model="n1"/>
                    <ion-input class="input-number" type="number" id="number02" placeholder="digite 2º número" v-model="n2"/>
                    <ion-input class="input-number" type="number" id="number03" placeholder="digite 3º número" v-model="n3"/>
                    <ion-input class="input-number" type="number" id="number04" placeholder="digite 4º número" v-model="n4"/>
                    <ion-input class="input-number" type="number" id="number05" placeholder="digite 5º número" v-model="n5"/>            
                    <ion-button @click="listaDeNumeros()">confirma</ion-button>
                    
                    <ion-row class="ion-justify-content-center" id="result">
                              {{ minVal }} <br>
                              {{ maxVal }} 
                    </ion-row>
                </ion-col>
              </ion-row>
              
          </ion-grid>

    </ion-content>
  </ion-page>
</template>

<script lang="ts">

import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonLabel, IonInput, IonGrid, IonButton, IonRow, IonCol } from '@ionic/vue';
import { defineComponent } from 'vue';


export default defineComponent({
  name: 'Home',
  components: {
    IonContent,
    IonHeader,
    IonPage,
    IonTitle,
    IonToolbar,
    //IonLabel, 
    IonInput,
    IonGrid, 
    IonRow, 
    IonCol,
    IonButton
  },
  
  //var app = new Vue({
  //    el: '#app',
  
   data() {
     return {
       lista: [],
         n1: 0,
         n2: 0, 
         n3: 0,
         n4: 0,
         n5: 0,
         minVal: 0,
         maxVal: 0
      }
    },

    methods: {
      listaDeNumeros: function() {
        
          const lista = [this.n1, this.n2, this.n3, this.n4, this.n5];
          alert(lista);
                    
          const maxNum = Math.max(...lista);
          const minNum = Math.min(...lista);
          this.maxVal = maxNum;
          this.minVal = minNum;
        }   
      }
    }
  
);

</script>

<style scoped>
#container {
  text-align: center;
  position: absolute;
  left: 0;
  right: 0;
  top: 50%;
  transform: translateY(-50%);
  
}

.input-number {
  display: block;
  
  padding: 5px;
  margin: 5px;
}

#container strong {
  font-size: 20px;
  line-height: 26px;
}

#container p {
  font-size: 16px;
  line-height: 22px;
  
  color: #8c8c8c;
  
  margin: 0;
}

#container a {
  text-decoration: none;
}

#result {
  margin-top: 10px;
  border: 1px solid lightgray;
  border-radius: 5px;
}
</style>