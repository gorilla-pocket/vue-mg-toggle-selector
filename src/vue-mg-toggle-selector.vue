<template>
    <div class="btn-group" role="group">
        <button type="button" class="btn btn-outline-info" :class="classObjectLeft" @click="onChange(left)">{{left}}</button>
        <button type="button" class="btn btn-outline-danger" :class="classObjectRight" @click="onChange(right)">{{right}}</button>
    </div>
</template>
<script>
export default {
    props: [
        'value',
        'left_text',
        'right_text',
    ],
    data() {
        return {
            //
        }
    },
    mounted: function () {
        //
    },
    watch: {
        //
    },
    computed: {
        left: function () {
            if (this.left_text) {
                return this.left_text
            } else {
                return 'OK'
            }
        },
        right: function () {
            if (this.right_text) {
                return this.right_text
            } else {
                return 'NG'
            }
        },
        classObjectLeft: function () {
            return {
                active: this.value==this.left,
            }
        },
        classObjectRight: function () {
            return {
                active: this.value==this.right,
            }
        },
    },
    methods: {
        onChange: function (event) {
            if (this.value == event) {
                this.$emit('input', '')
            } else {
                this.$emit('input', event)
            }
        }
    },
}
</script>
<style lang="scss" scoped>
</style>