<script lang="ts" setup>
const props = defineProps({
    messages: {
        type: Array<String>,
        required: true
    },
    companyName: {
        type: String,
        default: "" 
    }
})

const time = computed(() => new Date().getHours() + ":" + new Date().getMinutes());
</script>
<template>
    <div class="WhatsappChat__MessageContainer-quaMo quaMo">
    <div
      style="opacity: 1"
      class="WhatsappChat__Message-sc-1wqac52-4 kAZgZq"
      v-for="(item, i) in messages"
      :key="i"
    >
      <div class="WhatsappChat__Author-sc-1wqac52-3 bMIBDo">
        {{ companyName }}
      </div>
      <div class="WhatsappChat__Text-sc-1wqac52-2 iSpIQi">
        {{ item }}
      </div>
      <div class="WhatsappChat__Time-sc-1wqac52-5 cqCDVm">
        {{ time }}
      </div>
    </div>
  </div>
</template>
