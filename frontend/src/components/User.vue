<template>
  <div>
    <h2>User List</h2>
    <ul>
      <li v-for="user in userList" :key="user.id">
        {{ user.name }} - {{ user.email }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      userList: []
    };
  },
  mounted() {
    this.fetchUserList();
  },
  methods: {
    fetchUserList() {
      fetch("http://0.0.0.0:8000/api/users")
          .then(response => response.json())
          .then(data => {
            this.userList = data;
          })
          .catch(error => {
            console.error("Error fetching user list:", error);
          });
    }
  }
};
</script>