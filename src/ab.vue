Exemple avec un champ de texte :
<template>
  <input v-model="message" placeholder="Entrez un message" class="border p-2 rounded">
  <p class="mt-2">Vous avez écrit : {{ message }}</p>
</template>

<script setup>
import { ref } from 'vue';

const message = ref('');
</script>
Autres usages courants :
•	Checkbox :
vue
Copier le code
<template>
  <input type="checkbox" v-model="isChecked" class="mr-2">
  <label>Coché : {{ isChecked }}</label>
</template>

<script setup>
import { ref } from 'vue';

const isChecked = ref(false);
</script>
•	Radio :
vue
Copier le code
<template>
  <input type="radio" value="Option 1" v-model="selectedOption" class="mr-2"> Option 1
  <input type="radio" value="Option 2" v-model="selectedOption" class="ml-4 mr-2"> Option 2
  <p class="mt-2">Option sélectionnée : {{ selectedOption }}</p>
</template>

<script setup>
import { ref } from 'vue';

const selectedOption = ref('');
</script>
•	Select :
vue
Copier le code
<template>
  <select v-model="selectedValue" class="border p-2 rounded">
    <option value="A">Option A</option>
    <option value="B">Option B</option>
  </select>
  <p class="mt-2">Valeur sélectionnée : {{ selectedValue }}</p>
</template>

<script setup>
import { ref } from 'vue';

const selectedValue = ref('');
</script>
