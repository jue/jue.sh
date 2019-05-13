<template>
  <div class="container">
    <Header :toggleClose="toggleClose" @changeMenu="changeMenu"></Header>
    <Intro></Intro>
    <Product/>
    <Service/>
    <Case/>
    <Customer/>
    <Contact @changeMenu="changeMenu"></Contact>
    <contact-form v-show="toggleClose" @changeMenu="changeMenu"></contact-form>
  </div>
</template>
<script>
import Header from '@/components/header.vue'
import Intro from '@/components/intro.vue'
import Product from '@/components/product.vue'
import Service from '@/components/service.vue'
import Case from '@/components/case.vue'
import Customer from '@/components/customer.vue'
import Contact from '@/components/contact.vue'
import ContactForm from '@/components/contactForm.vue'
export default {
  head: {
    title: '觉·上海 JUE.sh  -  上海聚怡信息技术有限公司'
  },
  components: {
    Header,
    Intro,
    Product,
    Service,
    Case,
    Customer,
    Contact,
    ContactForm
  },
  data() {
    return {
      toggleClose: false
    }
  },
  mounted() {
    
  },
  methods: {
    changeMenu() {
      this.toggleClose = !this.toggleClose
    }
  }
}
</script>
