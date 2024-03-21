<template>
    <h1>{{title}}</h1>
    <h1>{{subTitle}}</h1>

    <div class="box" v-bind:class="{'box-red':isRed ,'box-blue':isBlue, 'f-bold':isBold, 'f-size':isSize, 'f-ita':isIta}">{{ boxText }}</div>

    <button v-on:click="redBox" type="button">빨간박스</button>
    <button v-on:click="blueBox" type="button">파란박스</button>
    <button v-on:click="boldOnOff" type="button">BOLD on/off</button>
    <button v-on:click="sizeOnOff" type="button">SIZE on/off</button>
    <button v-on:click="itaOnOff" type="button">ITA on/off</button>

    <br><br><br><br>
    <p style="font-size: 30px;">인라인스타일로 태그에 스타일 직접추가</p>
    <br>
    <p v-bind:style="type">인라인스타일로 태그에 스타일 추가</p>
    <button v-on:click="changeType" type="button">인라인스타일변경</button>
</template>
<script>

export default {
    name: "Ex04View",
    components: {},
    data() {
        return {
            title: "Vue 공부",
            subTitle: "class속성 제어",
            boxText: "vue공부.........",
            isRed: false,
            isBlue: false,
            isBold: false,
            isSize: false,
            isIta: false,
            type:""
        };
    },
    methods: {
        redBox(){
            this.isRed=true;
            this.isBlue=false;
        },
        blueBox(){
            this.isBlue=true;
            this.isRed=false;
        },
        boldOnOff(){
            if(this.isBold==true){
                this.isBold = false;
            } else {
                this.isBold = true;
            }
        },
        sizeOnOff(){
            this.isSize = !this.isSize;
        },
        itaOnOff(){
            this.isIta = !this.isIta;
        },
        changeType(){
            this.type = "color: #ff0000; font-size: 30px";
        }
    },
};
</script>
<style>
.box{
    width: 150px;
    border: 1px solid #000000;
}

.box-red{
    background-color: #ff0000;
}

.box-blue{
    background-color: blue;
}
.f-bold{font-weight: bold;}
.f-size{font-size: 20px;}
.f-ita{font-style: italic;}
</style>