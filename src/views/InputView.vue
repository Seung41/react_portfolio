<template>
    <v-app id="home">
        <NavBar />
        <v-container fluid>
            <div class="head">
                <v-row>
                    <v-carousel cycle height="400" hide-delimiter-background show-arrows="hover">
                        <v-carousel-item v-for="(slide, i) in slides" :key="i">
                            <v-sheet :color="colors[i]" height="100%">
                                <div class="d-flex fill-height justify-center align-center">
                                    <div class="text-h2">
                                        {{ slide }} Slide
                                    </div>
                                </div>
                            </v-sheet>
                        </v-carousel-item>
                    </v-carousel>
                </v-row>
            </div>
            <v-col cols="12" id="page1">
                <div class="cntsMiddle">
                    <h1 class="mt-8">본인 정보 등록</h1>
                    <v-divider></v-divider>
                    <span class="text-caption">
                        <v-breadcrumbs :items="breadcrumb">
                            <template v-slot:prepend>
                                <v-icon size="small" icon="mdi-vuetify"></v-icon>
                            </template>
                        </v-breadcrumbs>
                    </span>
                    <v-row class="mt-10">
                        <v-col cols="12">
                            <v-select v-model="value" :items="items" chips label="소속 팀" multiple></v-select>
                        </v-col>
                        <v-col cols="12" sm="6">
                            <v-text-field label="Name" persistent-hint="outlined"></v-text-field>
                        </v-col>
                        <v-col cols="12" sm="6">
                            <v-text-field label="Phone" persistent-hint="outlined"></v-text-field>
                        </v-col>
                    </v-row>
                    <v-file-input multiple label="File input"></v-file-input>
                    <v-textarea label="Message" persistent-hint="outlined"></v-textarea>
                    <v-btn color="#FBDF7E" class="mt-2">Submit</v-btn>
                </div>
            </v-col>
        </v-container>
        <FooterView />
    </v-app>
</template>

<script>
import { defineComponent } from 'vue';

// Components
import NavBar from '@/components/NavBar.vue';
import FooterView from '@/components/FooterView.vue';

export default defineComponent({
    name: 'HomeView',
    data() {
        return {
            colors: [
                'indigo',
                'warning',
                'pink darken-2',
                'red lighten-1',
                'deep-purple accent-4',
            ],
            slides: [
                'First',
                'Second',
                'Third',
                'Fourth',
                'Fifth',
            ],
            items: ['ERP개발팀', '고객정보서비스팀', 'IT전략팀', 'IT보안팀'],
            value: ['ERP개발팀', '고객정보서비스팀', 'IT전략팀', 'IT보안팀'],
            breadcrumb: [
                {
                    title: '메인',
                    disabled: false,
                    href: 'breadcrumbs_dashboard',
                },
                {
                    title: 'Home',
                    disabled: false,
                    href: 'breadcrumbs_link_1',
                },
                {
                    title: '본인 정보 등록',
                    disabled: true,
                    href: 'breadcrumbs_link_2',
                },
            ],
        }
    },
    setup() {
        return {
            item: true,
            other: false,
            slider2: 50,
            categories: [
                { img: "9.png" },
                { img: "1.png" }
            ],
            imgItems: [
                { img: "i3.jpg", },
                { img: "i4.jpg", },
                { img: "i5.jpg", },
                { img: "i6.jpg", },
                { img: "i9.jpg", },
                { img: "i8.jpg", },
            ],
        };
    },

    components: {
        NavBar,
        FooterView,
    },

});
</script>
<style scoped>
.v-container {
    padding: 16px 0;
    background-color: #F6F6F6;
}

.head {
    position: relative;
    text-align: center;
    padding: 12px;
    margin-bottom: 6px;
    height: 400px;
    width: 100%;
    color: white;
}

.cntsMiddle {
    width: 100%;
    height: 800px;
    text-align: center;
    padding: 0 200px;
    background-color: #f5f5f5;
}
</style>