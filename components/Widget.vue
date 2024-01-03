<script lang="ts" setup>
const messages = ref<String[]>([
    "Hi there 👋 How can I help you ?",
])

const showMessage = ref(false)
</script>
<template>
    <div class="whatsapp-widget" @click="showMessage = !showMessage">
        <div class="icon">
            <img src="~/assets/icon.svg" width="65" height="65" alt="whatsapp icon">
        </div>
    </div>
    <div v-if="showMessage" class="message-box">
        <div class="header">

        </div>
        <div class="chat">

            <Message companyName="Webrgy" :messages="messages" />
        </div>
        <div class="action">
            <a aria-label="Chat on WhatsApp" href="https://wa.me/1XXXXXXXXXX" target="_blank">
                chat on whatsapp
            </a> 
        </div>
    </div>
</template>
<style>
.whatsapp-widget .icon {
    cursor: pointer;
    width:3.5rem;
    height: 3.5rem;
    border-radius: 50%;
    overflow: hidden;
    background: #fff;
    position: absolute;
    right: 1rem;
    bottom: 12px;
    z-index: 1;
    box-shadow: rgba(0, 0, 0, 0.3) 0px 4px 12px 0px;
    display: flex;
    justify-content: center;
    align-items: center;
    transition: all 0.5s ease-in-out;
    border: 2px solid transparent
}
.whatsapp-widget:hover {
    border-color:  navy;
    border-spacing: 2px;
}

.message-box {
    width: 20rem;
    height: auto;
    min-height: 20rem;
    background: #fff;
    border-radius: 16px;
    box-shadow: rgba(0, 0, 0, 0.212) 0px 4px 12px 0px;
    position: absolute;
    bottom: 5rem;
    right: 2rem;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    overflow: hidden;
}
.message-box .header {
    background: green;
    width: 100%;
    height: 80px;
}
.message-box .chat {
    flex-grow: 1;
}
.message-box .action {
    background: whitesmoke;
    width: 100%;
    padding: 20px 0;
    display: flex;
    justify-content: center;
    align-items: center;
}

.message-box .action a {
    display:  inline-block;
    background: green;
    height: 20px;
    border-radius: 12px;
    text-align: center;
    color: #fff;
    text-decoration: none;
    padding: 5px 25px;
}
</style>
