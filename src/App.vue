<template>
  <div>
    <!--- Pascal Case 스타일 사용가능 <TheHeader /> --->
    <the-header></the-header>
    <button @click="setSelectComponent('active-goals')">Active Goals</button>
    <button @click="setSelectComponent('manage-goals')">Manage Goals</button>
    <!-- <active-goals v-if="selectComponent === 'active-goals'"></active-goals>
    <manage-goals v-if="selectComponent === 'manage-goals'"></manage-goals> -->
    <keep-alive>
      <component :is="selectComponent"></component>
    </keep-alive>
  </div>
</template>

<script>
import TheHeader from './components/layout/TheHeader.vue';
// import BadgeList from './components/BadgeList.vue';
// import UserInfo from './components/UserInfo.vue';
// import CourseGoals from './components/CourseGoals.vue';
import ActiveGoals from './components/ActiveGoals.vue';
import ManageGoals from './components/ManageGoals.vue';

export default {
  components: {
    TheHeader,
    ActiveGoals,
    ManageGoals,
  },
  data() {
    return {
      selectComponent:  'active-goals',
      activeUser: {
        name: 'Maximilian Schwarzmüller',
        description: 'Site owner and admin',
        role: 'admin',
      },
    };
  },
  methods: {
    setSelectComponent(cmp){
      this.selectComponent = cmp;
    }
  }
};
</script>

<style>
html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
</style>