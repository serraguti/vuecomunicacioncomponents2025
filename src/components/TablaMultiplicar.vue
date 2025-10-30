<template>
    <div>
        <h1>Tabla multiplicar</h1>
        <table border="1">
            <thead>
                <tr>
                    <th>Operación</th>
                    <th>Resultado</th>
                </tr>
            </thead>
            <tbody v-html="html">
            </tbody>
        </table>
    </div>
</template>

<script>
    export default {
        name: "TablaMultiplicar",
        data() {
            return {
                html: "",
                numero: 0
            }
        },
        watch: {
            '$route.params.valor' (nextVal, oldVal){
                if (nextVal != oldVal){
                    this.generarTabla();
                }
            }
        },
        methods: {
            generarTabla() {
                let aux = "";
                this.numero = parseInt(this.$route.params.valor);
                for (var i = 1; i <= 10; i++){
                    aux += "<tr>";
                    aux += "<td>" + this.numero + "*" + i + "</td>";
                    aux += "<td>" + (this.numero * i) + "</td>";
                    aux += "</tr>";
                }
                this.html = aux;
            }
        }, mounted() {
            this.generarTabla();
        }
    }
</script>

