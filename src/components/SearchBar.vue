<script lang="ts">
    import {ref} from "vue";
    export default{
        setup(props, ctx) {
            const searchValue = ref('');

            //send value of textarea input
            const emitSearchValue=(event:any)=>{
                ctx.emit('emitSearch',searchValue.value);
            }

            return{
                searchValue, emitSearchValue,
            }
        },
    }
</script>
<template>
    <div class="search">
        <label for="search">What are you thinking of?</label>
        <!--textarea input-->
        <input type="text" v-model="searchValue" name="search" @keyup.enter="emitSearchValue"></input>
    </div>
</template>
<style scoped>
    .search{
        display:flex;
        flex-direction:column;
        font-family:"Open Sans",Helvetica,Arial,sans-serif;
    }
</style>