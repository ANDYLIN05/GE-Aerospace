<script setup>
  import { ref } from 'vue';

  const num1 = ref(0);
  const num2 = ref(0);
  const product = ref(null);
  const showButton = ref(true);

  const computeProduct = () =>{
    product.value = num1.value * num2.value;
    showButton.value = false;
  };

  const reset = () =>{
    num1.value = 0;
    num2.value = 0;
    product.value = null;
    showButton.value = true;
  };
</script>

<template>

  <h1> Compute Product </h1>
  
  <!-- Display Number-->
  <div>
    <p>
      Number 1: <input v-model = "num1" type = "number" />
    </p>
    <p>
      Number 2: <input v-model = "num2" tpye = "number" />
    </p>
  </div>

  <!-- Compute Result / Button -->
  <div>
    <button v-if = "showButton" @click = "computeProduct">
      Compute
    </button>
    <p v-else>The product is: {{ product }}</p>
    <button @click = "reset">
      Rest
    </button>
  </div>

  <!--My Image-->
  <div>
    <img src="@/assets/Aerospace.jpeg" alt="Local Image" />
  </div>
</template>
