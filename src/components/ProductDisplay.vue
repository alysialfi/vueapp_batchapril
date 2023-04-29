<template>
    <div class="flex">
        <!-- layout 1 -->
        <div class="bg-gray-200 h-screen w-1/2 flex items-center justify-center">
            <img src="../assets/images/sofa.png" alt="the image of sofa">
        </div>
        <!-- layout 2 -->
        <div class="w-1/2 my-24 px-12 flex flex-col justify-between">
            <!-- layout 2a -->
            <div>
                <h1 class="font-semibold text-4xl">Greyana Sofa</h1>
                <p class="mt-4">Introducing the Greyana Sofa. The perfect combination of style and comfort. With its sleek and modern design, this sofa is a statement piece that will elevate any living space. The Greyana Sofa features a stunning grey upholstery that is both soft to the touch and durable for everyday use. Crafted with a sturdy wooden frame and high-density foam cushions, the Greyana Sofa offers unbeatable comfort and support. The seat and back cushions are also removable and reversible, making it easy to maintain and keep looking like new.</p>
            </div>
            <!-- layout 2b -->
            <div>
                <div class="font-semibold text-3xl">$75</div>
                <div class="flex">
                    <button @click="decreaseAmount()" class="bg-black w-8 h-6 text-white text-center">-</button>
                    <div class="bg-gray-100 border border-black w-8 h-6 text-black text-center">{{ amount }}</div>
                    <button @click="increaseAmount()" class="bg-black w-8 h-6 text-white text-center">+</button>
                </div>
                <div v-if="isItemExceedingMaxAmount" class="mb-16 text-xs mt-1 text-red-500">
                    <div>maximum items that can be added is 3</div>
                    <!-- <div>successfully added to cart</div> -->
                </div>
                <div class="mb-2">Subtotal: $0</div>
                <div class="flex gap-4">
                    <button class="bg-black text-white w-1/2 h-12">
                        Buy Now
                    </button>
                    <button @click="addToCart()" class="bg-black text-white w-1/2 h-12">
                        Add To Cart
                    </button>
                </div>
            </div>
        </div>
    </div>
</template>
  
<script>
    export default {
        name: 'ProductDisplay',
        data() {
            return {
                amount: 0,
                isItemExceedingMaxAmount: false
            }
        },
        methods: {
            increaseAmount() {
                this.amount += 1
            },
            decreaseAmount() {
                if (this.amount === 0) {
                    return
                }
                this.amount -= 1
            },
            addToCart() {
                if(this.amount >= 3) {
                    this.isItemExceedingMaxAmount = true
                }
            }
        },
    }
</script>
