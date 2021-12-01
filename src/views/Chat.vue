<template>
<div>
  <CometChatGroupListWithMessages/>
    <button v-on:click="logout" class="btn btn-sm bt-primary">Logout</button>

</div>
</template>

<script>
import { CometChat } from "@cometchat-pro/chat";
import {CometChatGroupListWithMessages} from '../cometchat-ui'
export default {
  components:{
CometChatGroupListWithMessages
  },
  methods:{
     async logout(){
  
  try {
    await CometChat.logout();
    this.$router.push({
        name: "homepage"
      });
  } catch (error) {
    console.error(error);
  }
}
  }
  }
</script>