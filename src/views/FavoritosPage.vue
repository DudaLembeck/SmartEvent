<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title>Eventos Favoritos</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Blank</ion-title>
        </ion-toolbar>
      </ion-header> 
      <ion-button @click="$router.push('/home')"> HOME </ion-button>
       <ion-button @click="$router.push('/eventos')"> EVENTOS </ion-button>
        
     
     <div id="container">
        <strong>Aqui Estão seus Eventos Favoritados!</strong>
      </div>
<ion-card>
      <ion-list>
  <ion-item v-for="evento in eventosFavoritos" :key="evento.id">
    <ion-label>{{ evento.nome }}</ion-label>
  </ion-item>
</ion-list>
</ion-card>
    </ion-content>

  </ion-page>
</template>

<script setup lang="ts">
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonList, IonItem, IonLabel, IonCard, IonButton } from '@ionic/vue';


import { ref, computed } from 'vue'


const listaEventos =  ref([
  { 
  id: 1, 
  nome: 'BTS WORLD TOUR | ARIRANG',
  data: "28/10",
  descricao: "O BTS, acrônimo de Bangtan Sonyeondan ou “Beyond the Scene”, é uma boyband sul-coreana indicada ao GRAMMY que vem conquistando os corações de milhões de fãs ao redor do mundo desde sua estreia, em junho de 2013. Os integrantes do BTS são RM, Jin, SUGA, j-hope, Jimin, V e Jung Kook. Reconhecido por sua música autêntica e autoral, performances de altíssimo nível e pela forma como se conectam com seus fãs, o grupo se consolidou como um ícone pop do século XXI, quebrando inúmeros recordes globais.",
  img: "https://i0.wp.com/popasiaticojpg.com/wp-content/uploads/2026/03/BTS-ARIRANG.png?fit=810%2C400&ssl=1",
  local: "Estádio MorumBIS - São Paulo",
  horario: "20hrs"

  },
  { 
    id: 2, 
    nome: 'JENIIE | COACHELLA',
    data: "04/06",
    descricao: "Prepare-se para uma apresentação inesquecível com Jennie no Coachella. A artista sul-coreana sobe ao palco trazendo um show eletrizante, que combina grandes sucessos, performances intensas e uma produção visual de alto nível.",
    img: "https://s2-g1.glbimg.com/tXbh-eGh_h9rkT8TNH-ljK8aokA=/3186x0/filters:format(jpeg)/https://i.s3.glbimg.com/v1/AUTH_59edd422c0c84a879bd37670ae4f538a/internal_photos/bs/2025/Q/E/mj07vtSRqPEpDOuJBoIg/ap25104160533128.jpg",
    local:"Empire Polo Club - Califórnia",
    horario: "21hrs"

  },
  { 
    id: 3, 
    nome: 'BRUNO MARS | RIO DE JANEIRO',
    data: "04/06",
    descricao: "Conhecido por suas performances envolventes, Bruno Mars promete um show completo, com banda ao vivo, coreografias impecáveis e uma conexão única com o público. No repertório, não vão faltar hits como “Uptown Funk”, “24K Magic” e “Just the Way You Are”, garantindo momentos de muita animação e emoção.",
    img: "https://santaportal.com.br/wp/wp-content/uploads/2023/09/Bruno-Mars.jpg",
    local: "Estádio Nilton Santos - Rio de Janeiro",
    horario: "18hrs"

  }
]);

// pega favoritos
const favoritos = ref<number[]>(
  JSON.parse(localStorage.getItem('favoritos') || '[]')
)

// filtra os eventos favoritos
const eventosFavoritos = computed(() => {
  return listaEventos.value.filter(e => favoritos.value.includes(e.id))
})
</script>

<style scoped>

ion-card {
  margin-top: 200px;
}

#container {
  text-align: center;
  position: absolute;
  left: 0;
  right: 0;
  margin-top: 100px;
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
</style>
