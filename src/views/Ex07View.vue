<template>
    <h1>{{title}}</h1>
    <h1>{{subTitle}}</h1>

    <label>10대</label><input type="radio" name="age" value="10" v-model="picked">
    <label>20대</label><input type="radio" name="age" value="20" v-model="picked">
    <label>30대</label><input type="radio" name="age" value="30" v-model="picked">
    <label>40대</label><input type="radio" name="age" value="40" v-model="picked">
    <label>기타</label><input type="radio" name="age" value="etc" v-model="picked">
    <p>당신의 나이는 {{ picked }}대 입니다.</p>

    <br><br><br>
    <label>독서</label><input type="checkbox" name="hobby" value="book" v-model="checked">
    <label>여행</label><input type="checkbox" name="hobby" value="trip" v-model="checked">
    <label>잠</label><input type="checkbox" name="hobby" value="sleep" v-model="checked">
    <label>게임</label><input type="checkbox" name="hobby" value="game" v-model="checked">
    <p>당신의 취미는 {{ checked }}입니다.</p>
</template>
<script>

export default {
    name: "Ex07View",
    components: {},
    data() {
        return {
            title: "Vue 공부",
            subTitle: "폼-radio: ",
            picked: "30",
            checked: ["sleep", "game"]
        };
    },
    methods: {
        
    },
};
</script>
<style>

</style>