<template>
  <div>
    <theHeader />
    <!-- <badge-list></badge-list>
    <user-info
      :full-name="activeUser.name"
      :info-text="activeUser.description"
      :role="activeUser.role"
    ></user-info>

    <course-goals>
      <template #default="slotProps">
        <h2>{{ slotProps.item }}</h2>
        <p>{{ slotProps['another-prop'] }}</p>
      </template>
    </course-goals> -->
    <button @click="setSelectedComponent('manage-goals')">Manage goals</button>
    <button @click="setSelectedComponent('active-goals')">Active goals</button>
    <!-- <active-goals v-if="selectedGoals === 'active-goals'"> </active-goals>
    <manage-goals v-if="selectedGoals === 'manage-goals'"> </manage-goals> -->
    <keep-alive>
      <component :is="selectedGoals"> </component>
    </keep-alive>
  </div>
</template>

<script>
import theHeader from './components/TheHeader.vue';
// import BadgeList from './components/BadgeList.vue';
// import UserInfo from './components/UserInfo.vue';
// import CourseGoals from './components/CourseGoals.vue';
import ActiveGoals from './components/ActiveGoals.vue';
import ManageGoals from './components/ManageGoals.vue';

export default {
  components: {
    theHeader,
    ActiveGoals,
    ManageGoals,
  },
  data() {
    return {
      selectedGoals: 'active-goals',
      activeUser: {
        name: 'Maximilian Schwarzmüller',
        description: 'Site owner and admin',
        role: 'admin',
      },
    };
  },
  methods: {
    setSelectedComponent(cmp) {
      this.selectedGoals = cmp;
    },
  },
};
</script>

<style scoped>
html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
</style>
