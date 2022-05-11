<template>
    <div>
        sono la search{{state.search}}
    </div>
</template>
<script>
import state from '../store.js'
export default {
    name:'AppSearch',
    data(){
        return{
            state
        }

    },
    methods:{

    }
}
</script>

<style lang="scss" scoped>

</style>