<template>
    <div class="tecnologias">
        <div class="tecnologias_box HTML">
            <p class="tecnologias_texto">HTML</p>
        </div>
        <div class="tecnologias_box CSS">
            <p class="tecnologias_texto">CSS</p>
        </div>
        <div class="tecnologias_box JS">
            <p class="tecnologias_texto">JavaScript</p>
        </div>
        <div class="tecnologias_box Bootstrap">
            <p class="tecnologias_texto">Bootstrap</p>
        </div>
        <div class="tecnologias_box VueJS">
            <p class="tecnologias_texto">VueJS</p>
        </div>

    </div>
</template>

<style scoped>
.tecnologias{
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
}
/* estilo de las box */
.tecnologias_box{
    display: flex;
    align-items: center;
    justify-content: center;
    height: 2rem;
    width: 6rem;
    color: aliceblue;
    font-weight: 700;
    margin: 0.5rem;
    text-shadow:
    1px 1px 0 #000,
    -1px 1px 0 #000,
    -1px -1px 0 #000,
    1px -1px 0 #000;
}
/* color de cada una */
.HTML{
    background-color: rgba(216, 38, 38, 0.952)
}
.CSS{
    background-color: blue;
}
.JS{
    background-color: yellow;
}
.Bootstrap{
    background-color: blueviolet;
}
.VueJS{
    background-color: green;
}
</style>