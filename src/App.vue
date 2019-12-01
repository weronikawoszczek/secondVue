<template>
  <div>
    <Header/>
    <h1>Hello Werka</h1>
    <ul>
      <li
        v-for="comment in comments"
        class="comment"
        :key="comment.id"
      >//v-bind:key kady element który zostal stowrzony z apomocą v-for musi miec swój klucz, dzięki któremu vue jest w stanie to poprawnie renderować, najlepiej zasymulować istnienie zmiennej id, w przypadku zwracania obiektow z api zapobiega to błędom
        <p>{{ comment.name }}</p>
        <p>{{ comment.content }}</p>
      </li>
    </ul>
  </div>
</template>

<script>
import Header from "./components/Header.vue";

export default {
  name: "App",
  components: {
    Header
  },
  data() {
    return {
      comments: [
        //lista komentarzy w postaci tablicy z zagniezdzonymi obiektami
        {
          id: 1234,
          name: "Roman",
          content: "Best site ever"
        },
        {
          id: 1235,
          name: "Pablo",
          content: "Best project ever"
        },
        {
          id: 1236,
          name: "Adam",
          content: "The same"
        },
        {
          id: 1237,
          name: "Ada",
          content: "Same here"
        }
      ]
    };
  }
};
</script>

<style lang="scss" scoped>
//scoped izoluje style wykorzystane w komponencie tak aby nie wplywaly na inne komponenty, nawet jezeli nazwy sa takie same
h1 {
  color: #fab;
}

.comment {
  background: #eee;
  padding: 20px;
  margin-bottom: 10px;
  list-style: none;

  p:first-child {
    font-weight: bold;
  }
  p:last-child {
    font-size: 2.5em;
  }
}
</style>

//v-for - iteruje przez dane i redneruje je w postaci listy 