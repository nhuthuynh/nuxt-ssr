<template>
  <v-layout column justify-center align-center>
    <v-flex xs12 sm8 md6>
      <div class="text-xs-center">
        <logo />
        <vuetify-logo />
        <ul>
          <li v-for="user in users" :key="user.id">
            <NuxtLink
              :to="`/user/${user.firstName}-${user.lastName}-${user.id}`"
            >
              {{ `${user.firstName} ${user.lastName}` }}
            </NuxtLink>
          </li>
        </ul>
      </div>
    </v-flex>
  </v-layout>
</template>

<script>
import Logo from '~/components/Logo.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'

export default {
  components: {
    Logo,
    VuetifyLogo
  },
  data: function() {
    return {
      users: [
        { firstName: 'Steve', lastName: 'Roger', id: 1 },
        { firstName: 'Thor', lastName: '', id: 2 },
        { firstName: 'Bruce', lastName: 'Banner', id: 3 },
        { firstName: 'Tony', lastName: 'Stark', id: 4 }
      ]
    }
  }
}
</script>
<style>
li {
  list-style-type: none;
}
</style>
