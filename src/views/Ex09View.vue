<template>
    <h1>{{title}}</h1>
    <h1>{{subTitle}}</h1>
    <p v-if="age<20">당신은 미성년자 입니다.</p>
    <p v-else-if="20<=age && age<65">당신은 성인 입니다.</p>
    <p v-else>당신은 노인 입니다.</p>
</template>
<script>

export default {
    name: "Ex09View",
    components: {},
    data() {
        return {
            title: "Vue 공부",
            subTitle: "if문",
            age: 64
        };
    },
    methods: {
        
    },
};
</script>
<style>

</style>