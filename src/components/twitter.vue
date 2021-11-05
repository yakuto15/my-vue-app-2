<template>
  <div>
    <textarea
      class="form_textarea"
      v-model="text"
      placeholder="いまどうしてる"
    />
    <div>
      <button v-on:click="postTweet">投稿</button>
      <div v-for="(message,index)in messages" v-bind:key="index">
        {{ message.text }}
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      text: "",
      messages: [],
    }
  },
  methods: {
    postTweet() {
      const data = {
        value: this.text,
      }
      this.message.push(data)
    },
  },
}
</script>
