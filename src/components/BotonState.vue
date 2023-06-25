<template>

    <button @click="state = !state">{{ labelBtn }}</button>
  
</template>

<script>
export default {
    data(){
        return {
            state: true
        }
    },
    emits: ['onChangeState'],
    computed: {
        labelBtn(){
            //al cambiar el estado se ejecuta de nuevo esta funcion y se aprovecha y emite un evento            
            this.emitter.on("onActiveAll", data => {
                this.state = data;
            });
            this.$emit('onChangeState', this.state);
            return this.state ? "Activo" : "Inactivo";
        }
    }
}
</script>