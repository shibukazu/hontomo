<template>
  <div id="sidebar">
    <ul class="nav flex-column">
      <li class="nav-item">
        <router-link
          :to="{ name: 'Top' }"
          class="nav-link disable-router-link-active"
          >ほんとも</router-link
        >
      </li>
      <li class="nav-item">
        <router-link :to="{ name: 'Top' }" class="nav-link">
          <font-awesome-icon icon="home" class="fa-lg" />
          <span>トップ</span>
        </router-link>
      </li>
      <li class="nav-item">
        <router-link :to="{ name: 'Shelf' }" class="nav-link">
          <font-awesome-icon icon="book" class="fa-lg" />
          <span>本棚</span>
        </router-link>
      </li>
    </ul>
    <hr />
    <router-link :to="{ name: 'MyLists' }" class="nav-link">
      <font-awesome-icon icon="list" class="fa-lg" /><span>リスト一覧</span>
    </router-link>
    <ul class="nav flex-column">
      <li v-for="l in list.slice(0, 3)" v-bind:key="l.id" class="nav-item">
        <router-link
          :to="{ name: 'List', params: { id: l.id } }"
          class="nav-link"
        >
          <font-awesome-icon
            icon="heart"
            class="fa-lg"
            v-show="l.id === 'favorite'"
          />
          <span>{{ l.name }}</span>
        </router-link>
      </li>
    </ul>
    <hr />
    <router-link :to="{ name: 'GlobalLists' }" class="nav-link">
      <font-awesome-icon icon="globe-asia" class="fa-lg" />
      <span>みんなのリスト</span>
    </router-link>
  </div>
</template>
<script>
export default {
  data: function() {
    return {
      list: [
        { name: "お気に入り", id: "favorite" },
        { name: "リスト1", id: 1 },
        { name: "リスト2", id: 2 },
        { name: "リスト3", id: 3 }
      ]
    };
  }
};
</script>
<style scoped>
hr {
  border-top: 1px solid #eeeeee;
}
.nav-link {
  color: #eeeeee;
}
.navbar-brand {
  color: #ffffff;
}
.router-link-exact-active {
  background-color: #767676;
  color: #ffffff;
}
.disable-router-link-active {
  background-color: #656565;
  color: #eeeeee;
}
</style>
