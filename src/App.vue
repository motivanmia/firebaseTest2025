<script setup>
import { collection, getDocs } from 'firebase/firestore'
import { db } from '@/lib/firebase'
const testFirestore = async () => {
  try {
    const querySnapshot = await getDocs(collection(db, 'test'))
    debugger
    querySnapshot.forEach(doc => {
      console.log(`${doc.id} =>`, doc.data())
    })
    
  } catch (error) {
    console.error(error);
    
  }
}

testFirestore()

</script>

<template>
  <h1>You did it!</h1>
</template>

<style scoped></style>
