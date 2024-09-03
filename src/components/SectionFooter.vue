<script>
export default {
    name:'SectionFooter'
}
</script>
<template>
    <div class="container__footer">
        <div class="text_desarrolladores">
            <p class="dev1">Develop by</p>
            
            <a href="https://www.instagram.com/teinviteok/" target="_blank" rel="noopener noreferrer">
                <p class="dev2">Teinvite.io</p>
            </a>
        </div>
    </div>
</template>
<style>
.container__footer{
    min-width:100vw;
    min-height:32px;
    display: flex;
    flex-direction: column;
    justify-content:flex-end;
    align-items: center;
    position:relative;
    background: rgba(128, 128, 128);
    bottom:0;
    left:0;
}
.text_desarrolladores {
    width: 100%;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    position: absolute;
    line-height: 10%;
}

.dev1 {
    color:white;
    font-size: .7rem;
}

.dev2 {
    color: black;
    font-size: .7rem;
    font-weight: 600;
    text-decoration: none;
}
</style>