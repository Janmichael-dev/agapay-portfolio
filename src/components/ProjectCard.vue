<template>
    <div class="col-lg-4 col-md-6 col-sm-12 mb-4">
        <div class="card project-card h-100">
            <img :src="project.image" class="card-img-top project-img" :alt="project.title">
            <div class="card-body d-flex flex-column">
                <h5 class="card-title fw-bold">
                    {{ project.title }}
                </h5>
                <p class="card-text project-description">
                    {{ project.description }}
                </p>
            </div>
        </div>
    </div>
</template>

<script setup>
import { defineProps } from 'vue';

defineProps({
    project: Object
});
</script>