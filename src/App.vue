<template>
    <div>
        <comment-form @addComment="createComment" />
        <comment-list v-bind:comments="comments" />            
    </div>
</template>
<script>
import CommentList from './components/CommentList';
import CommentForm from './components/CommentForm';

export default {
    components:{
        CommentList,
        CommentForm
    },

    data() {
        return {
            comments: [
                {id: 1, name: "Botir Akhmedov", email: "botircoders@gmail.com", content: "Lorem ipsum dolor, sit amet consectetur adipisicing elit. Aspernatur, voluptatum."},
                {id: 2, name: "Aziza Haydarova", email: "haydarova@gmail.com", content: "Lorem ipsum dolor, consectetur adipisicing elit. Aspernatur, voluptatum."},
                {id: 3, name: "Davron Kamolov", email: "khamolov@gmail.com", content: "Lorem ipsum dolor, sit amet adipisicing elit. Aspernatur, voluptatum."}
            ],
            name: "",
            email: "",
            content: "",
        }
    },
        methods: {
            createComment(comment) {
                this.comments.push(comment);
            }
        },
}
</script>
<style>
.comment{
    padding: 10px;
    margin: 10px;
    border: 3px solid #ccc;
}
</style>