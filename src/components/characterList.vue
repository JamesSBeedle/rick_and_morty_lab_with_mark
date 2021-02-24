<template>
    <div>
        <form>
            <!-- <label for="character-select">Characters List: </label> -->
            <list-item v-for="(character, index) in characters" :character="character" :key="index" >{{character.name}}</list-item>
            <!-- <select name="character-select" id="character-select">
                <option value="character.name" v-for="(character, index) in characters" :key="index" >{{character.name}}</option>
            </select> -->
        </form>
    </div>
</template>

<script>
import listItem from "./listItem.vue";

export default {
    name: "character-list",
    props: ['characters'],
    components: {
        'list-item': listItem
    }
}
</script>

<style>

</style>