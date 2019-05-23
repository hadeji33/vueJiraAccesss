<template>
  <div class="hello">
    <h1>{{ page }}</h1>

  </div>
</template>

<script>




import * as axios from "axios";

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
      message: 'Hello Vue!',
      currentUrl: '',
      auth: '',
      page: ''
    };
  },
  created: async function () {
    console.log(axios);
    axios.get("https://auth.atlassian.com/authorize", {
      headers: {
        'Access-Control-Allow-Origin': '*',
      },      params:
              { audience: 'api.atlassian.com',
                client_id: 'Ktble6wjgyp3ZUisspLE5Skio0KCUFtd',
                scope: 'read%3Ajira-user%20read%3Ajira-work',
                redirect_uri: window.location.href,
                state: '1fsfaalls1123lllsap',
                response_type: 'code',
                prompt: 'consent' } })
            .then(response => (this.page = response.data));
    const code = await getCode();
    /*this.currentUrl = window.location.href;
    const axios = require('axios');
    const oauth = require('axios-oauth-client');
    const getAuthorizationCode = oauth.client(axios.create(), {
      url: 'https://auth.atlassian.com/oauth/token',
      grant_type: 'authorization_code',
      client_id: 'Ktble6wjgyp3ZUisspLE5Skio0KCUFtd',
      client_secret: 'D_d8OusbNeOKYo9Dz_3T3eAWQ9l5prdXACTCBpnEh_TUM1NvRmYay0yHiLAX1i6S',
      redirect_uri: 'window.location.href',
      code: 'Oyf8M9ouKOdEPLE4&state=g6Fo2SBobWhBVVJqckNLQ…NpZNkgS3RibGU2d2pneXAzWlVpc3NwTEU1U2tpbzBLQ1VGdGQ'
    });
    this.auth = await getAuthorizationCode();*/
  },
  methods: {

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
