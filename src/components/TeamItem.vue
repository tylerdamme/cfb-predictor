<template>
    <div id="accordion">
        <div class="card">
            <div class="card-header" :style="{backgroundColor: team.color}">
                <a class="card-link"  data-toggle="collapse" v-bind:href="'#collapse' + team.id">
                    {{team.school}} {{team.mascot}}
                </a>
            </div>
            <div v-bind:id="'collapse' + team.id" class="collapse show" data-parent="#accordion">
            <div class="card-body">
                The games will go here
            </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'teamItem',
    props: ['team']
}

</script>
<ul>
        <li class="teamDisplay" :style="{backgroundColor: team.color}">{{team.school}} {{team.mascot}}</li>
    </ul>
<style>
    ul {
        list-style-type: none;
        vertical-align: middle;
    }
    
    .card-link {
        color: white;
    }
</style>