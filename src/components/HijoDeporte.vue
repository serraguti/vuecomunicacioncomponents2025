<template>
    <div>
        <h4 style="color:red">{{ nombredeporte }}</h4>
    </div>
</template>

<script>
    export default {
        name: "HijoDeporte",
        props: ["nombredeporte"]
        , mounted() {
            console.log(this.nombredeporte)
        }
    }
</script>