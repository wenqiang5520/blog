<template>
    <div class="paging">
        <el-pagination
                small
                :page-size="size"
                :page-sizes="sizes"
                @size-change="handleSizeChange"
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
            sizes: { type: Array },
        },
        name: 'pagination',
        data() {
            return {
                page:{
                    size:'',
                    index:'',
                }
            };
        },
        methods: {
            handleCurrentChange(val) {
                this.page.index = val;
                this.$emit('getPageMsg', this.page);
            },
            handleSizeChange(val) {
                this.page.size = val;
                this.$emit('getPageMsg', this.page);
            }
        },
        created() {
            console.log(this.total, this.size,this.sizes);
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