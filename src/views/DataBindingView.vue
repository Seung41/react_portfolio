<template>
    <v-app id="home">
        <NavBar />
        <v-container fluid>
        <v-col cols="8" sm="8" id="Asset" class="padd">
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
            </v-col>
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
                { img: "i10.jpg"},
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

    data() {
        return {
                productList: []
            };
        },
        created() {
            this.getList();
        },
        methods: {
            async getList() {
                this.productList = await this.$api("https://3272b01f-04cd-471b-a73c-65822f0621e2.mock.pstmn.io/list","get");
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