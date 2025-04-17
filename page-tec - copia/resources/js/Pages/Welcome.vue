<script setup>
    import MainLayout          from '@/Layouts/MainLayout.vue';
    import  HighlightSecction  from '../Components/HighLightSecction.vue';

    const data = [
    {
        title: '¿Porque elegir el TecNM?',
        text1: 'El Instituto Tecnológico de Cancún es una institución de excelencia con más de 36 años formando profesionales capacitados. Ofrece planes de estudio actualizados, docentes expertos, infraestructura moderna, becas e intercambios internacionales, asegurando una fuerte vinculación con el sector productivo.',
        text2: 'Ser parte del TecNM Cancún te permite desarrollar tu talento en un entorno dinámico, con actividades culturales, deportivas y tecnológicas. Aquí impulsamos tu crecimiento profesional con educación de calidad y conexión directa con las empresas. ¡Tu éxito empieza aquí! 🚀',
        img: '/images/image-student.png',
        alt: 'Estudiante Tecnologico',
    },
];


</script>



<template>
    <MainLayout>
        <HighlightSecction :data="data" :imagePosition="false" /> 
    </MainLayout>
</template>