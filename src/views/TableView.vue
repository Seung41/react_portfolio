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
                <div class="pre">
                    <h1 class="mt-8">개인별 자산 목록 조회</h1>
                    <v-divider></v-divider>
                    <span class="text-caption">
                        <v-breadcrumbs :items="breadcrumb">
                            <template v-slot:prepend>
                                <v-icon size="small" icon="mdi-vuetify"></v-icon>
                            </template>
                        </v-breadcrumbs>
                    </span>
                    <v-row class="mt-8">
                        <v-col cols="12" sm="2" md="2">
                            <v-switch v-model="ex1" label="indigo" color="indigo" value="indigo"
                                hide-details></v-switch>
                        </v-col>
                        <v-col cols="12" sm="2" md="2">
                            <v-switch v-model="ex1" label="orange" color="orange" value="orange"
                                hide-details></v-switch>
                        </v-col>
                        <v-col cols="12" sm="4" md="4" class="mt-2">
                            <v-radio-group v-model="ex2" inline>
                                <v-radio label="indigo" color="indigo" value="indigo"></v-radio>
                                <v-radio label="orange" color="orange" value="orange"></v-radio>
                            </v-radio-group>
                        </v-col>
                    </v-row>
                    <v-row>
                        <v-col cols="12">
                            <v-table fixed-header height="300px">
                                <thead>
                                    <tr>
                                        <th class="text-center">
                                            제품명
                                        </th>
                                        <th class="text-center">
                                            반출일
                                        </th>
                                        <th class="text-center">
                                            카테고리
                                        </th>
                                        <th class="text-center">
                                            관리자 사번
                                        </th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr :key="i" v-for="(product, i) in productList">
                                        <td>{{ product.product_name }}</td>
                                        <td>{{ product.price }}</td>
                                        <td>{{ product.category }}</td>
                                        <td>{{ product.delivery_price }}</td>
                                    </tr>
                                </tbody>
                            </v-table>
                        </v-col>
                    </v-row>
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

    components: {
        NavBar,
        FooterView,
    },

    data() {
        return {
            productList: [],
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
            ex1: ['indigo', 'orange'],
            ex2: 'red',
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
                    title: '자산 목록 조회',
                    disabled: true,
                    href: 'breadcrumbs_link_2',
                },
            ],
        };
    },
    created() {
        this.getList();
    },
    methods: {
        async getList() {
            this.productList = await this.$api("https://3272b01f-04cd-471b-a73c-65822f0621e2.mock.pstmn.io/list", "get");
        }
    }
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


.pre {
    width: 100%;
    height: 600px;
    text-align: center;
    padding: 0 200px;
    background-color: #f5f5f5;
}
</style>