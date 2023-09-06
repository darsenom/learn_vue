<script setup>
import Menubar from 'primevue/menubar';
import InputText from 'primevue/inputtext';
import Button from 'primevue/button'


  import { getAuth, signInWithPopup, GoogleAuthProvider } from 'firebase/auth'
  
  const googleRegister = () => {
    const auth = getAuth()
    const provider = new GoogleAuthProvider()
  
    signInWithPopup(auth, provider)
      .then((userCredential) => {
        const user = userCredential.user
        localStorage.setItem('user', JSON.stringify(user))
      })
      .catch((error) => {
        const errorCode = error.code
        const errorMessage = error.message
        console.log(errorCode, errorMessage)
      })
  }
</script>
<template>
    <Menubar :model="items">
        <template #start>
            <img alt="logo" src="https://www.nicepng.com/png/full/920-9203332_car-logo-png-hot-wheels-car-svg.png"
                height="50" class="mr-2" />
        </template>
        <template #end>
            <span class="p-input-icon-left">
                <i class="pi pi-search" />
                <InputText v-model="value3" type="text" size="large" placeholder="Search" />

            </span>
            <button type="button" class="p-link p-ml-auto" @click="googleRegister">
                <i class="pi pi-user"></i>
              </button>
        </template>

    </Menubar>
</template>
<script setup>
</script>



  
  