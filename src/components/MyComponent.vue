<template>
  <div class="root">
    <h1>{{ titleName }}</h1>
    <label>
      <input type="serch" v-model="searchName" />
    </label>

    <h2>Search:{{ serchFeild }}</h2>

    <h4>Всего имен: {{ searchName.length }}</h4>
    <ul>
      <li v-for="(value, index) in userNames" :key="index">
        {{ value.name }}
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: "MyComponent",
  data() {
    return {
      titleName: "Поиск имен",
      searchName: "",
      serchFeild: "",
      userNames: [
        { name: "misha" },
        { name: "kesha" },
        { name: "nasky" },
        { name: "nasty" },
      ],
    };
  },
  watch: {
    searchName: function (val) {
      if (!val || val.length === 0) {
        console.log("watch: name is empty");
        this.serchFeild = "";
        return;
      }
      var names = this.userNames.filter(function (user) {
        var name = user.name;
        return name.search(val) != -1;
      });
      if (names.length == 0) {
        console.log("watch: name is empty");
        this.serchFeild = "";
        return;
      }
      this.serchFeild = names;
    },
  },
};
</script>