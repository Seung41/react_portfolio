<template>
    <v-app id="home">
        <NavBar />
        <v-container fluid>
        <div class="head">
            <v-row>
                <v-col cols="5">
                    <div style="position: relative" class="mt-16">
                        <h1 class="text-white">ERP개발팀 이승연님, </h1>
                        <h1 class="text-white">한샘 자산관리시스템 입니다.</h1>
                        <v-btn tile dark class="text-white mt-8" variant="outlined">Register</v-btn>
                    </div>
                </v-col>
                <v-col cols="2">
                    <div style="position: absolute; z-index: 9999; bottom: 0; margin-left: auto; margin-right: auto; left:0; right: 0; text-align: center;">
                        <v-icon>fas fa-angle-double-down</v-icon>
                    </div>
                </v-col>
                <v-col cols="3">
                    <div style="position:relative; z-index: 9999;" class="mt-16">
                        <br /><br />
                        <v-img src="i1.png" contain max-height="300"></v-img>
                        <span class="text-white">조회할 자산 번호를 입력하세요</span>
                        <v-text-field density="compact" variant="outlined" label="Search" append-inner-icon="fas fa-search" single-line hide-details class="mt-8"></v-text-field>
                    </div>
                </v-col>
            </v-row>
        </div>
        <v-col cols="12" class="padd" id="portfolio">
            <div class="first" id="project">
                <v-row>
                    <v-col cols="12">
                        <div class="child">
                            <v-btn icon="fas fa-laptop" color="#FBDF7E" class="text-white"></v-btn>
                            <h3 class="ml-3 mt-4">나의 PC 자산관리</h3>
                            <p class="text-grey ml-3 mt-4 text-caption">
                                사용자(재무, 총무, HelpDesk) 별 <br />소유 IT 자산 상태 조회
                            </p>
                        </div>
                        <div class="child">
                            <v-btn icon="fas fa-mobile-alt" color="#FBDF7E" class="text-white"></v-btn>
                            <h3 class="ml-3 mt-4">모바일 자산 조회</h3>
                            <p class="text-grey ml-3 mt-4 text-caption">
                                자산 등록 QR 인식 기능 제공 & <br />
                                모바일 자산 정보 조회
                            </p>
                        </div>
                        <div class="child">
                            <v-btn icon="fas fa-camera" color="#FBDF7E" class="text-white"></v-btn>
                            <h3 class="ml-3 mt-4">자산 등록 QR 기능</h3>
                            <p class="text-grey ml-3 mt-4 text-caption">
                                자산 등록 QR 인식 기능 제공 & <br />
                                모바일 자산 정보 조회
                            </p>
                        </div>
                    </v-col>
                </v-row>
            <v-divider></v-divider>
            </div>
        </v-col>
        <v-col cols="12" sm="12" id="page">
            <div class="d-flex justify-center mb-6">
                <v-btn color="#FBDF7E" class="mr-2">ALL</v-btn>
                <v-btn class="mr-2" variant="tonal">메뉴1</v-btn>
                <v-btn class="mr-2" variant="tonal">메뉴2</v-btn>
                <v-btn class="mr-2" variant="tonal">메뉴3</v-btn>
                <v-btn variant="tonal">메뉴1</v-btn>
            </div>
        </v-col>
        <v-col cols="12" class="imgHover">
            <v-row class="fill-height" align="center" justify="center">
                <template v-for="(item, i) in items" :key="i">
                <v-col cols="12" md="4"> 
                    <v-hover v-slot="{isHovering, props}">
                    <v-card :elevation="isHovering ? 12: 2" :class="{'on-hover' : isHovering}" v-bind="props">
                        <v-img :src="item.img" height="225px" cover></v-img>
                    </v-card>
                    </v-hover>
                </v-col>
                </template>
            </v-row>
        </v-col>
        <v-col cols="12" sm="12">
            <div class="d-flex justify-center mb-6">
                <v-btn color="#FBDF7E" class="mt-4">Load more</v-btn>
            </div>
        </v-col>
        <v-col cols="12" id="page1">
            <div class="pre">
                <v-row>
                <v-col cols="12" sm="4">
                    <v-card class="mw-auto" max-width="600" height="">
                    <v-img src="i10.jpg" height="200px" cover></v-img>
                    <v-card-title>We Provide you the best</v-card-title>
                    <v-card-subtitle>
                        By AAE IdeaPro
                    </v-card-subtitle>
                    <v-card-text>
                        adsadsadsadsadsa
                    </v-card-text>
                    </v-card>
                </v-col>
                <v-col cols="12" sm="4">
                    <v-card class="mw-auto" max-width="600" height="">
                    <v-img src="i11.jpg" height="200px" cover></v-img>
                    <v-card-title>We Provide you the best</v-card-title>
                    <v-card-subtitle>
                        By AAE IdeaPro
                    </v-card-subtitle>
                    <v-card-text>
                        adsadsadsadsadsa
                    </v-card-text>
                    </v-card>
                </v-col>
                <v-col cols="12" sm="4">
                    <v-card class="mw-auto" max-width="600" height="">
                    <v-img src="i12.jpg" height="200px" cover></v-img>
                    <v-card-title>We Provide you the best</v-card-title>
                    <v-card-subtitle>
                        By AAE IdeaPro
                    </v-card-subtitle>
                    <v-card-text>
                        adsadsadsadsadsa
                    </v-card-text>
                    </v-card>
                </v-col>
                </v-row>
            </div>
        </v-col>
        <v-col cols="12" id="blog">
            <div class="hire">
                <v-row>
                <v-col cols="12" sm="8">
                    <h1 class="mt-9">qweqeqe</h1>
                    <p class="text-gray">
                    asdasdsadasdasdsa
                    </p>
                </v-col>
                <v-col cols="12" sm="4">
                    <v-btn color="#FBDF7E" class="mt-15">Hire Me</v-btn>
                </v-col>
                </v-row>
            </div>
        </v-col>
        <v-col cols="12" sm="12" class="px-16" id="contact">
            <v-row>
                <v-col cols="12" sm="4">
                    <div class="child">
                        <h1>Contact info.</h1>
                        <v-btn icon="fas fa-map-marker-alt" class="mt-10" variant="outlined"></v-btn><br />
                        <span class="text-caption">sdfsfdsfdsfdsfd</span><br />
                        <v-btn icon="fas fa-phone-alt" class="mt-10" variant="outlined"></v-btn><br />
                        <span class="text-caption">asdasd</span><br />
                        <span class="text-caption">asdasd</span><br />
                        <v-btn icon="fas fa-envelope" class="mt-10" variant="outlined"></v-btn><br />
                        <span class="text-caption">asdasd</span><br />
                        <span class="text-caption">asdasd</span><br />
                    </div>
                </v-col>
                <v-col cols="12" sm="8">
                <h1 class="mt-8">asdad</h1>
                <v-divider></v-divider>
                <span class="text-caption">
                    asdadas
                </span>
                <v-row class="mt-10">
                    <v-col cols="12" sm="6">
                    <v-text-field label="Name" persistent-hint="outlined"></v-text-field>
                    </v-col>
                    <v-col cols="12" sm="6">
                    <v-text-field label="Phone" persistent-hint="outlined"></v-text-field>
                    </v-col>
                </v-row>
                <v-textarea label="Message" persistent-hint="outlined"></v-textarea>
                <v-btn color="#FBDF7E" class="mt-2">asdadad</v-btn>
                </v-col>
            </v-row>
        </v-col>
            <!-- <v-col cols="8" sm="8" id="Asset" class="padd">
            <div class="first">
                <v-row>
                <v-col cols="12">
                    <div class="child">
                    <v-table fixed-header height="300px">
                        <thead>
                        <tr>
                            <th class="text-left">
                            제품명
                            </th>
                            <th class="text-left">
                            가격
                            </th>
                            <th class="text-left">
                            카테고리
                            </th>
                            <th class="text-left">
                            배송비
                            </th>
                        </tr>
                        </thead>
                        <tbody>
                        <tr :key="i" v-for="(product, i) in productList">
                            <td>{{ product.product_name }}</td>
                            <td>{{product.price}}</td>
                            <td>{{product.category}}</td>
                            <td>{{product.delivery_price}}</td>
                        </tr>
                        </tbody>
                    </v-table>
                    </div>
                    </v-col>
                    </v-row>
                </div>
            </v-col> -->
        </v-container>
        <footerView />
    </v-app>
</template>

<script>
import { defineComponent } from 'vue';

  // Components
import NavBar from '@/components/NavBar.vue';
import FooterView from '@/components/FooterView.vue';


export default defineComponent({
    name: 'HomeView',

    setup() {
        return {
            item: true,
            other: false,
            slider2: 50,
            categories: [
                {img: "9.png"},
                {img: "1.png"}
            ],
            items: [
                { img: "i3.jpg",},
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

    // data() {
    //       return {
    //           productList: []
    //       };
    //   },
    //   created() {
    //       this.getList();
    //   },
    //   methods: {
    //       async getList() {
    //           this.productList = await this.$api("https://3272b01f-04cd-471b-a73c-65822f0621e2.mock.pstmn.io/list","get");
    //       }
    //   }
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
    .head::before{
        content: " ";
        position: absolute;
        top: 0;
        left: 0;
        height: 100%;
        width: 50%;
        background: #9155FD;
        transform: skew(0deg, 4deg);
    }
    .head::after {
        content: " ";
        position: absolute;
        top: 0;
        right: 0;
        height: 100%;
        width: 50%;
        background: #9155FD;
        transform: skew(0deg, -4deg);
    }
    .first {
        width: 100%;
        height: 280px;
        text-align: center;
        padding: 2rem 2rem;
    }

    .child {
        display: inline-block;
        padding: 2rem 1rem;
        vertical-align: middle;
        text-align: center;
        margin-right: 8px;
    }
    .imgHover {
        padding: 0 200px;
    }
    .pre {
        width: 100%;
        height: 380px;
        text-align: center;
        padding: 0 200px;
        background-color: #f5f5f5;
    }
    .hire {
        width: 100%;
        height: 200px;
        padding: 0 200px;
        background-color: #e9e9e9;
        margin-top: -24px;
    }
    </style>