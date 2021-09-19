<template>
    <main class="container">
        <p>pagina {{ currentPage }} di {{ lastPage }}</p>
        <nav aria-label="Page navigation example">
  <ul class="pagination">
    <li class="page-item"><a class="page-link" href="#" @click="getPosts(currentPage - 1)">Previous</a></li>
    <li class="page-item"><a class="page-link" href="#" @click="getPosts(1)">1</a></li>
    <li class="page-item"><a class="page-link" href="#" @click="getPosts(2)">2</a></li>
    <li class="page-item"><a class="page-link" href="#" @click="getPosts(3)">3</a></li>
    <li class="page-item"><a class="page-link" href="#" @click="getPosts(currentPage + 1)">Next</a></li>
  </ul>
</nav>
        <div class="row">
            <div class="col-6" v-for="post,i in posts" :key="i">
                <div class="card text-center  my-3" >
                <div class="card-header">
                   
                </div>
                <div class="card-body">
                    <h5 class="card-title">{{post.title}}</h5>
                    <p class="card-text">{{post.content}}</p>
                    <a href="#" class="btn btn-primary">dettagli</a>
                </div>
                <div class="card-footer text-muted">
                
                </div>
            </div>
            </div>
        
        </div>
        <nav aria-label="Page navigation example">
  <ul class="pagination">
    <li class="page-item"><a class="page-link" href="#" @click="getPosts(currentPage - 1)">Previous</a></li>
    <li class="page-item"><a class="page-link" href="#" @click="getPosts(1)">1</a></li>
    <li class="page-item"><a class="page-link" href="#" @click="getPosts(2)">2</a></li>
    <li class="page-item"><a class="page-link" href="#" @click="getPosts(3)">3</a></li>
    <li class="page-item"><a class="page-link" href="#" @click="getPosts(currentPage + 1)">Next</a></li>
  </ul>
</nav>
    </main>
</template>

<script>
export default{
    name: "Main",
    data() {
        return{
            call: 'http://localhost:8000/api/posts',
            posts: [],
            currentPage: 1,
            LastPage: null
        }
    },
    created(){
        this.getPosts();
    },
    methods: {
        getPosts(pagenum){
            axios.get(this.call, {
                params: {
                    page: pagenum
                }
            })
                .then(x => {
                    this.posts = x.data.content.data;
                    this.currentPage = x.data.content.current_page;
                    this.lastPage = x.data.content.last_page;
                })
        }
    }
}
</script>

<style lang="scss" scoped>

</style>
