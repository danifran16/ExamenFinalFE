<template>
    <div id="app" class="container mt-5">
        <h1>Calculo de calificaciones</h1>

        <form @submit.prevent="calcularPromedio">
        <div class="mb-3">
            <label class="form-label">Nota 1</label>
            <input type="number" placeholder="Nota 1" @input="resetInput" v-model.number="nota1" min="10" max="70" class="form-control" required>
        </div>
        <div class="mb-3">
            <label class="form-label">Nota 2</label>
            <input type="number" placeholder="Nota 2" @input="resetInput" v-model.number="nota2" min="10" max="70" class="form-control" required>
        </div>

        <div class="mb-3">
            <label class="form-label">Nota 3</label>
            <input type="number" placeholder="Nota 3" @input="resetInput" v-model.number="nota3" min="10" max="70" class="form-control" required>
        </div>

        <div class="mb-3">
            <label class="form-label">Asistencia %</label>
            <input type="number" placeholder="Asistencia" @input="resetInput" v-model.number="asistencia" min="0" max="100" class="form-control" required>
        </div>

        <button type="submit" class="btn btn-primary">Calcular</button>
        </form>
        
        <div class="mb-3" v-if="estadoAlumno">
            <p>Promedio</p>
            <p>El promedio es: {{ promedioFinal }}</p>
            <p>El estado es: {{ estadoFinal }}</p>

            <p v-if="resultadoFinal">Aprobado</p>
            <p v-else>Reprobado</p>
        </div>

    </div>
</template>

<script>
    export default {
        data() {
            return {
                nota1: null,
                nota2: null,
                nota3: null,
                asistencia: null,
                estadoAlumno: false,
                resultadoFinal: null,
                estadoFinal: null
            };
        },
        computed: {
            promedioFinal() {
                return ((this.nota1 * 0.35) + (this.nota2 * 0.35) + (this.nota3 * 0.30))
            },

        },
        methods: {
            calcularPromedio() {
                const resultadoPromedio = (this.promedioFinal >= 0.4)
                const resultadoAsistenciaOK = this.asistencia >= 80

                this.resultadoFinal = resultadoPromedio && resultadoAsistenciaOK
                this.estadoAlumno = true
            },
            resetInput(){
            this.estadoAlumno = false,
            this.resultadoFinal = null

            }
        }
    };


</script>

<style scoped>
    /* Estilos específicos del componente */
    #app {
        text-align: center;
    }
    button {
        background-color: green;
    }

</style>
