<template>
    <div class="paging">
        <el-pagination
                small
                :page-size="size"
                @current-change="handleCurrentChange"
                layout="total, prev, pager, next, jumper"
                :total="total">
        </el-pagination>
    </div>
</template>

<script>
    export default {
        props: {
            total: { type: Number },
            size: { type: Number },
        },
        name: 'pagination',
        data() {
            return {

            };
        },
        methods: {
            handleCurrentChange(val) {
                this.$emit('getPageIndex', val);
            }
        },
        created() {
            console.log(this.total, this.size);
        }
    };
</script>

<style lang="scss">
    .paging{
        float: right;
        margin-top: 0.2rem;
        .el-pagination__editor.el-input .el-input__inner{
            width: 100%;
            border: 1px solid #DCDFE6;
        }
        .el-pagination .el-select .el-input .el-input__inner{
            width: 100%;
            border: 1px solid #DCDFE6;
        }
    }

</style>