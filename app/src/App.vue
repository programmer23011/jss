<script>
import dance from './components/dance.vue';
export default {
  components: {
    dance,
  }
}

</script>
<template>
  <div class="container mt-5">
    <dance />
  </div>
</template>
<style>
.container {
  max-width: 600px;
  margin: 0 auto;
}
.image{
  width: 142px;
  height: 96px;
  background-color: rgb(255, 0, 76);
  margin-right: 4px;
  margin-top: 12px;
}
body {
  margin: 0;
  padding: 0;
  background-color: #f8f9fa; 
  color: #212529;
}
p{
  font-weight: 500;
}
.col-1{
  width: 165px;
  height: 200px;
  border: 2px, solid, #1a1a1a;
  margin-left: 5px;
  margin-top: 20px;

  background-color: rgba(107, 114, 114, 0.466);
  border-radius: 16px; 
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08); 
}
.dir{
  width: 142px;
  height: 96px;
}
.col-2{
  background-color: rgba(107, 114, 114, 0.466);
  width: 165px;
  height: 200px;
  margin-left: 30px;
  border-radius: 15px;
  border: 2px, solid, #1a1a1a;
  margin-top: 20px;
}
.col-3{
  background-color: rgba(107, 114, 114, 0.466);
  width: 165px;
  height: 200px;
  margin-left: 40px;
  border-radius: 15px;
  border: 2px, solid, #1a1a1a;
  margin-top: 20px;
}
.card{
  transition: transform 0.3s ease; 
}
.card:hover{
  transform: translateY(-8px) scale(1.02);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15);
}
.col-4{
  background-color: rgba(107, 114, 114, 0.466);
  width: 165px;
  height: 200px;
  margin-top: 25px;
  border-radius: 15px;
  border: 2px, solid, #1a1a1a;
  margin-left: 5px;
}
.col-5{
  background-color: rgba(107, 114, 114, 0.466);
  width: 165px;
  height: 200px;
  margin-left: 30px;
  margin-top: 25px;
  border-radius: 15px;
  border: 2px, solid, #1a1a1a;
}
.col-6{
  background-color: rgba(107, 114, 114, 0.466);
  width: 165px;
  height: 200px;
  margin-left: 40px;
  margin-top: 25px;
  border-radius: 15px;
  border: 2px, solid, #1a1a1a;
}
.tr {
  margin-top: 25px;
  height: 210px;
  border: 2px, solid, #1a1a1a;
}
.inp{
  margin-top: 0px;
}
h2{
  color: #1a1a1a;
  font-family: Impact, fantasy;
  margin-left: 10px;
}
h3{
  margin-top: 5px;
  color: #1a1a1a;

}
h4{
  margin-top: -10px;
  color: #1a1a1a;
  margin-left: 10px;
  width: 170px;
}
.tit{
  margin-top: 15px;
}
.th{
  width: 130px;
  height: 30px;
  border: 2px, solid, black;
  margin-top: 35px;
  margin-left: 150px;
}
#theme{
  margin-left: 5px;
}
.logo{
  width: 100px;
  height: 100px;
  border-radius: 10px;
  background-size: cover; 
  background-position: center; 
  background-repeat: no-repeat;
  display: flex;
  align-items: center;
  justify-content: center;
}
.img{
  width: 100%;
  height: 250px;
  border-radius: 10px;
  background-size: cover; 
  background-position: center; 
  background-repeat: no-repeat;
  display: flex;
  align-items: center;
  justify-content: center;
}
header{
  display: flex;
}
label{
  margin-left: 5px;
}
.like{
  height: 40px;
  width: 40px;
  font-size: 15px;
  background-image: url(like.png);
  background-repeat: no-repeat;
  background-position: center;
  background-size: 30px;
  margin-right: 50px;
}
.dislike{
  height: 40px;
  width: 40px;
  font-size: 15px;
  background-image: url(dis.png);
  background-repeat: no-repeat;
  background-position: center;
  background-size: 30px;
}
.back {
  background-color: lightcoral;
}
</style>