<template>
  <div class="root"></div>
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