<template>
    <div>
        <datagrid api="http://localhost/course/course-code/gz1706/vue/php/student.php"></datagrid>
    </div>
</template>

<script>
    import datagrid from '../datagrid/datagrid.vue'

    export default {
        components: {
            datagrid
        }
    }
</script>