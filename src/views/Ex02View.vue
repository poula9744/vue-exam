<template>
    <h1>{{ title }}</h1>
    <h2>{{ subTitle }}</h2>
    <ul>
        <li>{{ menus[0] }}</li>
        <li>{{ menus[1] }}</li>
        <li>{{ menus[2] }}</li>
    </ul>
    <table border="1">
        <thead>
            <tr>
                <th>번호</th>
                <th>이름</th>
                <th>핸드폰</th>
                <th>회사</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>{{ personVo.no }}</td>
                <td>{{ personVo.name }}</td>
                <td>{{ personVo.hp }}</td>
                <td>{{ personVo.company }}</td>
            </tr>
        </tbody>
    </table>

    <p>{{ content }}</p>
    <p v-html="content"></p>
    <img v-bind:src="imgUrl">
</template>

<script>
export default {
    name: "Ex02View",
    components: {},
    data() {
        return {
            title: "vue공부",
            subTitle: "바인딩된 소제목",
            menus:["게시판", "갤러리", "방명록"],
            personVo: {
                no: 1,
                name: "이효리",
                hp: "010-9999-9999",
                company: "02-9999-9999"
            },
            content: "지금부터 <strong>열심히!</strong> 하자",
            imgUrl: "data:image/png;base64,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"
        };
    },
    methods: {},
};
</script>
<style></style>
