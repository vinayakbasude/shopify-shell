<template>
    <div class="mimic-cart">
        <div class="product__summary">
            <div class="product__summary__title">
                <h2 class="title"> {{ product.title }}</h2>
                <button class="close">
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
            <div class="product__summary__info">
                <div>
                    <span class="product__price">{{ product.price }}</span>
                    <s class="product__original-price">{{ product.compare_at_price }}</s>
                </div>

                <div class="product__reviews">
                    <div class="product__reviews__ratings" v-for="star in stars">
                        <svg width="12px" height="12px" viewBox="0 3 20 10" version="1.1"
                            xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
                            <title>Star Copy 3</title>
                            <g id="Welcome" stroke="none" stroke-width="1" fill="none" fill-rule="evenodd"
                                opacity="0.900000036">
                                <g id="Summer-Sale-Desktop" transform="translate(-308.000000, -2339.000000)"
                                    fill="#FF7400">
                                    <g id="Social-Proof" transform="translate(240.000000, 2154.000000)">
                                        <g id="Group-8" transform="translate(0.000000, 81.000000)">
                                            <g id="Group-45" transform="translate(0.000000, 104.000000)">
                                                <g id="Group-11" transform="translate(1.000000, 0.000000)">
                                                    <polygon id="Star-Copy-3"
                                                        points="75.5 12.75 70.5038254 15.3766445 71.4580098 9.81332223 67.4160196 5.87335555 73.0019127 5.06167777 75.5 0 77.9980873 5.06167777 83.5839804 5.87335555 79.5419902 9.81332223 80.4961746 15.3766445">
                                                    </polygon>
                                                </g>
                                            </g>
                                        </g>
                                    </g>
                                </g>
                            </g>
                        </svg>
                    </div>
                    <div class="product__reviews__review-count">48 Reviews</div>
                </div>
            </div>

        </div>

        <div class="product__images">
            <div class="product__images__container">
                <div v-for="image in product.images" :key="image" class="product__images__slide">
                    <img class="image" :src="image" alt="">
                </div>
            </div>
            <div class="product__images__buttons">
                <button class="prev">
                    <svg width="19px" height="15px" viewBox="0 0 19 15" version="1.1" xmlns="http://www.w3.org/2000/svg"
                        xmlns:xlink="http://www.w3.org/1999/xlink">
                        <title>Path</title>
                        <g id="Welcome" stroke="none" stroke-width="1" fill="none" fill-rule="evenodd">
                            <g id="Summer-Sale-Desktop" transform="translate(-951.000000, -2721.000000)" fill="#000000"
                                fill-rule="nonzero">
                                <g id="Social-Proof" transform="translate(240.000000, 2154.000000)">
                                    <g id="Group-49" transform="translate(681.000000, 535.000000)">
                                        <path
                                            d="M30.95,40.42928 L45.7567,40.42928 L40.6609,45.41386 C40.289925,45.7767382 40.289925,46.3651955 40.6606625,46.7278414 C41.0316375,47.0907195 41.6334625,47.0907195 42.0044375,46.7278414 L48.72165,40.1570052 L48.72165,40.1570052 C48.765825,40.1137944 48.80525,40.0661695 48.839925,40.0155245 C48.8558375,39.9920606 48.867,39.9667381 48.880775,39.9423449 C48.89645,39.9135377 48.9145,39.8861243 48.9270875,39.8556909 C48.940625,39.8243282 48.948225,39.7918039 48.957725,39.7592796 C48.9655625,39.7334925 48.975775,39.7088669 48.9812375,39.6823829 C48.9935875,39.6219806 49,39.5611137 49,39.5000145 L49,39.5000145 C49,39.4993176 48.9997625,39.4986206 48.9997625,39.4979237 C48.999525,39.4377537 48.99335,39.3773515 48.9812375,39.3181108 C48.9755375,39.2902328 48.96485,39.2644457 48.9565375,39.2370324 C48.947275,39.2061343 48.94015,39.1747716 48.927325,39.1448028 C48.91355,39.1125108 48.895025,39.083239 48.877925,39.0528055 C48.8651,39.0300385 48.8548875,39.0068069 48.8401625,38.9849691 C48.8054875,38.9336272 48.7655875,38.88577 48.721175,38.8423269 L42.0042,32.2721877 C41.633225,31.9093095 41.0316375,31.9093095 40.6606625,32.2719554 C40.2896875,32.6348335 40.2896875,33.2232909 40.6606625,33.5864014 L45.7564625,38.570749 L30.95,38.570749 C30.4253625,38.570749 30,38.9868277 30,39.5000145 C30,40.0132014 30.4253625,40.42928 30.95,40.42928 Z"
                                            id="Path"
                                            transform="translate(39.500000, 39.500000) scale(-1, 1) translate(-39.500000, -39.500000) ">
                                        </path>
                                    </g>
                                </g>
                            </g>
                        </g>
                    </svg>
                </button>
                <button class="next">
                    <svg width="19px" height="15px" viewBox="0 0 19 15" version="1.1" xmlns="http://www.w3.org/2000/svg"
                        xmlns:xlink="http://www.w3.org/1999/xlink">
                        <title>Path</title>
                        <g id="Welcome" stroke="none" stroke-width="1" fill="none" fill-rule="evenodd">
                            <g id="Summer-Sale-Desktop" transform="translate(-1027.000000, -2721.000000)" fill="#000000"
                                fill-rule="nonzero">
                                <g id="Social-Proof" transform="translate(240.000000, 2154.000000)">
                                    <g id="Group-49" transform="translate(681.000000, 535.000000)">
                                        <path
                                            d="M106.95,40.42928 L121.7567,40.42928 L116.6609,45.41386 C116.289925,45.7767382 116.289925,46.3651955 116.660663,46.7278414 C117.031638,47.0907195 117.633463,47.0907195 118.004437,46.7278414 L124.72165,40.1570052 L124.72165,40.1570052 C124.765825,40.1137944 124.80525,40.0661695 124.839925,40.0155245 C124.855838,39.9920606 124.867,39.9667381 124.880775,39.9423449 C124.89645,39.9135377 124.9145,39.8861243 124.927087,39.8556909 C124.940625,39.8243282 124.948225,39.7918039 124.957725,39.7592796 C124.965563,39.7334925 124.975775,39.7088669 124.981238,39.6823829 C124.993588,39.6219806 125,39.5611137 125,39.5000145 L125,39.5000145 C125,39.4993176 124.999763,39.4986206 124.999763,39.4979237 C124.999525,39.4377537 124.99335,39.3773515 124.981237,39.3181108 C124.975538,39.2902328 124.96485,39.2644457 124.956537,39.2370324 C124.947275,39.2061343 124.94015,39.1747716 124.927325,39.1448028 C124.91355,39.1125108 124.895025,39.083239 124.877925,39.0528055 C124.8651,39.0300385 124.854888,39.0068069 124.840162,38.9849691 C124.805487,38.9336272 124.765587,38.88577 124.721175,38.8423269 L118.0042,32.2721877 C117.633225,31.9093095 117.031638,31.9093095 116.660663,32.2719554 C116.289687,32.6348335 116.289687,33.2232909 116.660663,33.5864014 L121.756462,38.570749 L106.95,38.570749 C106.425363,38.570749 106,38.9868277 106,39.5000145 C106,40.0132014 106.425363,40.42928 106.95,40.42928 Z"
                                            id="Path"></path>
                                    </g>
                                </g>
                            </g>
                        </g>
                    </svg>
                </button>
            </div>
        </div>

        <div class="product__additional-info">
            <p></p>
        </div>

        <div class="product__color-variants">
            <div class="color-variants__header">
                <h3 class="color-variants__header--label">COLOR :</h3>
                <h3 class="color-variants__header--selected">Yellow</h3>
            </div>
            <div class="color-variants__images">
                <div class="variant" v-for="variant in product.variants" :key="variant.id">
                    {{ variant.title.split('')[0] }}
                </div>
            </div>
        </div>
        <div v-if="product.sizes" class="product__size-variants">
            <div class="size-variants__header">
                <h3 class="size-variants__header--label">Size :</h3>
                <h3 class="size-variants__header--selected">30</h3>
            </div>
            <div class="size-variants__info"></div>
        </div>

        <div class="product__add-to-cart">
            <div class="product__add-to-cart__price">{{ product.price }}</div>
            <button class="product__add-to-cart__btn" @click="addToCart()">
                Add to Bag
            </button>
        </div>
        <p class="product__add-to-cart__disclaimer">
            Free shipping for orders over $49 | Returns are easy and free
        </p>
    </div>

</template>

<script>

const ModalCart = {
    name: 'Modal Cart',
    props: ['product'],
    emits: ['added'],
    data() {
        return {
            stars: [1, 2, 3, 4, 5]
        }
    },
    created() {
        console.log(this.product);
    },
    methods: {
        async addToCart() {
            let formData = {
                'items': [{
                    'id': `${this.product.variants[0].id}`,
                    'quantity': 1,
                    properties: {}
                }]
            };
            const myDat = await fetch(window.Shopify.routes.root + 'cart/add.js', {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json'
                },
                body: JSON.stringify(formData)
            })
                .then(response => {
                    console.log('response in 1990')
                    return response.json();
                })
                .catch((error) => {
                    console.error('Error:', error);
                });
            console.log('myDat', myDat)
            this.$emit('added')
        }
    }
}

export default ModalCart;
</script>

<style lang="scss">
@mixin displayFlex($justify) {
    display: flex;
    justify-content: $justify
}


.mimic-cart {
    position: fixed;
    right: 0;
    top: 0;
    bottom: 0;
    width: 36.8rem;
    background-color: #ffffff;
    padding: 1.4rem 1.6rem 1.6rem;

    .product {
        &__summary {
            &__title {
                @include displayFlex(space-between);
                padding-bottom: 0.8rem;

                .title {
                    font-size: 20px;
                    font-weight: 700;
                    line-height: 1.4;
                    max-width: 280px;
                    text-align: left;
                    margin-bottom: 0;
                }
            }

            .close {
                padding: 0;
            }

            &__info {
                @include displayFlex(space-between);
                align-items: baseline;
            }
        }

        &__price {
            letter-spacing: .2rem;
            line-height: 1.143;
            font-weight: 700;
            margin-right: .4rem;
            font-size: 1.2rem;

        }

        &__original-price {
            font-size: 12px;
            // text-decoration: line-through;
        }

        &__images {
            display: flex;
            position: relative;
            height: 300px;
            margin-bottom: 12px;
            margin-top: 12px;

            &__container {
                @include displayFlex(none);
                overflow: auto;
                scroll-snap-type: x mandatory;
                width: 26.5rem;
                position: absolute;
                top: 0;
                left: 10.5%;
                z-index: 1;
            }

            &__slide {
                height: 300px;
                width: 26.5rem;
                background-color: aquamarine;
                flex: 1 0 auto;

                .image {
                    height: 100%;
                    width: 100%;
                }
            }

            &__buttons {
                width: 360px;
                display: flex;
                justify-content: space-between;
                align-items: center;
            }

        }

        &__additional-info {
            font-size: 14px;
            letter-spacing: .1px;
            line-height: 1.714;
        }


        &__reviews {
            display: flex;
            &__ratings{
                line-height: 1.3rem;
            }
            &__review-count {
                font-size: 1.2rem;
                line-height: 1.333;
                margin: 0 0 0 0.25rem;
            }
        }

        &__color-variants,
        &__size-variants {

            .color-variants,
            .size-variants {
                &__header {
                    display: flex;

                    &--label {
                        font-size: 12px;
                        letter-spacing: 2px;
                        line-height: 1.333;
                        margin: 0;
                        margin-right: 8px;
                    }

                    &--selected {
                        font-size: 14px;
                        font-weight: 700;
                        letter-spacing: 0;
                        line-height: 1.143;
                    }
                }

                &__images {
                    .variant {
                        display: inline-flex;
                        justify-content: center;
                        align-items: center;
                        text-transform: uppercase;
                        height: 3rem;
                        width: 3rem;
                        border: 1px solid #d5d4d4;
                    }
                }
            }
        }

        &__add-to-cart {
            @include displayFlex(space-around);

            &__price {
                display: flex;
                align-items: center;
            }

            &__btn {
                font-size: 14px;
                font-weight: 700;
                height: 40px;
                letter-spacing: 3px;
                line-height: 1.143;
                padding: 0;
                width: 255px;
                background-color: #27863a;
                border-color: #27863a;
                color: #fff;
            }

            &__disclaimer {
                font-size: 10px;
                letter-spacing: .1px;
                line-height: 1.6;
                margin-top: 8px;
                text-align: center;
            }
        }
    }

}
</style>