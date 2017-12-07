<template>
    <div>
        <datagrid api="http://localhost/course/course-code/gz1706/vue/php/student.php" :filterCols="filterColumns"></datagrid>
    </div>
</template>

<script>
    import datagrid from '../datagrid/datagrid.vue'

    export default {
        data: function(){
            return {
                filterColumns: ['indexid', 'password', 'classes', 'phone']
            }
        },
        components: {
            datagrid
        }
    }
</script>