<template>
    <ul>
        <li class="teamDisplay" :style="{backgroundColor: team.color}">{{team.school}} {{team.mascot}}</li>
    </ul>
</template>

<script>
export default {
    name: 'teamItem',
    props: ['team']
}

</script>

<style>
    ul {
        list-style-type: none;
        vertical-align: middle;
    }
    
    .teamDisplay {
        border: 1px;
        border-style: solid;
        border-color: black;
        width: 40%;
        margin: auto;
        color: white;
    }
</style>