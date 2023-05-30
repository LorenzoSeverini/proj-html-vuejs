<!-- script -->
<script>

import footerino from './footerino.vue'

    export default {
        name: 'AppFooter',

        components: {
            footerino,
        },
        
        props: {
            
        },

        data () {
            return {
                //
            }
        },
    }

</script>

<!-- template -->
<template>
    <footer>
        <footerino />
    </footer>
    
</template>

<!-- style -->
<style lang="scss" scoped>

@use '../styles/partials/_variables' as *;
@use '../styles/partials/_mixing' as *;


</style>