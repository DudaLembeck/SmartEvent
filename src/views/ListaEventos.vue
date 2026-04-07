<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title>SmartEvents</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Blank</ion-title>
        </ion-toolbar>
      </ion-header>
        <ion-button @click="$router.push('/home')" style="margin-top: 20px; width: 7%; height: 40px; margin-left: 20px;">
        Voltar
      </ion-button>

      <div id="container">
       <h1>Eventos Disponíveis</h1>
      </div>

       <ion-card>
          <ion-card-content >
            <ion-list >
             
                <ion-item class="item-evento" 
                  v-for="eventos in listaEventos" 
                  :key="eventos.id"
                  :router-link="'/eventos/' + eventos.id"
                  button>
                   <img :src="eventos.img" />
                  <ion-label>{{ eventos.nome }}</ion-label>
                  <p>{{ eventos.descricao }}</p>
                  <ion-button @click="`/eventos/${eventos.id}`">
                    VER EVENTO
                  </ion-button>
                </ion-item>


           </ion-list>
          
          </ion-card-content>
        </ion-card>

    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { 
  IonContent,
  IonButton,
  IonLabel,
  IonList,
  IonItem,
  IonCardContent, 
  IonHeader, 
  IonPage, IonTitle, 
  IonToolbar,
  IonCard,  
  
  } from '@ionic/vue';


const listaEventos = 
[
   { 
  id: 1, 
  nome: 'BTS WORLD TOUR | ARIRANG',
  data: "28/10",
  descricao: "O BTS, acrônimo de Bangtan Sonyeondan ou “Beyond the Scene”, é uma boyband sul-coreana indicada ao GRAMMY que vem conquistando os corações de milhões de fãs ao redor do mundo desde sua estreia, em junho de 2013. Os integrantes do BTS são RM, Jin, SUGA, j-hope, Jimin, V e Jung Kook. Reconhecido por sua música autêntica e autoral, performances de altíssimo nível e pela forma como se conectam com seus fãs, o grupo se consolidou como um ícone pop do século XXI, quebrando inúmeros recordes globais.",
  img: "https://i0.wp.com/popasiaticojpg.com/wp-content/uploads/2026/03/BTS-ARIRANG.png?fit=810%2C400&ssl=1"

  },
  { 
    id: 2, 
    nome: 'JENIIE | COACHELLA',
    data: "04/06",
    descricao: "Prepare-se para uma apresentação inesquecível com Jennie no Coachella. A artista sul-coreana sobe ao palco trazendo um show eletrizante, que combina grandes sucessos, performances intensas e uma produção visual de alto nível.",
    img: "https://s2-g1.glbimg.com/tXbh-eGh_h9rkT8TNH-ljK8aokA=/3186x0/filters:format(jpeg)/https://i.s3.glbimg.com/v1/AUTH_59edd422c0c84a879bd37670ae4f538a/internal_photos/bs/2025/Q/E/mj07vtSRqPEpDOuJBoIg/ap25104160533128.jpg"

  },
  { 
    id: 3, 
    nome: 'BRUNO MARS | RIO DE JANEIRO',
    data: "04/06",
    descricao: "Conhecido por suas performances envolventes, Bruno Mars promete um show completo, com banda ao vivo, coreografias impecáveis e uma conexão única com o público. No repertório, não vão faltar hits como “Uptown Funk”, “24K Magic” e “Just the Way You Are”, garantindo momentos de muita animação e emoção.",
    img: "https://santaportal.com.br/wp/wp-content/uploads/2023/09/Bruno-Mars.jpg"

  }
];

</script>

<style scoped>



ion-label {
  width: 100%;
}

ion-button {
  margin-bottom: 20px;
  margin-top: 20px;
}
.item-evento {
  margin-bottom: 20px;
}

.item-evento::part(native) {
  display: flex;
  flex-direction: column; /* AGORA SIM fica embaixo */
  align-items: center;
  text-align: center;
}

img {
  margin-top: 10px;
  width: 100%;
  max-width: 300px;
  border-radius: 10px;
}

ion-card {
  margin-top: 130px;
}
#container {
  text-align: center;
  position: absolute;
  left: 0;
  right: 0;
  transform: translateY(40%);
}
h1 {
  font-weight: 600;
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
