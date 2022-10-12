<template>
  <div class="tweet">
    <ProfileImage :image="props.tweet.user.image" />

    <div class="body">
      <div class="top">
        <User :user="props.tweet.user" />
        <Timestamp :timestamp="props.tweet.timestamp" />
      </div>

      <!-- Contenido del mensaje pasado con slot en vez de prop  -->
      <Message>{{ props.tweet.message }}</Message>
      <Actions />
    </div>

    <i class="fas fa-ellipsis-h"></i>
  </div>
</template>

<script setup>
import { defineProps } from "vue";
import ProfileImage from "./ProfileImage.vue";
import User from "./User.vue";
import Timestamp from "./Timestamp.vue";
import Message from "./Message.vue";
import Actions from "./Actions.vue";
const props = defineProps(["tweet"]);
</script>

<style scoped>
a {
  color: #42b983;
}
</style>
