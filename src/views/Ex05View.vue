<template>
    <h1>{{title}}</h1>
    <h1>{{subTitle}}</h1>

    <!--폼전송은 클릭이벤트와 다르다 ((form에 submit 이벤트))-->
    <form v-on:submit.prevent="getPersonVo" action="" method="get">
        <label for="uName">이름</label>
        <!-- 단방향: <input id="uName" type="text" name="name" v-bind:value="name">-->
        <input id="uName" type="text" name="name" v-model="personVo.name">
        <br>
        <label for="uHp">전화번호</label>
        <input id="uHp" type="text" name="hp" v-model="personVo.hp">
        <br>
        <textarea name="content" v-model="personVo.content"></textarea>
        <br>
        <button v-on:click="setPersonVo" type="button">값쓰기</button>
        <button type="submit">값수정</button>
    </form>
</template>
<script>

export default {
    name: "Ex05View",
    components: {},
    data() {
        return {
            title: "Vue 공부",
            subTitle: "폼-text, textarea: (양방향바인딩) --> 폼에는 그냥 쓰자",
            personVo: {
                name: "",
                hp: "",
                content: ""
            }
            
        };
    },
    methods: {
        setPersonVo(){
            console.log("click");
            
            let pVo = {
                name: "정우성",
                hp: "010-0000-0000",
                content: "안녕"
            }

            this.personVo = pVo;
        },
        getPersonVo(){
            console.log("데이터수집");
            console.log("서버로 전송.....");

            console.log(this.personVo);
        }
    },
};
</script>
<style>

</style>