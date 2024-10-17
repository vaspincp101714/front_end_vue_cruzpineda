<template>
	<div class="container">
		<form>
			<div class="align-items-center">
				<div class="row">
					<h1>Datos Personales</h1>
				</div>
				<div class="form-group row">
					<div class="col-sm">
						<label class="sr-only" for="pnombre">Primer Nombre</label>
						<input type="text" class="form-control" id="pnombre" v-model="pnom" placeholder="Primer Nombre" aria-describedby="descripcionPrimerNombre">
						<small id="descripcionPrimerNombre" class="form-text text-muted mb-4">Primer Nombre</small>
					</div>
					<div class="col-sm">
						<label class="sr-only" for="snombre">Segundo Nombre</label>
						<input type="text" class="form-control" id="snombre" v-model="snom" placeholder="Segundo Nombre" aria-describedby="descripcionSegundoNombre">
						<small id="descripcionSegundoNombre" class="form-text text-muted mb-4">Segundo Nombre</small>
					</div>
					<div class="col-sm">
						<label class="sr-only" for="papellido">Primer Apellido</label>
						<input type="text" class="form-control" id="papellido" v-model="pape" placeholder="Primer Apellido" aria-describedby="descripcionPrimerApellido">
						<small id="descripcionPrimerApellido" class="form-text text-muted mb-4">Primer Apellido</small>
					</div>
					<div class="col-sm">
						<label class="sr-only" for="sapellido">Segundo Apellido</label>
						<input type="text" class="form-control" id="sapellido mb-4" v-model="sape" placeholder="Segundo Apellido" aria-describedby="descripcionSegundoApellido">
						<small id="descripcionSegundoApellido" class="form-text text-muted mb-4">Segundo Apellido</small>
					</div>
					<div class="col-sm">
						<label class="sr-only" for="fechanac">Fecha de nacimiento</label>
						<input type="date" class="form-control" id="fechanac" v-model="fechnac" placeholder="Fecha de nacimiento" aria-describedby="descripcionFechaNac">
						<small id="descripcionFechaNac" class="form-text text-muted mb-4">Fecha de Nacimiento</small>
					</div>
					<div class="col-auto">
						<label class="sr-only" for="estadofam">Estado Familiar</label>
						<input type="text" class="form-control" id="estadofam" v-model="estfam" placeholder="Estado Familiar" aria-describedby="descripcionEstadoFam">
						<small id="descripcionEstadoFam" class="form-text text-muted mb-4">Estado Familiar</small>
					</div>
				</div>
				<div class="form-group row">
					<div class="col-sm">
						<label class="sr-only" for="profesion">Profesión</label>
						<input type="text" class="form-control" id="profesion" v-model="prof" placeholder="Profesión" aria-describedby="descripcionProfesion">
						<small id="descripcionProfesion" class="form-text text-muted mb-4">Profesión/Oficio</small>
					</div>
					<div class="col-sm">
						<label class="sr-only" for="estatura">Estatura</label>
						<input type="text" class="form-control" id="estatura" v-model="est" placeholder="Estatura" aria-describedby="descripcionEstatura">
						<small id="descripcionEstatura" class="form-text text-muted mb-4">Estatura(mtrs)</small>
					</div>
					<div class="col-sm">
						<label class="sr-only" for="peso">Peso</label>
						<input type="text" class="form-control" id="peso" v-model="pes" placeholder="Peso" aria-describedby="descripcionPeso">
						<small id="descripcionPeso" class="form-text text-muted mb-4">Peso(Lbrs)</small>
					</div>
					<div class="col-sm">
						<label class="sr-only" for="colorpiel">Color de Piel</label>
						<input type="text" class="form-control" id="colorpiel" v-model="colpiel" placeholder="Color de piel" aria-describedby="descripcionColorPiel">
						<small id="descripcionColorPiel" class="form-text text-muted mb-4">Color de piel</small>
					</div>
					<div class="col-sm">
						<label class="sr-only" for="colorojos">Color de ojos</label>
						<input type="text" class="form-control" id="colorojos" v-model="colojo" placeholder="Color de ojos" aria-describedby="descripcionColorOjos">
						<small id="descripcionColorOjos" class="form-text text-muted mb-4">Color de ojos</small>
					</div>
					<div class="col-sm">
						<label class="sr-only" for="colorcabello">Color de cabello</label>
						<input type="text" class="form-control" id="colorcabello" v-model="colocabe" placeholder="Color de cabello" aria-describedby="descripcionColorCabello">
						<small id="descripcionColorCabello" class="form-text text-muted mb-4">Color de cabello</small>
					</div>
				</div>
				<div class="row">
					<div class="col-sm">
						<label class="sr-only" for="residencia">Residencia</label>
						<input type="text" class="form-control" id="residencia" v-model="resid" placeholder="Residencia" aria-describedby="descripcionDireccion">
						<small id="descripcionDireccion" class="form-text text-muted mb-4">Dirección de residencia</small>
					</div>
				</div>
				<hr style="height:2px;border-width:0;color:gray;background-color:gray"> 
				<div v-for="(trabajo,i) in empleos" :key="i" class="row">
					<div class="col-auto">
						<label class="sr-only" for="nombreempresa">Nombre de la empresa</label>
						<input type="text" class="form-control mb-2" id="nombreempresa" v-model="trabajo.empresa" placeholder="Nombre de la empresa" aria-describedby="descripcionNombreEmpresa">
						<small id="descripcionNombreEmpresa" class="form-text text-muted mb-4">Nombre de la empresa</small>
					</div>
					<div class="col-auto">
						<label class="sr-only" for="dependencia">Dependencia</label>
						<input type="text" class="form-control mb-2" id="dependencia" v-model="trabajo.dependencia" placeholder="Dependencia" aria-describedby="descripcionDependenciaEmpresa">
						<small id="descripcionDependenciaEmpresa" class="form-text text-muted mb-4">Dependencia</small>
					</div>
					<div class="col-auto">
						<label class="sr-only" for="cargo">Cargo</label>
						<input type="text" class="form-control mb-2" id="cargo" v-model="trabajo.cargo" placeholder="Cargo" aria-describedby="descripcionCargoEmpresa">
						<small id="descripcionCargoEmpresa" class="form-text text-muted mb-4">Cargo</small>
					</div>
					<div class="col-auto">
						<label class="sr-only" for="desde">Desde</label>
						<input type="date" class="form-control mb-2" id="desde" v-model="trabajo.desde" placeholder="Desde" aria-describedby="descripcionDesdeEmpresa">
						<small id="descripcionDesdeEmpresa" class="form-text text-muted mb-4">Desde</small>
					</div>
					<div class="col-auto">
						<label class="sr-only" for="hasta">Hasta</label>
						<input type="date" class="form-control mb-2" id="hasta" v-model="trabajo.hasta" placeholder="Hasta" aria-describedby="descripcionHastaEmpresa">
						<small id="descripcionHastaEmpresa" class="form-text text-muted mb-4">Hasta</small>
					</div>
					<div class="col-sm">
						<label class="sr-only" for="direccion">Dirección</label>
						<input type="text" class="form-control mb-2" id="direccion" v-model="trabajo.direccion" placeholder="Dirección" aria-describedby="descripcionDirecciónEmpresa">
						<small id="descripcionDireccionEmpresa" class="form-text text-muted mb-4">Dirección de la empresa</small>
					</div>
				</div>
				<div class="col-auto">
					<button type="button" class="btn btn-primary mb-2" @click="cargar()">Cargar Datos del Backend</button>
				</div>
			</div>
		</form>
	</div>
</template>
<script>
import axios from 'axios'

export default {
	name: 'FormularioVue',
	props: {
		
	},
	data(){
		return{
			results:[],
			pnom:"",
			snom:"",
			pape:"",
			sape:"",
			fechnac:"",
			estfam:"",
			resid:"",
			prof:"",
			est:0.0,
			pes:0.0,
			colpiel:"",
			colojo:"",
			colocabe:"",
			empleos:[{
				empresa:"",
				dependencia:"",
				direccion:"",
				cargo:"",
				desde:"",
				hasta:""
			}]
		}
	},
	async mounted() {

	},
	methods:{
		async cargar(){
			try {
				const response = await axios.get('http://localhost:3000/usuario', { params: { query: this.query } })
				//this.results = response.data
				this.pnom = response.data.primernombre
				this.snom = response.data.segundonombre
				this.pape = response.data.primerapellido
				this.sape = response.data.segundoapellido
				this.fechnac = response.data.fechanacimiento
				this.estfam = response.data.estadofamiliar
				this.resid = response.data.residencia
				this.prof = response.data.profesion
				this.est = response.data.estatura
				this.pes = response.data.peso
				this.colpiel = response.data.colorpiel
				this.colojo = response.data.colorojos
				this.colocabe = response.data.colorcabello
				this.empleos = response.data.ultimosempleos
			} catch(err) {
				console.log(err)
			}
		}
	}
}
</script>
<style>

</style>