<template>
    <v-app-bar app color="#9155FD" dark flat class="px-12">
        <v-btn>
            <v-icon color="white" left class="mr-2" border="1px solid #eee">fas fa-signature</v-icon>HANSSEM
        </v-btn>
        <v-spacer></v-spacer>
        <v-btn text class="text-white"><router-link to="/">Home</router-link></v-btn>
        <v-btn text><router-link to="/input">Input</router-link></v-btn>
        <v-btn text><router-link to="/table">List</router-link></v-btn>
        <v-btn text @click="scroll('asset')">Asset</v-btn>
        <v-btn text @click="scroll('asset_admin')">Asset admin</v-btn>
        <v-btn text @click="scroll('contact')">Contact</v-btn>
        <v-btn text @click="scroll('page')">Page</v-btn>
    </v-app-bar>
</template>
<script>
export default {
    methods: {
        scroll(refName) {
            const element = document.getElementById(refName);
            element.scrollIntoView({behavior: "smooth"});
        }
    }
}
</script>
<style>

</style>