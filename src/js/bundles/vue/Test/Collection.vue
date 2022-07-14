<template>
    <div class="collections-grid">
        <div class='collections-grid__item' v-for="product in products" :key="product.id">
            <div class="collections-grid__item__img" >
                <a :href='"/products/"+product.handle'>
                    <img class="img" :src="product.featured_image" />
                </a>
                <button class="quick-view" @click.stop="toggleModal($event, product);">Quick View</button>
            </div>
 
            <label>{{product.title}}</label>
            <p>Rs.{{product.price}}</p>
        </div>

        <div class="modal-container" v-if='showQuickModal' @click.self="hideModal('showQuickModal')">
            <QuickModal :product='itemDetails' v-on:added='showCartPage()'/>
        </div>

        <div class="modal-container" v-if='showCart' @click.self="hideModal('showCart')">
            <Cart ref='cart'/>
        </div>
    </div>
</template>
<script>
    import QuickModal from './QuickModal.vue'
    import Cart from './Cart.vue';

    export default {
        name: "Collection page",
        components:{
            QuickModal,
            Cart
        },
        data(){
            return {
                showQuickModal: false,
                itemDetails: undefined,
                showCart: false,
            }
        },
        created(){
            console.log('products collection',  this.products)
        },
        mounted(){
            console.log("cart ref", this.$refs.cart)
        },
        props:{
            title: { 
                type:String, 
                default: 'I  here'
            },
            products: { 
                type: Array, 
                default: []
            }
        },
        methods:{
            toggleModal(evt, item){
                this.itemDetails = item;
                this.showQuickModal = !this.showQuickModal;
            },

            showCartPage(){
                this.showQuickModal = false;
                this.showCart = true;
                console.log('this.$refs.cart?', this.$refs.cart)
                this.$refs.cart?.showCartDetails();
            },
            hideModal(tab){
                this[tab]= !this[tab];
            }
        }
    }
</script>

<style>
    .collections-grid{
        display: flex;
        flex-wrap: wrap;
        gap: 2rem;
    }
    .collections-grid__item{
        height: auto;
        flex: 1 0 30%;
    }

    .collections-grid__item__img{
        position: relative;
    }

    
    .collections-grid__item__img .img{
        height: 30rem;
        width: 30rem;
        object-fit: fill;
    }

    .collections-grid__item__img .quick-view{
        height: 3rem;
        line-height: 2.4rem;
        position: absolute;
        bottom: 2rem;
        left: 50%;
        transform: translateX(-50%);
        opacity: 0;
        background-color: #ffffff;
        color: #000003;
        display: flex;
        align-items: center;
    }
    .collections-grid__item__img:hover .quick-view{
        opacity: 1;
    }
    .collections-grid .modal-container{
        height: 100%;
        width: 100%;
        background-color: #414042cc;
        position: fixed;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
    }    
</style>
