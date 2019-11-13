<template>
  <div class="container">
    <article>
      <h1 class="title">{{post.title}}</h1>
      <p class="text">{{post.text}}</p>
    </article>
    <aside>
      <h3>Related posts</h3>
      <ul>
        <li v-for="related in relatedPosts" :key="related.id">
          <nuxt-link :to="{
            name: 'posts-id',
            params: {
              id: related.id
              }
            }">{{related.title}}</nuxt-link>
        </li>
      </ul>
    </aside>
  </div>
</template>

<script>

  export default {
    //name: "id.vue",
    head(){
      return {
        title: this.post.title
      }
    },
    data() {
      return {
        id: this.$route.params.id,
        posts: [
          {
            "id": "1",
            "index": 0,
            "picture": "http://placehold.it/32x32",
            "title": "amet",
            "text": "Proident est est reprehenderit qui dolor proident. Incididunt labore aliqua incididunt id eu est duis anim in. Aute elit eiusmod labore duis mollit sit cupidatat aliquip ipsum et sit esse amet. Cillum consectetur laborum consequat non anim eiusmod. Veniam consectetur magna dolor do occaecat laborum minim. Deserunt veniam amet veniam laborum cillum occaecat non nostrud amet Lorem culpa ullamco nostrud. Nostrud tempor adipisicing eiusmod duis aliquip non.\r\n",
            "createDate": "2018-06-21T07:51:03 -03:00",
            "tags": [
              "qui",
              "consectetur",
              "id",
              "velit",
              "in",
              "laborum",
              "aute"
            ]
          },
          {
            "id": "2",
            "index": 1,
            "picture": "http://placehold.it/32x32",
            "title": "laboris",
            "text": "Culpa voluptate in occaecat ut quis esse officia veniam incididunt. Eiusmod elit commodo amet qui irure nulla deserunt velit ipsum non. Fugiat voluptate anim nisi occaecat veniam commodo eu nostrud duis velit proident veniam ad. Sint aliquip ea aliquip incididunt exercitation officia eu et eu ullamco laboris commodo. Anim sint quis aliquip tempor eu nostrud enim nisi amet dolor aute aliqua. Incididunt nostrud ea adipisicing velit.\r\n",
            "createDate": "2016-08-16T09:27:17 -03:00",
            "tags": [
              "dolor",
              "fugiat",
              "est",
              "nulla",
              "esse",
              "nisi",
              "occaecat"
            ]
          },
          {
            "id": "3",
            "index": 2,
            "picture": "http://placehold.it/32x32",
            "title": "sunt",
            "text": "Qui excepteur do ex tempor deserunt proident pariatur irure voluptate duis esse ut quis irure. Aliqua ipsum enim cupidatat sit deserunt elit veniam ad ex ea. Occaecat qui enim voluptate et sit adipisicing fugiat nostrud fugiat nostrud reprehenderit. Qui reprehenderit excepteur incididunt ex culpa incididunt. Do est eiusmod qui proident quis et laboris officia exercitation sit voluptate excepteur labore enim.\r\n",
            "createDate": "2017-09-12T01:44:23 -03:00",
            "tags": [
              "dolor",
              "quis",
              "proident",
              "eu",
              "quis",
              "elit",
              "magna"
            ]
          },
          {
            "id": "4",
            "index": 3,
            "picture": "http://placehold.it/32x32",
            "title": "duis",
            "text": "Minim aliquip ex sint id ipsum dolor sunt tempor sint occaecat eu nostrud. Sit anim nostrud qui labore. Lorem qui ex qui exercitation id excepteur non dolor occaecat non occaecat ad reprehenderit. Reprehenderit excepteur consectetur incididunt ex. Eiusmod occaecat do non qui. Dolor eu velit Lorem do incididunt magna fugiat ullamco excepteur mollit nulla elit.\r\n",
            "createDate": "2017-10-10T11:20:58 -03:00",
            "tags": [
              "irure",
              "nostrud",
              "ut",
              "amet",
              "deserunt",
              "anim",
              "ipsum"
            ]
          },
          {
            "id": "5dcabbf8a7942589280c1f19",
            "index": 4,
            "picture": "http://placehold.it/32x32",
            "title": "culpa",
            "text": "Cillum minim id quis eiusmod aliqua occaecat irure sunt ea laboris sint enim et. Incididunt duis nulla laborum labore deserunt consequat in aliqua do enim fugiat nisi et. Ex do excepteur voluptate excepteur aliqua aute reprehenderit deserunt non. Aliquip qui velit commodo aliqua proident tempor anim.\r\n",
            "createDate": "2019-08-30T03:37:09 -03:00",
            "tags": [
              "enim",
              "in",
              "Lorem",
              "sint",
              "duis",
              "nisi",
              "labore"
            ]
          },
          {
            "id": "6",
            "index": 5,
            "picture": "http://placehold.it/32x32",
            "title": "nostrud",
            "text": "Irure elit est exercitation dolor cupidatat consequat in. Exercitation consequat ullamco nisi laborum consequat et ipsum Lorem enim dolor ullamco fugiat eiusmod. Nostrud ipsum ex minim id adipisicing ut dolore nulla ut eu eiusmod. Elit ipsum aliquip veniam proident id ex. Ex occaecat qui officia aliqua officia ea laborum quis aliqua sunt laboris tempor sunt mollit. Nulla dolor eiusmod voluptate anim duis eu sint ad quis ipsum proident. Fugiat ex consectetur elit aute quis occaecat ipsum sit culpa cupidatat irure consectetur Lorem mollit.\r\n",
            "createDate": "2014-04-03T05:58:38 -04:00",
            "tags": [
              "cillum",
              "sit",
              "quis",
              "mollit",
              "adipisicing",
              "nisi",
              "et"
            ]
          }
        ]
      }
    },
    computed: {
      post() {
        return this.$store.state.posts.all.find( post => post.id === this.id );
      },
      relatedPosts() {
        return this.$store.state.posts.all.filter( post => post.id !== this.id );
      }
    }
  }
</script>

<style scoped>

</style>
