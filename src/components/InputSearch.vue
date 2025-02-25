<script>
export default {
    props: {
        modelValue: {
            type: String,
            default: ''
        },
    },
    emits: ['submit', 'update:modelValue'],
    method: {
        updateModelValue(e) {
            this.$emit('update:modelValue', e.target.value);
        },
    },
    submit(){
        this.$emit('submit');
    },
};
</script>

<template>
    <div class="'input-group">
        <input type="text"
        class='form-control'
        placeholder="Nhập thông cần tìm"
        vlaue="modelValue"
        @input="updateModelValue"
        @keyup.enter="submit"
        >
        <div class="input-group-append">
            <button class="btn btn-outline" type="button" @click="submit">
                <i class="fa fa-search">Tìm kiếm<main></main></i>
            </button>
        </div>
    </div>
    
</template>