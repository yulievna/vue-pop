<template>
  <div class="tabs">
    <router-link to="/"><div class="home">Home</div></router-link>
    <div class="stick"></div>
    <router-link to="/about"><div class="data">Data</div></router-link>
  </div>
  <router-view></router-view>
</template>

<style>
.tabs{
  display: flex;
  position: absolute;
  top: 0px;
  left: calc(50% - 120px);
}
.tabs div{
  font-weight: bold;
  font-size: large;
  margin: 20px;
  color: tomato;
}
.stick{
  border-right: 1px solid tomato;
}

.open-popup {
  width: 200px;
  position: absolute;
  top: calc(50% - 20px);
  left: calc(50% - 100px);
}
.popup__bg {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100vh;
  background: rgba(0, 0, 0, 0.5);
  transition: 0.5s all;
}
.popup {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background: #fff;
  width: 500px;
  padding: 25px;
  border-radius: 20px;
}

span {
  margin-left: 50px;
}

.popup label {
  width: 100%;
  margin-bottom: 25px;
  display: flex;
  flex-direction: column-reverse;
}
.popup h1 {
  text-transform: uppercase;
  color: tomato;
  text-align: center;
}

.popup .label__text {
  font-size: 10px;
  text-transform: uppercase;
  font-weight: 500;
  color: #cfd0d3;
}

.popup input {
  height: 45px;
  font-size: 18px;
  outline: none;
  border: 1px solid #cfd0d3;
  border-radius: 10px;
}

.popup input:focus + .label__text {
  color: tomato;
}
button {
  width: 100%;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #fff;
  font-size: 18px;
  border: 2px solid tomato;
  border-radius: 10px;
  background: tomato;
  cursor: pointer;
  text-transform: uppercase;
  transition: 0.5s all;
}
button:hover {
  background: #fff;
  color: tomato;
  transition: 0.5s all;
}
</style>