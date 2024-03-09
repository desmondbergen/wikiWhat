<script lang="ts">
    import Anthropic from '@anthropic-ai/sdk';  
    export default{
        setup(props, ctx) {
            const anthropic = new Anthropic({
                apiKey: 'my_api_key', // defaults to process.env["ANTHROPIC_API_KEY"]
            });
            
        },
        props: {
        receivedText: {
            type: String
        }
    }
        
    }

</script>
<template>
    <div class="result">
        <h3>Your input: {{ receivedText }}</h3>
    </div>
</template>
<style scoped>
    .result{
        font-family:"Open Sans",Helvetica,Arial,sans-serif;
    }

</style>