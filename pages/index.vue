<script setup lang="ts">
import useAsset from "@/helpers/useAsset"
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel'
import 'vue3-carousel/dist/carousel.css'
import { ref } from 'vue'
import { Tabs, Tab } from 'flowbite-vue'
const activeTab = ref('first')

useHead({ title: "Trang chủ" })
const pictures = [
    {
        'src': useAsset('images/home/z2161740555616_cf6d683f88aa9447af57b89917e84acb.jpg'),
        'alt': 'Picture 1',
    },
    {
        'src': useAsset('images/home/z2161740555387_88fc044837bea7695ee9ec8320a39cef.jpg'),
        'alt': 'Picture 2',
    },
]
const handlePaneClick = (): void => {
    console.log("Click!")
    console.log("Click!")
    console.log("Click!")

}
</script>

<template>
    <carousel :autoplay="3000" :wrap-around="true" class="relative slideshow" ref="slideshow">
        <slide v-for="(item, index) in pictures" :key="index">
            <img :src="item.src" :alt="item.alt" class="carousel-image" />
        </slide>
        <template #addons>
            <navigation />
            <pagination class="sm:block hidden" />
        </template>
    </carousel>
    <div
        class="relative bg-[url('/images/pattern.png')] bg-repeat bg-top max-w-full flex flex-wrap items-center justify-center">
        <div class="relative w-full">
            <img src="/images/background-header.png" alt="Top header">
        </div>
        <div class="flex flex-wrap lg:gap-x-32 gap-5 justify-center items-center py-5">
            <div class="flex items-center justify-between gap-x-10 relative">
                <div class="w-[114px] h-[130px] sm:block hidden">
                    <img class="absolute -top-10 left-0" :src="useAsset('images/home/icon-ticket.png')" alt="ticket banner">
                </div>
                <h2
                    class="uppercase font-bold text-[#e00d7a] leading-[32px] text-[32px] text-shadow-xs text-shadow font-Futurab">
                    mua vé <br>
                    online
                </h2>
            </div>
            <div class="grid grid-cols-2 gap-5">
                <select-search model-value=""
                    class="rounded-tr-[24px] rounded-br-[24px] rounded-bl-[24px] sm:w-[300px] w-[45vw] py-[10px] border-0 uppercase"
                    :options="[
                        { label: 'Cô thư ký và anh giám đốc', value: '1' },
                        { label: 'Em hàng xóm xinh đẹp', value: '2' },
                        { label: 'Tiếp viên hàng không xinh đẹp', value: '3' },
                    ]" placeholder="Chọn phim" />
                <select-search model-value=""
                    class="rounded-tl-[24px] rounded-bl-[24px] rounded-br-[24px] sm:w-[300px] w-[45vw] py-[10px] border-0 uppercase"
                    :options="[
                        { label: 'Cô thư ký và anh giám đốc', value: '1' },
                        { label: 'Em hàng xóm xinh đẹp', value: '2' },
                        { label: 'Tiếp viên hàng không xinh đẹp', value: '3' },
                    ]" placeholder="Chọn rạp" />
                <select-search model-value=""
                    class="rounded-tl-[24px] rounded-tr-[24px] rounded-br-[24px] sm:w-[300px] w-[45vw] py-[10px] border-0 uppercase"
                    :options="[
                        { label: 'Cô thư ký và anh giám đốc', value: '1' },
                        { label: 'Em hàng xóm xinh đẹp', value: '2' },
                        { label: 'Tiếp viên hàng không xinh đẹp', value: '3' },
                    ]" placeholder="Chọn ngày" />
                <select-search model-value=""
                    class="rounded-tl-[24px] rounded-tr-[24px] rounded-bl-[24px] sm:w-[300px] w-[45vw] py-[10px] border-0 uppercase"
                    :options="[
                        { label: 'Cô thư ký và anh giám đốc', value: '1' },
                        { label: 'Em hàng xóm xinh đẹp', value: '2' },
                        { label: 'Tiếp viên hàng không xinh đẹp', value: '3' },
                    ]" placeholder="Chọn suất chiếu" />
            </div>
        </div>
        <div>

        </div>
    </div>
    <div class="bg-gradient-to-tr from-[#4E0045] to-[#23001C] relative">
        <div>

        </div>
        <div class="flex justify-center items-center gap-x-10 py-10">
            <nuxt-link class="z-10 hover:opacity-[0.5] hover:transition-all hover:duration-300 hover:ease-in-out" to="/">
                <img :src="useAsset('images/home/dolby.png')" :alt="useAsset('images/home/dolby.png')">
            </nuxt-link>
            <nuxt-link class="z-10 hover:opacity-[0.5] hover:transition-all hover:duration-300 hover:ease-in-out" to="/">
                <img :src="useAsset('images/home/christie.png')" :alt="useAsset('images/home/christie.png')">
            </nuxt-link>
            <nuxt-link class="z-10 hover:opacity-[0.5] hover:transition-all hover:duration-300 hover:ease-in-out" to="/">
                <img :src="useAsset('images/home/2d.png')" :alt="useAsset('images/home/2d.png')">
            </nuxt-link>
            <nuxt-link class="z-10 hover:opacity-[0.5] hover:transition-all hover:duration-300 hover:ease-in-out" to="/">
                <img :src="useAsset('images/home/3d3.png')" :alt="useAsset('images/home/3d3.png')">
            </nuxt-link>
        </div>
        <div class="relative z-10 tabs">
            <tabs v-model="activeTab">
                <tab name="first" title="Phim đang chiếu" class="!text-[#000]">
                    <div class="bg-red-400">
                        Lorem...
                    </div>
                </tab>
                <tab name="second" title="Phim sắp chiếu">
                    <div class="bg-red-400">
                        Lorem...
                    </div>
                </tab>
                <tab name="third" title="Suất chiếu đặc biệt">
                    <div class="bg-red-400">
                        Lorem...
                    </div>
                </tab>
            </tabs>
        </div>
        <div class="absolute top-0 left-0 h-full w-full bg-no-repeat bg-center bg-[url('/images/bg-top.png')] z-1"></div>
    </div>
</template>
<style>
.slideshow .carousel__pagination {
    gap: 10px;
    position: absolute;
    top: 50%;
    right: 10px;
    transform: translateY(-50%);
}

.slideshow .carousel__prev,
.slideshow .carousel__next {
    width: 30px;
    height: 30px;
    background: #fff;
    border-radius: 50%;
    display: none;
}

.slideshow .carousel__pagination-button--active {
    border: 1px solid rgba(255, 255, 255, 0.8);
    border-radius: 50%;
    transform: translateY(0);
}

.slideshow .carousel__pagination-button::after {
    background-color: white;
    border-radius: 50%;
    width: 15px;
    height: 15px;
}

@media all and (max-width: 1024px) {
    .slideshow .carousel__pagination {
        right: auto;
        bottom: 10%;
        top: auto;
        left: 10px;
        transform: none;
    }

    .slideshow .carousel__pagination-button::after {
        height: 10px;
        width: 10px;
    }
}

.slideshow .carousel__pagination {
    display: flex;
}

@media all and (max-width: 767px) {
    .slideshow .carousel__pagination {
        display: none;
    }

    .slideshow .carousel__prev,
    .slideshow .carousel__next {
        display: flex;
    }
}

.tabs ul {
    justify-content: center;
}

.tabs ul li {
    background-color: #f18720;
    -webkit-transition: all 0.3s ease-in-out;
    box-shadow: 10px 0 0 rgba(0,0,0,0.1);
}

.tabs ul li:nth-child(1) {
    border-radius: 30px 50px 50px 0;
    -webkit-border-radius: 30px 50px 50px 0;
}

.tabs li:nth-child(2) {
    border-radius: 0 50px 50px 0;
    -webkit-border-radius: 0 50px 50px 0;
    padding-left: 55px;
    margin-left: -80px;
}

.tabs ul li:nth-child(3) {
    padding-left: 55px;
    margin-left: -80px;
    border-radius: 0 30px 0 0;
    -webkit-border-radius: 0 30px 0 0;
}

.tabs ul li div {
    font-family: 'avantgarde-demi';
    font-weight: normal;
    color: #fff;
    font-size: 30px;
    text-transform: uppercase;
    line-height: 74px;
    transition: all 0.3s ease-in-out;
    -webkit-transition: all 0.3s ease-in-out;
    padding: 0 45px;
}
</style>

<style scoped>
.text-shadow {
    text-shadow: 4px 4px 0 rgba(0, 0, 0, 0.1);
}
</style>