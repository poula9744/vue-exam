<template>
    <h1>{{title}}</h1>
    <h1>{{subTitle}}</h1>

    <table border="1">
        <thead>
            <tr>
                <th>순번</th>
                <th>번호</th>
                <th>이름</th>
                <th>핸드폰</th>
                <th>회사</th>
            </tr>
        </thead>
        <tbody>
            <tr v-bind:key="personVo.no" v-for="(personVo, i) in pList">
                <td>{{ i }}</td>
                <td>{{ personVo.no }}</td>
                <td>{{ personVo.name }}</td>
                <td>{{ personVo.hp }}</td>
                <td>{{ personVo.company }}</td>
            </tr>
        </tbody>
    </table>

    <button v-on:click="getList">데이터불러오기</button>

    <br><br>
    <span v-bind:key="i" v-for="(ageInfo, i) in radioAges">
        <label>{{ ageInfo.text }}</label><input type="radio" name="age" v-bind:value="ageInfo.code" v-model="aPicked">
    </span>
    <p>당신의 나이는 {{ aPicked }} 입니다.</p>
</template>
<script>

export default {
    name: "Ex08View",
    components: {},
    data() {
        return {
            title: "Vue 공부",
            subTitle: "반복문",
            pList: [],
            aPicked: "",
            radioAges: [
                {text:"10대", code:"10"}, {text:"20대", code:"20"}, {text:"30대", code:"30"}, {text:"40대", code:"40"}, {text:"기타", code:"etc"}
            ]
        };
    },
    methods: {
        getList(){
            console.log("데이터 수신중.... ");

            let personList = [
                {    no: 1, 
                    name: "정우성",
                    hp: "010-1111-1111",
                    company: "02-1111-1111"}, 
                {   no: 2, 
                    name: "이효리",
                    hp: "010-2222-2222",
                    company: "02-2222-2222"}, 
                {   no: 3, 
                    name: "유재석",
                    hp: "010-3333-3333",
                    company: "02-3333-3333"}
            ]

            this.pList = personList;
        }
    },
    created(){
        this.getList();
    }
};
</script>
<style>

</style>