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
      <h3>Build. Deploy. Manage.</h3>
      </div>
          <div v-for="service in services" class="serviceCards">
              <md-card id="serviceCard">
                <md-card-header>
                  <md-card-header-text>
                    <div class="md-title">{{service.name}}</div>
                    <div class="md-subhead">{{service.msg}}</div>
                  </md-card-header-text>

                  <md-card-media>
                    <img :src="service.imgSrc">
                  </md-card-media>
                </md-card-header>

                <md-card-content>
                <ul v-for="link in service.links">
                  <li >
                    {{link.url}}
                  </li>
                </ul>
                </md-card-content>

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
  name: 'home',
  data() {
    return {
      msg: 'Developers',
      services: {
        "cdn": {
          name: "Client CLI",
          msg: "Deploy and host your static, client-side content across multiple environments.",
          imgSrc: "static/clientcli_conf.png",
          links: {
            "link1": {
              url: "url1link"
            }
          }
        },
        "api": {
          name: "Server CLI",
          msg: "Manage and deploy your server-side APIs using Node, Serverless Technology and AWS Lambdas.",
          imgSrc: "static/server-cli-conf.png",
          links: {
            "link1": {
              url: "url1link"
            }
          }
        },
        "buildbot": {
          name: "Hybrid App BuildBot",
          msg: "Build a hybrid app using any framework, and deploy cross-platform.",
          imgSrc: "static/buildbot-cli-conf.png",
          links: {
            "link1": {
              url: "url1link"
            }
          }
        },
        "forms": {
          name: "Forms CLI",
          msg: "Powerful next-gen forms generator for creating front-end forms components.",
          imgSrc: "static/forms_conf.png",
          links: {
            "link1": {
              url: "url1link"
            }
          }
        },
        "analytics": {
          name: "Analytics SDK",
          msg: "Javascript library for adding custom Server-Side analytics to your API project.",
          imgSrc: "static/analytics_conf.png",
          links: {
            "link1": {
              url: "url1link"
            }
          }
        },
        "console": {
          name: "Analytics Console",
          msg: "Management Console for displaying analytics dashboards with your custom data.",
          imgSrc: "static/console_conf.png",
          links: {
            "link1": {
              url: "url1link"
            },
            "link2": {
              url: "url2link"
            }
          }
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

.serviceCards{
  margin: 15px;
  width: 30%;
  display:inline-block;
}

#serviceCard{
  min-height: 300px;

}

#headerMain{
  width: 100%;
  align: center;
  margin-bottom: 150px;

}

#headerImg{
  float: left;
  width: 200px;
  display: table-cell; 
  vertical-align: bottom;
}

#headerWrapper{
  width: 315px;
  margin: 0 auto;
  margin-top:100px;
  height: 50px;
  margin-bottom: 75px;
}

#headerTitle{
  float: right;
  display: table-cell; 
  vertical-align: bottom;
  height: 10px;


}

#menuList{
  float: right;
  margin-right: 20px;
}

#linksList{
    
}

</style>
