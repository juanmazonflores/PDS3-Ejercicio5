<template>
  <SideBar/>
  <main>
    <TableContainer/>
    <ModalVue/>
  </main>

</template>

<script>
import SideBar from './components/SideBar.vue'
import TableContainer from './components/TableContainer.vue'
import ModalVue from './components/ModalVue.vue'

export default {
  name: 'App',
  components: {
    SideBar,
    TableContainer,
    ModalVue
  }
}

//#region 7. FETCH
const apiURL = 'https://jsonplaceholder.typicode.com/posts';


function fetchAPI(url, method = 'GET', data = null) {

  const headers = {
    'Content-Type': 'application/json',
  };

  const options = {
    method,
    headers,
  };

  if (data !== null && (method === 'POST' || method === 'PUT' || method === 'DELETE')) {
    options.body = JSON.stringify(data);
  }

  return fetch(url, options)
    .then(response => {
      if (!response.ok) {
        throw new Error('Error en la solicitud: ' + response.status);
      }
      return response.json();
    })
    .catch(error => {
      if (error instanceof TypeError) {
        console.error('Error de red:', error.message);
      } else {
        console.error('Error general:', error.message);
      }
    });

}
//#endregion

//#region 6. FUNCIONES UTILES



//#endregion

//#region 1. MODELO DE DATOS (MODELS)
// Clase Tarea
class Task {
    constructor(id, userId, title, body) {
      this.id = id; 
      this.userId = userId; 
      this.title = title; 
      this.body = body; 
    }
}

function mapAPIToTasks(data) {
    return data.map(item => {
      return new Task(
        item.id,
        item.userId,
        item.title,
        item.body,
      );
    });
}

//#endregion

//#region 2. TAREAS (VIEW)

function displayTasksView(tasks) {

    clearTable();
  
    showLoadingMessage();
  
    if (tasks.length === 0) {
  
      showNotFoundMessage();
  
    } else {
  
      hideMessage();
  
      displayTasksTable(tasks);
    }
  
}

function clearTable() {
    const tableBody = document.getElementById('data-table-body');
  
    tableBody.innerHTML = '';
}

function displayTasksTable(tasks) {

    const tablaBody = document.getElementById('data-table-body');
  
    tasks.forEach(task => {
  
      const row = document.createElement('tr');
      
      if (task.completed) {
        row.style.textDecoration='line-through';

      }
      row.innerHTML = `
        <td>${task.id}</td>
        <td>${task.userId}</td>
        <td>${task.title}</td>
        <td>
          <button class="btn-get fa-solid fa-magnifying-glass" data-task-id="${task.id}"></button>
        </td>
      `;
  
      tablaBody.appendChild(row);
  
    });
  
    initDetailsTaskButtonHandler();

}

function showLoadingMessage() {
    const message = document.getElementById('message');
  
    message.innerHTML = 'Cargando...';
  
    message.style.display = 'block';
}

function showNotFoundMessage() {
    const message = document.getElementById('message');
  
    message.innerHTML = 'No se encontraron tareas con el filtro proporcionado.';
  
    message.style.display = 'block';
}


function hideMessage() {
    const message = document.getElementById('message');
  
    message.style.display = 'none';
}

//#region 4. BOTONES PARA AGREGAR, ACTUALIZAR Y ELIMINAR TAREAS (VIEW)


function openTaskModal(data) {
  document.getElementById('sale-form').reset();
  document.getElementById('modal-background').style.display = 'block';
  document.getElementById('modal').style.display = 'block';
    document.getElementById('id-field').value=data.id;
    document.getElementById('modal-title').textContent='Actualizar Tarea';
    document.getElementById('title-field').value=data.title;
    document.getElementById('description-field').value=data.description;

}

function closeTaskModal() {
    document.getElementById('modal-title').textContent='Nueva Tarea';
    document.getElementById('modal-background').style.display = 'none';
    document.getElementById('modal').style.display = 'none';
    document.getElementById('botonModal').textContent='Guardar Tarea';
}




//Funcion para procesar la creacion o actualizacion de una tarea
function initDetailsTaskButtonHandler() {
  document.querySelectorAll('.btn-get').forEach(button => {

    button.addEventListener('click', () => {

      const taskId = button.getAttribute('data-task-id'); 
      getTask(taskId); 
    });

  });

}

//#endregion

//#region 5. CONSUMO DE DATOS DESDE API

function getTasksData(tag,completed) {

  const url = buildGetTasksDataUrl(tag,completed);

  fetchAPI(url, 'GET')
    .then(data => {
      
      const tasksList = mapAPIToTasks(data);
      displayTasksView(tasksList);
    });
}

function getTask(id) {
  fetchAPI(`${apiURL}/${id}`, 'GET')
    .then(data => {
      openTaskModal(data)
    });
  
}


function buildGetTasksDataUrl() {

  const url = new URL(`${apiURL}`);
  return url;
}



//#endregion

//#region 6. INICIAR CONTROLADORES

getTasksData();
initTaskButtonsHandler();


//#ENDregion

</script>

<style>
  @import url('../public/styles.css');
 
  
</style>
