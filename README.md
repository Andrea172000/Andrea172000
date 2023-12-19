<!DOCTYPE html>
<html>
 <head>
 <title>To-Do List App</title>
 <script>
  function addItem() {
   var newItem = document.createElement("div");
   newItem.innerHTML = document.getElementById("myInput").value;
   newItem.onclick = removeItem;
   document.getElementById("list").appendChild(newItem);
   saveList();
  }
  function removeItem() {
   document.getElementById("list").removeChild(this);
   saveList();
  }
  function saveList() {
   localStorage.storedList = document.getElementById("list").innerHTML;
  }
  function loadList() {
   document.getElementById("list").innerHTML = localStorage.storedList;
   for(var i = 0; i < list.children.length; i++) {
    list.children[i].onclick = removeItem;
   }
  }
 </script>
 <style>
  .header {
    text-align: center;
    height:50px; 
    width: 300px; 
    background-color:lightblue; 
    float: center; 
    padding:10px; 
    margin:20px;
    text-align:centre; 
    font-size:24px;
  }
  .app {
  text-align: center;
    height:600px;
    width: 300px; 
    background-color: yellow;
    float: center; 
    padding:10px; 
    margin:20px;
  }
  input[type="button"] {
   background-color:white;
  }
 </style>
</head>
<body>
 <div class="header">
  <img style="float: left;"> 
  <p>Anding To do list</p>
 </div>
 <div class="app">
  <p style="font-size:25px; font-style:bold;">To-Do List</p>
  <input type="text" id="myInput" placeholder="Type here to add task"/>
  <br/>
  <input type="button" value="Add item" onclick="addItem();"/>
  <br/>
   <div id="list"></div>
 </div>
 <script>
  if(localStorage.storedList) {
   loadList();
  }
 </script>
</body>
</html>
