<template>
      <div id="modal-background" class="modal-background">
      </div>


    <div id="modal" class="modal">

        <h2 id="modal-title">DETALLES DE POST</h2>

        <form id="sale-form" class="form-section fx-content-center fx-row">

          <div class="fx-row">
              <h4>ID: </h4>
              <h4 id="id-field" class="form-field"></h4>
          </div>

          <div class="fx-row">
              <h4>ID Usuario: </h4>
              <h4 id="userid-field" class="form-field"></h4>
          </div>

          <div class="fx-row">
              <h4>Titulo: </h4>
              <h4 id="title-field" class="form-field"></h4>
          </div>
          
          <div  class="fx-row">
              <h4>Descripcion: </h4>
              <h4 id="description-field" class="form-field"></h4>
             
          </div>
                  
        </form>
        <h2>Presiona fuera de la ventana para salir</h2>
    </div>


    

</template>

<script>
  
  export default {
    name: 'ModalVue',
  }

</script>

<style scoped>
.modal-background {
  display: none;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
}

.modal {
  display: none;
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background: #E1C78F;
  padding: 20px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}
.form-section {
  flex-direction: column;
  background-color: #e2e5b5;
  padding: 1rem;
  gap: 0.5rem;
  font-size: 1.2rem;
  flex-wrap: wrap;
  align-items: left;
}
.form-section .form-field {
  display: flex;
  flex-direction: row;
}
.form-section input::placeholder {
  font-weight: lighter;
}
.form-section textarea::placeholder {
  font-weight: lighter;
}
.form-section select:invalid {
  font-weight: lighter;
}
.form-section input[type=date]:invalid::-webkit-datetime-edit {
  font-weight: lighter;
}
.form-section .filter-field:invalid {
  font-weight: lighter;
}
.form-section input,
.form-section textarea,
.form-section select {
  font-size: 1rem;
  padding: 1rem;
  border: transparent;
  border: 1.2px solid #d6b367;
  background-color: #e2e5b5;
  font-family: "Cormorant Garamond", serif;
  font-size: 1.2rem;
  font-weight: bold;
  color: #706233;
}
.form-section input:focus, .form-section input:hover, .form-section input:active, .form-section input:autocomplete,
.form-section textarea:focus,
.form-section textarea:hover,
.form-section textarea:active,
.form-section textarea:autocomplete,
.form-section select:focus,
.form-section select:hover,
.form-section select:active,
.form-section select:autocomplete {
  border: 1.2px solid #773434;
  font-family: "Cormorant Garamond", serif;
  font-size: 1.2rem;
  color: #706233;
  font-weight: bold;
}
.form-section input::-webkit-inner-spin-button, .form-section input::-webkit-calendar-picker-indicator,
.form-section textarea::-webkit-inner-spin-button,
.form-section textarea::-webkit-calendar-picker-indicator,
.form-section select::-webkit-inner-spin-button,
.form-section select::-webkit-calendar-picker-indicator {
  cursor: pointer;
  border-radius: 4px;
  margin-right: 2px;
  opacity: 0.6;
  filter: invert(0.1);
}
.form-section label {
  font-weight: bold;
  font-size: 1.3;
  margin-right: 1rem;
  width: 25%;
}
.form-section h4 {
  font-weight: bold;
  font-size: 1.3;
  margin-right: 1rem;
  width: 25%;
}
.form-section input[type=text],
.form-section input[type=number], .form-section select, .form-section textarea {
  flex-grow: 1;
  min-width: 300px;
}
.form-section input[type=date] {
  display: flex;
  flex-direction: row;
  min-width: 300px;
  align-items: left;
}
.form-section input[type=checkbox] {
  font: inherit;
  accent-color: #706233;
  margin-right: 0.4rem;
  width: 1rem;
  height: 1rem;
  border-radius: 0px;
}
.form-section button {
  border: none;
  padding: 0.5rem 1rem;
  cursor: pointer;
  transition: background-color 0.3s;
  font-size: 1.5rem;
  padding: 1rem 1.5rem;
  font-family: "Cormorant Garamond", serif;
  font-weight: bold;
}
.form-section button.btn-submit {
  background-color: #e2e5b5;
  color: #706233;
}
.form-section button.btn-submit:hover {
  background-color: #883c3c;
  font-family: "Cormorant Garamond", serif;
  color: #fff0f0;
}

</style>
