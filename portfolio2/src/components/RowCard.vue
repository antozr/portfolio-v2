<script setup>
const props = defineProps({
  nbCard: Number,
  visible2: Boolean,
  visible3: Boolean
})

let datal = [{ name: 'lo' }, { name: 'la' }, { name: 'lu' }]
</script>

<template>
  <div
    class="projetBox__rowListC"
    :v-show="visible2"
    :class="[visible2 ? 'projetBox__rowListC--start' : 'projetBox__rowListC--end']"
  >
    <p v-for="item in datal">
    {{ item.name }}
    </p>
  </div>
</template>
