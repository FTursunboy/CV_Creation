<template>
  <div class="container column">
    <AppForm  @form_enter="add_part"></AppForm>
    <AppCV :title="title" :subtitle="subtitle" :avatar="avatar" :text1="text1"></AppCV>
  </div>
  <AppComment :comments="comments" @loadComments="getComments"></AppComment>
</template>

<script>
import AppComment from './components/AppComment'
import AppForm from './components/AppForm'
import AppCV from './components/AppCV'
import axios from 'axios'

export default {
  data() {
    return {
      comments: [],
      title: '',
      subtitle: '',
      avatar: '',
      text1: ''
    }
  },
  methods: {
    add_part(block) {
      if (block.title === 'title') {
        this.title = block.text
      }
      else if(block.title === 'subtitle') {
        this.subtitle = block.text
      }
      else if(block.title === 'avatar') {
        this.avatar = block.text
      }
      else {

        this.text1 = block.text

      }
    },


    async getComments() {
      const { data } = await axios.get('https://jsonplaceholder.typicode.com/comments?_limit=2');

      this.comments = Object.keys(data).map((key) => ({
        id: data[key].id,
        name: data[key].email,
        text: data[key].body,
      }));


    },
  },
  components: {
    AppComment, AppForm, AppCV
  }

}
</script>

<style>
.avatar {
  display: flex;
  justify-content: center;
}

.avatar img {
  width: 150px;
  height: auto;
  border-radius: 50%;
}
</style>
