<template>
  <div class="hello">
   <md-whiteframe md-elevation="2">
   <div id="topSection">
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
    <div id="headerImg" >
      <img src="../assets/BlinkMobile_Logo.png"></img>
    </div>
    <div id="headerTitle">
       <h1>{{msg}}</h1> 
    </div>
      
    </div>
      <h3>Build. Deploy. Manage.</h3>
    </div>
    </div>
   </md-whiteframe>
  
  <div id="servicesHeader">
  <h1> Services </h1>
  <md-divider></md-divider>
  </div>

          <div v-for="service in services" class="serviceCards" v-bind:key="service">
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
                <ul v-for="link in service.links" v-bind:key="link">
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
            <p>
              {{posts}}
              </p>
          </div>

</template>

<script>
import axios from 'axios';

import rssparser from 'rss-parser'

export default {
  name: 'home',
  data() {
    return {
      msg: 'Developers',
      posts: [],
      services: {
        "cdn": {
          name: "Client CLI",
          msg: "Deploy and host your static, client-side content across multiple environments.",
          imgSrc: "static/clientcli_conf.png",
          links: {
            "link1": {
              text: "url1link",
              url: ""
            },
            "link2":{
              text: "",
              url: ""
            },
            "link3":{
              text: "",
              url: ""
            },
            "link4":{
              text: "",
              url: ""
            }
          }
        },
        "api": {
          name: "Server CLI",
          msg: "Manage and deploy your server-side APIs using Node, Serverless Technology and AWS Lambdas.",
          imgSrc: "static/server-cli-conf.png",
          links: {
            "link1": {
              text: "url1link",
              url: ""
            },
            "link2":{
              text: "",
              url: ""
            },
            "link3":{
              text: "",
              url: ""
            },
            "link4":{
              text: "",
              url: ""
            }
          }
        },
        "buildbot": {
          name: "Hybrid App BuildBot",
          msg: "Build a hybrid app using any framework, and deploy cross-platform.",
          imgSrc: "static/buildbot-cli-conf.png",
          links: {
            "link1": {
              text: "url1link",
              url: ""
            },
            "link2":{
              text: "",
              url: ""
            },
            "link3":{
              text: "",
              url: ""
            },
            "link4":{
              text: "",
              url: ""
            }
          }
        },
        "forms": {
          name: "Forms CLI",
          msg: "Powerful next-gen forms generator for creating front-end forms components.",
          imgSrc: "static/forms_conf.png",
          links: {
            "link1": {
              text: "url1link",
              url: ""
            },
            "link2":{
              text: "",
              url: ""
            },
            "link3":{
              text: "",
              url: ""
            },
            "link4":{
              text: "",
              url: ""
            }
          }
        },
        "analytics": {
          name: "Analytics SDK",
          msg: "Javascript library for adding custom Server-Side analytics to your API project.",
          imgSrc: "static/analytics_conf.png",
          links: {
            "link1": {
              text: "url1link",
              url: ""
            },
            "link2":{
              text: "",
              url: ""
            },
            "link3":{
              text: "",
              url: ""
            },
            "link4":{
              text: "",
              url: ""
            }
          }
        },
        "console": {
          name: "Analytics Console",
          msg: "Management Console for displaying analytics dashboards with your custom data.",
          imgSrc: "static/console_conf.png",
          links: {
            "link1": {
              text: "url1link",
              url: ""
            },
            "link2":{
              text: "",
              url: ""
            },
            "link3":{
              text: "",
              url: ""
            },
            "link4":{
              text: "",
              url: ""
            }
          }
        }
      },
      rss: {}

    }
  },
  created() {
    axios.get(`http://blinkmobile.com.au/BlinkMobileDeveloperBlogRSSFeed?format=feed`)
    .then(response => {
      // JSON responses are automatically parsed.
      this.posts = response.data
    })
    .catch(e => {
      this.errors.push(e)
    })

    // async / await version (created() becomes async created())
    //
    // try {
    //   const response = await axios.get(`http://jsonplaceholder.typicode.com/posts`)
    //   this.posts = response.data
    // } catch (e) {
    //   this.errors.push(e)
    // }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello{
  background-color: #ebebeb;
}

#topSection{
  background-color: #fff;
  margin-bottom: 30px;
}
h1,
h2 {
  font-weight: normal;
  display: table-cell;
  padding-left: 6px;
  padding-bottom: 5px;
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

#servicesHeader{
  margin-left: 40px;
  margin-top: 20px;
  Margin-bottom: 30px;
  margin-right: 40px;
}

#btnSmallNpm{
  width: 40px;
}

#btnSmallGit{
  width: 50px;
}

.serviceCards{
  margin: auto 0;
  width: 30%;
  margin-bottom: 30px;
  display:inline-block;
  margin-left: 15px;
  margin-right: 15px;
}

#serviceCard{
  min-height: 300px;
  max-width: 500px;
}

#headerMain{
  width: 100%;
  margin-bottom: 150px;

}

#headerImg{
  width: 200px;
  display: table-cell; 
  vertical-align: bottom;
  padding-bottom: 5px;
}

#headerWrapper{
  width: 315px;
  margin: 0 auto;
  margin-top:100px;
  height: 50px;
  margin-bottom: 75px;
}

#headerTitle{
  display: table-cell; 
  vertical-align: bottom;
}

#menuList{
  float: right;
  margin-right: 20px;
}

#linksList{
    
}
/**/
</style>
