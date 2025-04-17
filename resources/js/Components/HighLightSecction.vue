<script setup>

defineProps({

    data: {
        type: Array,
        required: true
    },

    imagePosition: {
        type: Boolean,
        default: false
    }
});

</script>


<template>
    <section v-for="(item, index) in data" :key="index"
        class="grid items-center w-full h-auto grid-cols-1 p-4 md:grid-cols-12 rounded-2xl">
        <div :class="[
            'md:col-span-3 flex justify-center items-center',
            imagePosition ? 'order-2 md:order-2' : 'order-1 md:order-1'
        ]">
            <div class="w-full max-w-[280px] h-[250px] overflow-hidden rounded-2xl">
                <img :src="item.img" :alt="item.alt" :width="120"
                class="object-center w-full h-full transition-transform duration-500 hover:scale-105" />
            </div>
        </div>
        <div :class="[
            'flex flex-col justify-center items-center space-y-3 md:col-span-8 bg-[#f8f9fa] shadow shadow:sm p-5',
            imagePosition ? 'order-1 md:order-1' : 'order-2 md:order-2'
        ]">
            <div class="text-center">
                <h1 class="text-[26px] font-bold">{{ item.title }}</h1>
            </div>
            <div class="w-auto h-auto space-y-3 text-center">
                <p class="leading-relaxed text-balance text-neutral-800">
                    {{ item.text1 }}
                </p>
                <p class="hidden leading-relaxed text-balance text-neutral-800 sm:block">
                    {{ item.text2 }}
                </p>
            </div>
        </div>
    </section>
</template>

