<template>
  <span class="user">
    <span class="name">{{ props.user.name }}</span>
    <span class="handle">{{ "@" + props.user.handle }}</span>
  </span>
</template>
<script setup>
import { defineProps, onMounted } from "vue";
const props = defineProps(["user"]);

// const props = defineProps({
//   user: {
//     name: {
//       type: String,
//       required: true,
//       default: "missing user name",
//     },
//     handle: {
//       type: String,
//       required: true,
//       default: "missing user handle",
//     },
//   },
// });

// ↑ validación sobre las propiedades del objeto no parecen funcionar
// ↓ alternativa para validar "manualmente" las propiedades de un props objeto
onMounted(() => {
  if (!props.user.name) console.warn("User name is missing");
  else if (typeof props.user.handle !== "string")
    console.warn("User name is not a String");
  if (!props.user.handle) console.warn("User handle is missing");
  else if (typeof props.user.handle !== "string")
    console.warn("User handle is not a String");
});
</script>
<style scoped></style>
