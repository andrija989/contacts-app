import Vue from 'vue'
import VueRouter from 'vue-router'
import App from './App.vue'

Vue.use(VueRouter)

import ContactForm from '@/components/ContactForm'
import ContactList from '@/components/ContactList'
import SingleContact from '@/components/SingleContact'

import AppContacts from '@/components/AppContacts'
import AppUsers from '@/components/AppUsers'

const routes = [
  // { path: '/contacts', component: ContactList },
  // { path: '/add-contact', component: ContactForm },
  // { path: '/contact/:id', component: SingleContact }
  {
    path: '/',
    redirect: '/contacts'
  },
  {
    path: '/users',
    component: AppUsers
  },
  {
    path: '/contacts',
    component: AppContacts,
    redirect: 'contacts/list',
    children: [
      {
        path: 'list',
        component: ContactList
      },
      {
        path: 'add-contact',
        component: ContactForm
      },
      {
        path: ':id',
        component: SingleContact
      }
    ]
  },
  {
    path: '*',
    redirect: '/contacts/list'
  }
]

const router = new VueRouter({
  routes: routes,
  mode: 'history',
  linkActiveClass: 'test'
})

Vue.config.productionTip = false

new Vue({
  router: router,
  render: h => h(App),
}).$mount('#app')
