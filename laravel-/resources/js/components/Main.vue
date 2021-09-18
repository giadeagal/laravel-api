<template>
    <main class="container">
        <div class="row">
            <div class="col-6">
                <div class="card text-center m-5">
                <div class="card-header">
                    categoria
                </div>
                <div class="card-body">
                    <h5 class="card-title">titolo</h5>
                    <p class="card-text">contenuto Lorem ipsum dolor sit amet, consectetur adipisicing elit. Numquam asperiores illo aspernatur eum dolore officia quia harum impedit vitae eos.</p>
                    <a href="#" class="btn btn-primary">dettagli</a>
                </div>
                <div class="card-footer text-muted">
                    tags
                </div>
            </div>
            </div>
            <div class="col-6">
                <div class="card text-center m-5">
                <div class="card-header">
                    categoria
                </div>
                <div class="card-body">
                    <h5 class="card-title">titolo</h5>
                    <p class="card-text">contenuto Lorem ipsum dolor sit amet, consectetur adipisicing elit. Numquam asperiores illo aspernatur eum dolore officia quia harum impedit vitae eos.</p>
                    <a href="#" class="btn btn-primary">dettagli</a>
                </div>
                <div class="card-footer text-muted">
                    tags
                </div>
            </div>
            </div>
        </div>
    </main>
</template>

<script>
export default{
    name: "Main",
    data() {
        return{
            call: 'http://localhost:8000/api/posts'
        }
    },
    created(){

    },
    methods(){
        
    }
}
</script>

<style lang="scss" scoped>

</style>
