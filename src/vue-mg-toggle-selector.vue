<template>
    <div class="btn-group" role="group" v-if="!options">
        <button type="button" class="btn btn-outline-info" :class="classObjectLeft" @click="onChange(left)">{{left}}</button>
        <button type="button" class="btn btn-outline-danger" :class="classObjectRight" @click="onChange(right)">{{right}}</button>
    </div>
    <div class="btn-group" role="group" v-else>
        <template v-for="(option, index) in options">
            <button type="button" class="btn btn-outline-primary" :style="styleObject" :class="classObject(option)" @click="onChange(option)" :key="index">{{option}}</button>
        </template>
    </div>
</template>
<script>
export default {
    props: {
        value: '',
        left_text: '',
        right_text: '',
        options: null,
        button_width: '',
    },
    data() {
        return {
            //
        }
    },
    mounted() {
        //
    },
    watch: {
        //
    },
    computed: {
        left() {
            if (this.left_text) {
                return this.left_text
            } else {
                return 'OK'
            }
        },
        right() {
            if (this.right_text) {
                return this.right_text
            } else {
                return 'NG'
            }
        },
        classObjectLeft() {
            return {
                active: this.value==this.left,
            }
        },
        classObjectRight() {
            return {
                active: this.value==this.right,
            }
        },
        classObject() {
            return (name) => {
                return {
                    active: this.value==name,
                    
                }
            }
        },
        styleObject() {
            return {
                width: this.button_width,
            }
        },
    },
    methods: {
        onChange(event) {
            if (this.value == event) {
                this.$emit('input', '')
            } else {
                this.$emit('input', event)
            }
        },
    },
}
</script>
<style lang="scss" scoped>
</style>