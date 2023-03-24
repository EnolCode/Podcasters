
<template>
<div class="div">
    
<span>100</span>
<input type="text" placeholder="Filter podcasts..." class="input" >
</div>
</template>

<style lang="scss" scoped>
@use "../scss/colors" as c;

.div { 
    display:flex;
    align-self: end;
    margin-bottom: 5em;
    margin-right: 3em;
    justify-content: space-around;
    width: 17em;

    span{
        align-self: center;
        background: map-get(c.$colors, "blue-electric");
        padding: .2em .4em;
        border-radius: .6em;
        color: white;
    }

    .input{
        padding: .3em;
        border: 1px solid grey;
        border-radius: .3em;
        // margin-left: em;
    }
}
</style>