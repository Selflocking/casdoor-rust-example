<!--Copyright 2022 The Casdoor Authors. All Rights Reserved.-->

<!--Licensed under the Apache License, Version 2.0 (the "License");-->
<!--you may not use this file except in compliance with the License.-->
<!--You may obtain a copy of the License at-->

<!--     http://www.apache.org/licenses/LICENSE-2.0-->

<!--Unless required by applicable law or agreed to in writing, software-->
<!--distributed under the License is distributed on an "AS IS" BASIS,-->
<!--WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.-->
<!--See the License for the specific language governing permissions and-->
<!--limitations under the License.-->

<template>
  <div id="headBox">
    <img id="logo" alt="Vue logo" src="./assets/casbin.svg">
    <p id="logoText">Casdoor Rust SDK example</p>
  </div>
  <p>
    <router-link to="/login"></router-link>
    <router-link to="/callback"></router-link>
    <router-link to="/about"></router-link>
    <router-link to="/home"></router-link>
  </p>
  <router-view></router-view>

</template>

<script>

export default {
  name: 'App',
  mounted() {
    let url = window.location.pathname
    if (url === '/') {
      if (localStorage.getItem('user')) {
        window.location.href = './home'
      } else {
        window.location.href = './login'
      }
    }

  }
}
</script>

<style>
#headBox {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100px;
  background-color: #f5f5f5;
}

#logo {
  width: 100px;
  float: left;
  margin: 100px 100px 100px 100px;
}

#logoText {
  font-size: 40px;
}
</style>
