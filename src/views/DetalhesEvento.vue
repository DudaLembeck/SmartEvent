<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title>{{ evento?.nome || 'Evento' }}</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">{{ evento?.nome }}</ion-title>
        </ion-toolbar>
      </ion-header>
<div class="buttons">
      <ion-button @click="$router.push('/eventos')" style="margin-top: 0; width: 7%; height: 40px;">
        Voltar
      </ion-button>
        <ion-button @click="$router.push('/favoritos')"  style="margin-top: 0; width: 7%; height: 40px;"> FAVORITOS </ion-button>
</div>
      <ion-card>
        <ion-card-content>
              <div id="container" v-if="evento">
                <img :src="evento.img" />

                <h2>{{ evento.nome }}</h2>
                <p>{{ evento.descricao }}</p>
              </div>

        </ion-card-content>
      </ion-card>
      <ion-card>
        <ion-card-content>
          <div id="container" v-if="evento">
                  <h2>Data:
                    <p>{{ evento.data }}</p>
                  </h2>
                  <h2>Local:
                    <p>{{ evento.local }}</p>
                  </h2>
                   <h2>Hrorário:
                    <p>{{ evento.horario }}</p>
                  </h2>
              </div>

              <ion-button @click="toggleFavorito">
                FAVORITAR EVENTO
                  <ion-icon :icon="favorito ? star : starOutline" class="star"></ion-icon>
              </ion-button>
               <ion-button >
          Comprar Ingresso
        </ion-button>
        </ion-card-content>
      </ion-card>
      
       
      

    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonButton, IonCard, IonCardContent } from '@ionic/vue'

import { IonIcon } from '@ionic/vue'
import { starOutline, star } from 'ionicons/icons';

import { ref, computed } from 'vue'
import { useRoute } from 'vue-router'

const route = useRoute()
const id = Number(route.params.id)

// 👇 lista de IDs favoritos
const favoritos = ref<number[]>(
  JSON.parse(localStorage.getItem('favoritos') || '[]')
)

// 👇 verifica se esse evento é favorito
const favorito = computed(() => {
  return favoritos.value.includes(id)
})

// 👇 adiciona/remove
const toggleFavorito = () => {
  if (favorito.value) {
    favoritos.value = favoritos.value.filter(f => f !== id)
  } else {
    favoritos.value.push(id)
  }

  localStorage.setItem('favoritos', JSON.stringify(favoritos.value))
}


const listaEventos = 
[
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
];



const evento = computed(() => {
  return listaEventos.find(e => e.id === id)
})
</script>

<style scoped>

.buttons {
  display: flex;
}


.star {
  margin-left: 40px;
  font-size: 20px;
  transition: transform 0.2s ease, color 0.2s ease;
}

.star.active {
  color: gold;
  transform: scale(1.3);
}

.star {
  margin-left: 10px;
}
ion-button {
  display: flex;
  margin-top: 30px;
  margin-bottom: 0;
  padding: 0;
  height: 60px;
  justify-content: center;
}

#container {
  padding: 16px;
  text-align: center;
}

img {
  margin-bottom: 40px;
  width: 500px;
  border-radius: 10px;
}

h2 {
  font-size: 30px;
  margin-bottom: 10px;
  font-weight: 600;
  color: aliceblue;
}

p {
  font-size: 16px;
  color: #a8a8a8;
}
</style>