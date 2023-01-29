<script setup lang='ts'>
import { ref } from 'vue';
import Collapse from './Collapse.vue';

const faqs = ref([
    {
        q: "How do I reset my password?",
        a: "You can reset your password by clicking on the 'Forgot Password' link on the login page and following the prompts.",
        open: false
    },
    {
        q: "What is the refund policy?",
        a: "We offer a full refund within 30 days of purchase. After 30 days, we can offer a store credit.",
        open: false
    },
    {
        q: "How can I track my order?",
        a: "You can track your order by logging into your account and viewing the order status.",
        open: false
    },
    {
        q: "What are the system requirements for your software?",
        a: "Our software requires a 64-bit operating system, at least 4GB of RAM, and a 2GHz processor.",
        open: false
    },
    {
        q: "Do you offer bulk discounts?",
        a: "Yes, we offer bulk discounts for orders of 10 or more items. Please contact our sales team for more information.",
        open: false
    }
])
</script>

<template>
    <div style="" class="parent">
        <div class="backdrop">
            <div v-for="faq, idx in faqs" style="border-bottom: 1px solid gray; padding: 1rem 0;">
                <p role="button" tabindex="0" @click="faq.open = !faq.open" style="cursor: pointer;">{{ faq.q }}</p>

                <Collapse v-model="faq.open">
                    {{ faq.a }}
                </Collapse>
            </div>
        </div>
    </div>
</template>

<style>
.parent {
    margin-left: auto;
    margin-right: auto;
    max-width: 400px;
}



p {
    margin: 10px;
}
</style>