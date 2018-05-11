<template>
	<div>
		<ul>
		 	<li v-for="(post, key) in posts" :key="post.id"> 
		 	{{post.title}} - {{ post.text }} </li>
		 	
        </ul>

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