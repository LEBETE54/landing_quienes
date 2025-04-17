<script setup>
    import { Link } from '@inertiajs/vue3';
    import { ref } from 'vue';
    import Image from 'primevue/image';
    const addclass = ref('-translate-y-full');
    const showicon = ref(true);
    
    function toggleMenu () {        
        addclass.value = addclass.value === '-translate-y-full' ?  'translate-y' : addclass.value = '-translate-y-full';
        addclass.value === '-translate-y-full' ? document.body.classList.remove('overflow-hidden') : document.body.classList.add('overflow-hidden');
        addclass.value === '-translate-y-full' ? showicon.value = true : showicon.value = false;
    }
    
</script>

<template>
    <aside class="bg-[#0a2320] h-[3.5rem] flex items-center justify-between px-4 py-2 sticky z-30">
        <Image src="images/gobmx_logo.png" alt="Image" width="120"/>
        <ul class="flex gap-3 text-white list-none">
            <li><a href="https://www.gob.mx/gobierno" target="_blank">Gobierno</a></li>
            <li><Link :href="''">Participa</Link></li>
            <li><Link :href="''">Datos</Link></li>
        </ul>        
    </aside>
    <header class="px-5 bg-white shadow-sm h-[4rem] flex items-center justify-between sticky top-0 z-30">
        <div class="flex items-center gap-4">
            <Image src="images/itcancun.png" alt="Image" width="40"/>
            <Image src="images/mexico_tecnm.jpg" alt="Image" width="120"/>
            <Image src="images/educacion-gob.png" alt="Image" width="120"/>
        </div>
        <button type="button" class="cursor-pointer" @click="toggleMenu">      
            <template v-if="showicon">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" class="size-5">
                    <path fill-rule="evenodd" d="M2 4.75A.75.75 0 0 1 2.75 4h14.5a.75.75 0 0 1 0 1.5H2.75A.75.75 0 0 1 2 4.75ZM2 10a.75.75 0 0 1 .75-.75h14.5a.75.75 0 0 1 0 1.5H2.75A.75.75 0 0 1 2 10Zm0 5.25a.75.75 0 0 1 .75-.75h14.5a.75.75 0 0 1 0 1.5H2.75a.75.75 0 0 1-.75-.75Z" clip-rule="evenodd" />
                </svg>
            </template>
            <template v-else>
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" class="size-5">
                    <path d="M6.28 5.22a.75.75 0 0 0-1.06 1.06L8.94 10l-3.72 3.72a.75.75 0 1 0 1.06 1.06L10 11.06l3.72 3.72a.75.75 0 1 0 1.06-1.06L11.06 10l3.72-3.72a.75.75 0 0 0-1.06-1.06L10 8.94 6.28 5.22Z" />
                </svg>
            </template>
        </button>
    </header>

    <nav class="
        grid w-full min-h-[calc(100vh-7.5rem)] max-h-[calc(100vh-7.5rem)] overflow-y-auto grid-cols-1 gap-4 px-10 py-6 bg-white justify-items-start sm:justify-items-center sm:grid-cols-3 absolute left-0 transition-transform duration-300"
        :class="addclass">
        <div v-for="item in 50">
            <ul>
                <li>Menu {{ item }}</li>
                <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quae possimus consequuntur fugit, voluptatibus impedit voluptates asperiores, laudantium cum neque maiores sint voluptate. Animi eaque, porro molestiae quidem suscipit quam nulla!</p>
            </ul>
        </div>
    </nav>
    

    <main class="container px-[5rem] py-5 mx-auto">
        <slot />
        <!-- <div v-for="item in 10" class="h-[30rem] bg-green-700">
            Holis
        </div> -->
    </main>
</template>