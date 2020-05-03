<template>
  <div class="">
    <div id="my-signin2"></div>
    <div id="gSignInWrapper">
      <div id="costomBtn" class="customGPlusSignIn">
      <!-- Ref(haven't finished): https://developers.google.com/identity/sign-in/web/build-button -->
        <span class="icon"></span>
        <span class="buttonText">Google</span>
      </div>
    </div>
  </div>
</template>

<script src="https://apis.google.com/js/platform.js?onload=onLoadCallback" async defer></script>
<script>
export default {
  name: 'ConstantTop',
  mounted() {
    gapi.signin2.render('my-signin2',{
      onsuccess : this.onSuccess
    });
  },
  methods: {
    onSuccess: function(googleUser) {
      var profile = googleUser.getBasicProfile();
      console.log('ID: ' + profile.getId()); // Do not send to your backend! Use an ID token instead.
      console.log('Name: ' + profile.getName());
      console.log('Image URL: ' + profile.getImageUrl());
      console.log('Email: ' + profile.getEmail());
    }
  },
  props: {
  },
  data: function() {
    return {
    };
  },
}
</script>

<style scoped>
  .constanttop {
    background: pink;
    color: white;
    width: 100%;
  }
  li {
    list-style-type: none;
    display: block;
  }
  img {
    height:100px;
  }
</style>
