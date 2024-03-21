<template>
    <h1>{{title}}</h1>
    <h1>{{subTitle}}</h1>

    <select name="telecom">
        <option value="">이동통신사를 선택해주세요</option>
        <option value="skt">SKT</option>
        <option value="kt" selected="selected">KT</option>
        <option value="lg">LG U+</option>
    </select>

    <br><br>
    
    <select name="telecom" v-model="telecom">
        <option value="">이동통신사를 선택해주세요</option>
        <option value="skt">SKT</option>
        <option value="kt">KT</option>
        <option value="lg">LG U+</option>
    </select>
    <p>선택한 이동통신사는 {{ telecom }} 입니다.</p>
</template>
<script>

export default {
    name: "Ex06View",
    components: {},
    data() {
        return {
            title: "Vue 공부",
            subTitle: "폼-selectbox: ",
            telecom: "lg"
            
        };
    },
    methods: {
        
    },
};
</script>
<style>

</style>