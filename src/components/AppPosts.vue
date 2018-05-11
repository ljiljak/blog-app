<template>

	<div class="col-md-8 blog-main">
		<div class="blog-post" v-for="post in posts" :key="post.id">
    		<h2 class="blog-post-title">{{ post.title }}</h2>
    		<p class="card-text">{{ post.text }}</p>
    		<router-link class="nav-link" to="/post/${id}">View Post</router-link>
		</div>
	</div>

</template>

<script>

import {posts} from '../services/Posts.js'

export default {
 data () {
 	return {
 		posts: []
 		}
	},

	created() {
		posts.getAll() 
		.then((response) => {
			this.posts = response.data
		})
	}

}
	

</script>