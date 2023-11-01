<template>
    
    <div class="table-container">
        <table id="data-table">
        <thead>
            <tr id="row">
            <th>idTarea</th>
            <th>idUsuario</th>
            <th>Titulo</th>
            <th>Detalles</th>
            </tr>
        </thead>
        <tbody id="data-table-body">
            <!-- LLENAR CON API -->
        </tbody>
        </table>
    </div>
    <div id="message" class="message">
        <p>No se ha realizado una consulta de ventas.</p>
    </div>

</template>

<script>
    export default {
        name: 'TableContainer',
    }
    
</script>

<style scoped>
.table-container {
  max-width: 100%;
  overflow-x: auto;
}

table {
  width: 100%;
  border-collapse: collapse;
  white-space: nowrap;
  font-size: 1.2rem;
  font-weight: bold;
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.15);
}
table thead tr {
  background-color: #E1C78F;
  color: #706233;
  text-align: center;
}
table thead tr th {
  border: none;
  font-size: 1.2rem;
  font-weight: bolder;
  padding: 2rem 1.25rem;
  white-space: nowrap;
}
table tbody tr {
  border-bottom: none;
}
table tbody tr:nth-of-type(even) {
  background-color: #e2e5b5;
}
table tbody tr:last-of-type {
  border-bottom: 4px solid #E1C78F;
}
table tbody tr td {
  padding: 1rem 1.25rem;
  border: none;
  white-space: wrap;
  text-align: center;
}
table tbody tr input[type=checkbox] {
  font: inherit;
  accent-color: #706233;
  margin-right: 0.4rem;
  width: 1rem;
  height: 1rem;
  border-radius: 0px;
}

.fa-solid {
  color: #706233;
  background-color: transparent;
  font-size: 1.2rem;
  cursor: pointer;
}

.message {
  display: none;
  text-align: center;
  font-size: 1rem;
  padding: 2rem;
}

</style>


