<script>
export default {
data() {
return {

}
},
props: {
    title: {
        typeof: String,
        required: true
    },
    language: {
        typeof: String,
        required: true
    },
    content: {
        typeof: String,
        required: true
    },
    finished: {
        typeof: Boolean,
        required: true
    },
    image_url: {
        typeof: String,
        required: true
    },
    website: {
        typeof: String,
        required: true
    },
    technologies: {
        typeof: Array,
        required: true
    },
    type: {
        typeof: Array,
        required: true
    }
}
}
</script>

<template>
    <div class="container-fluid my-4">
        <div class="row justify-content-center">
            <div class="card col-4" style="width: 18rem;">
                <img :src="image_url" class="card-img-top p-2" :alt="title">
                <div class="card-body">
                    <h5 class="card-title">{{ title }}</h5>
                    <h6>Language: <span class="badge text-bg-secondary">{{ language }}</span></h6>
                    <div>
                        <span v-for="technology in technologies" class="badge text-bg-primary mx-1">{{ technology.name }}</span>
                    </div>
                    <div>
                        <span class="badge text-bg-success mx-1">{{ type.name }}</span>
                    </div>
                    <p class="card-text">{{ content }}</p>
                    <a :href="website" class="btn btn-primary">website</a>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
    
</style>