<script setup>
  import { collection, getDocs } from 'firebase/firestore'
  import { db } from '@/lib/firebase'
  const testFirestore = async () => {
    try {
      const querySnapshot = await getDocs(collection(db, 'messages'))
      querySnapshot.forEach((doc) => {
        console.log(`${doc.id} =>`, doc.data())
      })
    } catch (error) {
      console.error(error)
    }
  }

  testFirestore()
</script>

<template>
  <h1>Firestore Chat</h1>
  <nav>
    <RouterLink to="/">Home</RouterLink>
    <br />
    <RouterLink to="/chat">Chat</RouterLink>
  </nav>
</template>

<style scoped></style>
