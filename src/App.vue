<template>
  <div class="p-4">
    <Checkbox :checked="isChecked"
    @updateChecked="handleUpdateChecked"
     />
    <p>La case à cocher est : <span class="text-green-500 mb-4">{{ isChecked ? 'checked' : 'unchecked' }}</span></p>
<!-- ########### ########################-->

    <br>
  <ArticleCard
    :title="articleTitle"
    :content="articleContent"
  />
<!-- ########### ########################-->

  <br>
  <div >
    <CustomCheckbox
      v-model="isCheck"
      label="Accepterrrr les termes et conditions"
      id="terms-checkbox"
    />
    <p v-if="isCheck"> <span class="text-green-500 mb-4">Vous  avez accepté</span> les termes et conditions.</p>
    <p v-else><span class="text-green-500 mb-4">Vous n'avez pas accepté</span> les termes et conditions.</p>
  </div>
  </div>
<!-- ########### ########################-->
  <br>
  <br>
  <!-- <div class="text-green-500 m-6">
    <h1>Composant Parent</h1>
    <ChildComponent 
      message="Bonjour depuis le parent!" 
      @notify="handleNotification" 
    />
    <p>{{ notificationMessage }}</p>
  </div> -->
 
</template>

<script setup>
import { ref } from 'vue'
import Checkbox from './components/Checkbox.vue'
import ArticleCard from './components/ArticleCard.vue';
import CustomCheckbox from './components/CustomCheckbox.vue';
import ChildComponent from './components/ChildComponent.vue';

const isChecked = ref(false);
const isCheck = ref(false);


const articleTitle = 'Titre de l\'article';
const articleContent = 'Contenu de l\'article...';
// État pour stocker le message de notification
const notificationMessage = ref('')

// Méthode pour gérer la notification du composant enfant
const handleNotification = (msg) => {
  notificationMessage.value = msg
}

const handleUpdateChecked = (newValue)=>{
  isChecked.value = newValue;
}


</script>


