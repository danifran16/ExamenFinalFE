<template>
    <div id="app" class="container mt-5">
        <h1>Formulario de registro</h1>

        <form @submit.prevent="envioForm"> 
            <div class="mb-3">
                <label  class="form-label">Nombre</label>
                <input  type="text" v-model="form.nombre" id="nombre" @input="validarNombre" class="form-control">
                <p v-if="error.nombre" class="error-message">{{ error.nombre }}</p>
            </div>
            <div class="mb-3">
                <label class="form-label">Correo</label>
                <input type="email" v-model="form.correo" id="correo" @input="validarCorreo" class="form-control">
                <p v-if="error.correo" class="error-message">{{ error.correo }}</p>
            </div>

            <div class="mb-3">
                <label class="form-label">Contraseña</label>
                <input type="password" v-model="form.contraseña" id="contraseña" @input="validarContraseña" class="form-control">
                <p v-if="error.contraseña" class="error-message">{{ error.contraseña }}</p>
            </div>

            <div class="mb-3">
                <label class="form-label">Repetir contraseña</label>
                <input type="password" v-model="form.repetirContraseña" id="repetirContraseña" @input="validarContraseñaRepetida" class="form-control">
                <p v-if="error.repetirContraseña" class="error-message">{{ error.repetirContraseña }}</p>

            </div>

            <button type="submit" class="btn btn-primary">Enviar</button>
        </form>
    </div>

</template>

<script>
    export default {
        data() {
            return {
                form:{
                    nombre: "",
                    correo: "",
                    contraseña: "",
                    repetirContraseña: ""
                },
                error: {
                    nombre: "",
                    correo: "",
                    contraseña: "",
                    repetirContraseña: ""
                }
            };
        },
        computed: {
            total() {
            }
        },
        methods: {
            validarNombre(){
                if (!this.form.nombre) {
                    this.error.nombre = 'campo nombre requerido';
                }else if (/\d/.test(this.form.nombre)) {
                    this.error.nombre = 'campo nombre no debe contener números'
                }else {
                    this.error.nombre = '';
                }
            },
            validarCorreo(){
                if (!this.form.correo) {
                    this.error.correo = 'campo correo es requerido';
                } else if (!/^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/.test(this.form.correo)) {
                    this.error.correo = 'correo es inválido';
                } else {
                    this.error.correo = '';
                }
            },
            validarContraseña() {
                if (!this.form.contraseña) {
                    this.error.contraseña = 'campo contraseña es requerido';
                } else if (this.form.contraseña.length < 3) {
                    this.error.contraseña = 'La contraseña debe tener al menos 3 caracteres';
                } else {
                    this.error.contraseña = '';
                }
            },
            validarContraseñaRepetida() {
                if (!this.form.repetirContraseña) {
                    this.error.repetirContraseña = 'campo repetirContraseña es requerido';
                } else if (this.form.repetirContraseña !== this.form.contraseña) {
                    this.error.repetirContraseña = 'campo de contraseña debe coincidir';
                } else {
                    this.error.repetirContraseña = '';
                }
            },
            
            envioForm(){             
                this.validarNombre();
                this.validarCorreo();
                this.validarContraseña();
                this.validarContraseñaRepetida();

                if (!Object.values(this.error).some(error => error !== '')) {
                    alert('el registro se ha realizado correctamente');
                }
            }
    

        }
    };
</script>

<style scoped>
    #app {
        text-align: center;
    }
    button{
        background-color:beige;
        color: black;
    }

</style>
