<template>
    <div class="sidebar">
        <header>MIS POSTS</header>
    </div>
</template>
  
  <script>

    export default {
        name: 'SideBar',
    }
  </script>
  
  <style>
    .sidebar {
    position: fixed;
    box-sizing: border-box;
    width: max(10%, 200px);
    justify-content: center;
    align-items: center;
    text-align: center;
    height: 100%;
    display: inline-block;
    padding-top: 50px;
    background-color: #e2e5b5;
    box-shadow: 0 6px 8px rgba(0, 0, 0, 0.1);
    }
    .sidebar header {
    font-weight: bold;
    font-size: 1.5rem;
    text-align: center;
    }
    .sidebar li {
    padding-top: 2rem;
    }
    .sidebar ul {
    list-style: none;
    }
    .sidebar a {
    text-decoration: none;
    }
    .sidebar button {
    background-color: transparent;
    font-family: "Cormorant Garamond", serif;
    font-size: 1.5rem;
    font-weight: bold;
    cursor: pointer;
    color: #706233;
    width: 100%;
    height: 50px;
    text-align: center;
    }
    .sidebar button:hover {
    background-color: #773434;
    color: #fff0f0;
    }
    .sidebar label {
    font-size: 1.2rem;
    padding: 1rem;
    border: transparent;
    border-radius: 3px;
    width: 100%;
    height: 50px;
    text-align: left;
    font-weight: bold;
    }
    .sidebar input[type=checkbox] {
    cursor: pointer;
    font-size: 0.5rem;
    padding: 1rem;
    margin-right: 15px;
    width: 1.5rem;
    height: 50px;
    background-color: #e2e5b5;
    }
    .sidebar .filter-field {
    display: none;
    }
    .sidebar #tag-filter {
    display: none;
    }
    .sidebar select {
    text-align: left;
    background-color: transparent;
    font-family: "Cormorant Garamond", serif;
    font-size: 1.2rem;
    padding: 1rem;
    border: transparent;
    background-color: transparent;
    border-radius: 3px;
    width: 100%;
    height: 50px;
    color: #706233;
    font-weight: bold;
    }
    .sidebar select:focus, .sidebar select:hover, .sidebar select:active {
    border: transparent;
    background-color: #e2e5b5;
    }
    
  </style>
  