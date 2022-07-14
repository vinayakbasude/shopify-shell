<template>
    <div class="custom-cart">
        <div class="cart-header">
            <div class="cart-header__main-heading">
                <h2 class="title">Cart</h2>
                <span class="total-quantity">
                    ({{ cart?.item_count }} {{ cart?.item_count > 1 ? 'items' : 'item' }})
                </span>
            </div>

            <button>
                <svg width="17px" height="17px" viewBox="0 0 17 17" version="1.1" xmlns="http://www.w3.org/2000/svg"
                    xmlns:xlink="http://www.w3.org/1999/xlink">
                    <title>Close Icon</title>
                    <g id="Welcome" stroke="none" stroke-width="1" fill="none" fill-rule="evenodd"
                        opacity="0.900000036">
                        <g id="Mobile-Sticky-Copy-2" transform="translate(-329.000000, -28.000000)" fill="#191919">
                            <g id="Group" transform="translate(329.000000, 28.000000)">
                                <rect id="Rectangle"
                                    transform="translate(8.500000, 8.900000) rotate(-45.000000) translate(-8.500000, -8.900000) "
                                    x="-2" y="8" width="21" height="1.8"></rect>
                                <rect id="Rectangle"
                                    transform="translate(8.500000, 8.900000) rotate(45.000000) translate(-8.500000, -8.900000) "
                                    x="-2" y="8" width="21" height="1.8"></rect>
                            </g>
                        </g>
                    </g>
                </svg>
            </button>
        </div>
        <div class="cart__item" v-for="item in cart?.items" :key="item.id">
            <div class="cart__item__image">
                <img class="img-aspect-ratio" :src="item.image" alt="">
            </div>
            <div class="cart__item__details">
                <div class="item-detail">
                    <h3 class="item-detail__title">{{ item.title }}</h3>
                    <span>{{ item.variant_title }}</span>
                </div>
                <div class="price-quantity-details">
                    <div class="quantity-controls">
                        <button @click="decrementQuantity">-</button>
                        <span>{{item.quantity}}</span>
                        <button @click="incrementQuantity">+</button>
                    </div>
                    <div>{{ item.price }}</div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    expose: ['showCartDetails'],
    data() {
        return {
            cart: undefined
        }
    },
    async mounted() {
        this.cart = await fetch(window.Shopify.routes.root + 'cart.js', {
            method: 'GET',
            headers: {
                'Content-Type': 'application/json'
            }
        }).then(response => {
            return response.json();
        })
            .catch((error) => {
                console.error('Error:', error);
            });

        console.log('cart details', this.cart)
    },
    methods: {
        incrementQuantity() {
            console.log('incrementQuantity')
        },
        decrementQuantity() {
            console.log('decrementQuantity')
        }
    }
}
</script>

<style lang="scss">
@mixin displayFlex($justify) {
    display: flex;
    justify-content: $justify
}
.custom-cart {
    position: fixed;
    right: 0;
    top: 0;
    bottom: 0;
    width: 36.8rem;
    background-color: #ffffff;
    padding: 1.4rem 1.6rem 1.6rem;

    .cart-header{
        display: flex;
        @include displayFlex(space-between);

        &__main-heading{
            @include displayFlex(flex-start);
            align-items: baseline;
            &__title{
                margin: 0;
            }
            .total-quantity{
                font-size: 1.2rem;
                font-weight: 200;
                line-height: 1.2rem;
            }
        }
    }

    .cart__item{
        display: grid;
        grid-template-columns: 7.6rem auto;
        margin-bottom: 2rem;
        &__image{
            height: 10rem;
            width: 8rem;

            .img-aspect-ratio{
                width: 100%;
                height: 100%;
            }
        }
        &__details{
            @include displayFlex(flex-start);
            flex-direction: column;
            margin-left: .8rem;
            .item-detail{
                &__title{
                    font-size: 1.4rem ;
                    line-height: 1.6;
                }
            }
            .price-quantity-details{
                @include displayFlex(space-between);
                align-items: center;
            }
        }
    }
    .quantity-controls{
        display: flex;
        justify-content: space-between;
        align-items: center;
        border: 1px solid #d5d4d4;
    }
}
</style>