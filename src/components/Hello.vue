<template>
  <div class="hello">
  <div id="menu">
  <ul id="menuList">
    <li>Developers Blog</li>
    <li>GitHub</li>
    <li>NPM Directory</li>
    <li>Helpdesk Portal</li>
  </ul>
  </div>
  <div id="headerMain">
  <div id="headerWrapper">
      <img id="headerImg" src="../assets/BlinkMobile_Logo.png"></img><h1 id="headerTitle" class="md-title" style="flex: 1">{{ msg }}</h1> 
      </div>    
</div> 
          <div v-for="service in services" class="serviceCard">
              <md-card>
                <md-card-header>
                  <md-card-header-text>
                    <div class="md-title">{{service.name}}</div>
                    <div class="md-subhead">{{service.msg}}</div>
                  </md-card-header-text>

                  <md-card-media>
                    <img :src="service.imgSrc">
                  </md-card-media>
                </md-card-header>

                <md-card-actions>
                  <md-button><img src="static/github.png" id="btnSmallGit"></md-button>
                  <md-button><img src="static/npm.png" id="btnSmallNpm"></md-button>
                </md-card-actions> 
              </md-card> 
            </div> 
          </div>
</template>

<script>
export default {
  name: 'hello',
  data() {
    return {
      msg: 'Developers',
      services: {
        "cdn": {
          name: "Client CLI",
          msg: "cdn hosting",
          imgSrc: "static/clientcli_conf.png"
        },
        "api": {
          name: "Server CLI",
          msg: "api hosting",
          imgSrc: "static/server-cli-conf.png"
        },
        "buildbot": {
          name: "Hybrid App BuildBot",
          msg: "Hybrid apps",
          imgSrc: "static/buildbot-cli-conf.png"
        },
        "forms": {
          name: "Forms CLI",
          msg: "Create Forms Components",
          imgSrc: "static/forms_conf.png"
        },
        "analytics": {
          name: "Analytics SDK",
          msg: "JavaScript & PHP Analytics SDK",
          imgSrc: "static/analytics_conf.png"
        },
        "console": {
          name: "Analytics Console",
          msg: "Console for creating and viewing Analytics dashboards",
          imgSrc: "static/console_conf.png"
        }
      } 
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
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

#headerMain{
  display: inline-block;
}

#btnSmallNpm{
  width: 40px;
}

#btnSmallGit{
  width: 50px;
}

.serviceCard{
  margin: 15px;
  width: 30%;
  display:inline-block;
}

#headerMain{
  width: 100%;
  align: center;
    margin-bottom: 100px;

}

#headerImg{
  float: left;
  width: 200px;
}

#headerWrapper{
  width: 315px;
  margin: 0 auto;
  margin-top:100px;
  position: relative;
}

#headerTitle{
  float: right;

}

#menuList{
  float: right;
  margin-right: 20px;
}

</style>
