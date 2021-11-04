<template>
  <section>
    <base-card>
      <template v-slot:header>
        <h3>{{ fullName }}</h3>
        <base-badge :type="role" :caption="role.toUpperCase()"></base-badge>
      </template>
      <p>{{ infoText }}</p>
    </base-card>
  </section>
</template>

<script>
import BaseBadge from './BaseBadge.vue';

export default {
  components: {
    BaseBadge,
  },
  props: ['fullName', 'infoText', 'role'],
};
</script>
