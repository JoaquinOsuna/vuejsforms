<template>
  <div id="app" class="container">
    <div class="col-md-6">
      <h1>Formulario</h1>
      <form>
    <div class="form-group">
      <label for="correo">Nombre</label>
      <input type="text" class="form-control" placeholder="Nombre" v-model.trim.lazy="usuario.nombre">
    </div> 
    <div class="form-group">
      <label for="correo">Correo Electrónico</label>
      <input type="email" class="form-control" placeholder="Correo Electrónico" v-model.lazy='usuario.correo'>
    </div>
    <div class="form-group">
      <label for="clave">Contraseña</label>
      <input type="password" class="form-control" placeholder="Contraseña" v-model='usuario.pass'>
    </div>
    <div class="form-group">
      <label for="clave">Edad</label>
      <input type="text" class="form-control" placeholder="Edad" v-model.number='usuario.edad'>
    </div>
    <div class="form-group">
      <label for="pais">País</label>
      <select class="form-control" v-model='usuario.pais'>
        <option v-for="pais in paises" v-bind:key = pais> {{ pais }} </option>
      </select>
    </div>
    
    <div class="form-group">
      <label for="mensaje">Mensaje</label>
      <textarea class="form-control" rows="3" v-model='usuario.mensaje'></textarea>
    </div>

    <fieldset class="form-group">
      <legend>Genero</legend>
      <div class="form-check">
        <label class="form-check-label">
          <input type="radio" class="form-check-input" name="optionsRadios"  
                value="hombre" checked>
          Hombre
        </label>
      </div>
      <div class="form-check">
      <label class="form-check-label">
          <input type="radio" class="form-check-input" name="optionsRadios"  
                value="mujer">
          Mujer
        </label>
      </div>
      
      </fieldset>
      <div class="form-check">
        <label class="form-check-label">
          <input type="checkbox" class="form-check-input" value="acepto">
          Acepto las condiciones
        </label>
      </div>
      <div class="form-check">
        <label class="form-check-label">
          <input type="checkbox" class="form-check-input" value="newsletter">
          Recibir la newsletter
        </label>
      </div>
      <button type="submit" class="btn btn-primary">Enviar</button>
    </form>
    </div>
    <div class="resultados col-md-6">
      <h1>Resultados</h1>
      <p><strong>Nombre: </strong> {{ usuario.nombre }} - {{ usuario.nombre.length }}</p>
      <p><strong>Correo Electrónico: </strong> {{ usuario.correo }}</p>
      <p><strong>Contraseña: </strong> {{ usuario.pass }}</p>
      <p><strong>Edad: </strong>{{ usuario.edad }} - {{ typeof usuario.edad }}</p>
      <p><strong>País: </strong>{{ usuario.pais }}</p>
      <p class="mensaje"><strong>Mensaje: </strong> {{ usuario.mensaje }}</p>
      <p><strong>Genero: </strong></p>
      <p><strong>Condiciones: </strong></p>
    </div>
  </div>
</template>

<script>
export default {
  data (){
    return {
      usuario: {
        nombre: '',
        correo: '',
        pass : '',
        edad : '',
        pais : '',
        mensaje : '',
        genero : '',
      },
      paises : ['Mexico', 'Espania', 'Estados Unidos', 'Venezuela']

    }
  }
}
</script>

<style>
 

</style>
