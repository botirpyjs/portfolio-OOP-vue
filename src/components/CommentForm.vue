<template>
    <div>
        <div class="w-75 mx-auto">
            <h1 class="text-center">Add comment</h1>
            <form @submit.prevent>
                <input v-model="comment.name" type="text" placeholder="Enter your name..." class="form-control">
                <input v-model="comment.email" type="email" placeholder="Enter your email..." class="form-control my-2">
                <input v-model="comment.content" type="text" placeholder="Enter your content..." class="form-control">
                <div class="d-flex flex-row-reverse">
                    <button @click="createComment" class="btn btn-danger mt-3 w-25" >Add commit</button>
                </div>
            </form>
        </div>        
    </div>
</template>
<script>
export default {
    data() {
        return {
            comment: {
                name: '',
                email: '',
                content: ''
            }
        }
    },
    methods: {
        createComment() {
            this.comment.id = Date.now();
            this.$emit('addComment', this.comment);
            this.comment = {
                name: '',
                email: '',
                content: ''
            }
        }
    },
}
</script>
<style>

</style>