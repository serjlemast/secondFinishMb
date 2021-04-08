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
};
</script>