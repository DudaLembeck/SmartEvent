<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <div class="title">
          <ion-title>SmartEvents</ion-title>
        </div>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Blank</ion-title>
        </ion-toolbar>
      </ion-header>

      <div class="navbar">
        <ion-button @click="$router.push('/eventos')"> EVENTOS </ion-button>
        <ion-button @click="$router.push('/favoritos')"> FAVORITOS </ion-button>
        <ion-button @click="$router.push('/perfil')"> <ion-icon  :icon="person"></ion-icon> </ion-button>
      </div>


      <div id="container">
        <strong>Ache aqui seus maiores Eventos!</strong>
        <p>Navegue pelos eventos dos seus artistas preferidos aqui no SmartEvents</p>
      </div>

      <div class="home-fotos"> 
<ion-card>
  <ion-card-title>
      TAME IMPALA SHOW RIO DE JANEIRO 04/03
    </ion-card-title>
  <ion-card-content>
    <ion-img id="tame-impala"
        src="https://upload.wikimedia.org/wikipedia/commons/1/13/Tame_Impala_at_Flow_Festival_Helsinki_Aug_10_2019_-24.jpg"
      ></ion-img>
 </ion-card-content>
</ion-card>

<ion-card>
  <ion-card-title>
     JENNIE SHOW COACHELLA 05/10
    </ion-card-title>
   <ion-card-content>
      <ion-img id="jennie"
      src="https://capricho.abril.com.br/wp-content/uploads/2025/04/jennie-blackpink-coachella.jpg?quality=85&strip=info&w=1024"
    ></ion-img>
</ion-card-content>
  </ion-card>

  <ion-card>
    <ion-card-title>
      BTS SHOW SÃO PAULO 28/10
    </ion-card-title>
    <ion-card-content>
      <ion-img id="jennie"
      src="https://www.otempo.com.br/adobe/dynamicmedia/deliver/dm-aid--279f9a83-445a-4c67-a938-c3c5bb1ef624/bts-faz-o-comeback-da-decada-na-netflix-com-a-performance-bts-the-comeback-live-arirang.jpg?quality=90&preferwebp=true&width=800&height=600">
    </ion-img>
</ion-card-content>
</ion-card>
</div>
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">

import { IonIcon } from '@ionic/vue'
import {
person, 
} from 'ionicons/icons'

import {
  IonContent,
  IonHeader,
  IonPage,
  IonTitle,
  IonToolbar,
  IonButton,
  IonImg,
  IonCard,
  IonCardContent,
  IonCardTitle
} from "@ionic/vue";
</script>




<style scoped>

ion-card-title {
  display: flex;
  justify-content: center;
  padding-top: 10px;
}

#tame-impala {
  width: 600px;
  transition: all 0.3s;
}
#jennie{
  width: 530px;
  transition: all 0.3s;
}
#tame-impala:hover {
  transform: scale(1.01);
}

#jennie:hover {
  transform: scale(1.01);
}

.home-fotos {
  display: flex;
  align-items: center;
  justify-content: space-around;
  margin-top: 300px;
  width: 100%;
}
.navbar {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  position: absolute;
  margin-top:40px;
}
#container {
  text-align: center;
  position: absolute;
  left: 0;
  right: 0;
  transform: translateY(280%);
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


</style>
