<template>
    <section class="recipes">
        <Recipe
        v-for="recipe in recipes"
        :key="recipe.id" 
        :thumbnail="recipe.thumbnail"
        :title="recipe.title"
        :id="recipe.id"
        :previewText="recipe.previewText"
        :description="recipe.description"/>
<!-- 
        <Recipe 
        thumbnail="https://post.healthline.com/wp-content/uploads/2020/07/pizza-beer-1200x628-facebook-1200x628.jpg"
        title="Pizza!!!"
        id="2"
        previewText="yum yum tasty!"/> -->
    </section>
</template>

<script>
import Recipe from '@/components/Recipe'

export default {
    components: {
        Recipe
    },
    asyncData() {
        // return axios.get()
        //since we are returning Nuxt will wait for this data to resolve
        return new Promise ((resolve,reject) => {
            setTimeout(() => {
                resolve({
                    recipes: [
                        {
                            id: "1",
                            title: "Delish",
                            preview: "yum yum",
                            description: 'kjsdfklsdhjfkldjsklfjs memememe',
                            thumbnail: "https://images.dailyhive.com/20201028135237/sugotoronto_119532360_649255475710285_1291059132088708725_n.jpg"
                        },
                        {
                            id: "2",
                            title: "Pizza",
                            preview: "yum yum tasy",
                            description: 'hsjkdhfjksdhfiusdhfjkhsdfjkhsdjkfhsjf IT ME!',
                            thumbnail: "https://post.healthline.com/wp-content/uploads/2020/07/pizza-beer-1200x628-facebook-1200x628.jpg"
                        }
                    ]
                })
            }, 1500);
        })
    },
    
}
</script>


<style>
.recipes {
    display: flex;
    flex-flow: wrap;
    justify-content: center;
    align-items: center;
}
a{
    text-decoration: none;
    color: black;
}
.recipe {
    box-sizing: border-box;
    width: 280px;
    padding: 8px;
    border: 1px solid #ccc;
    box-shadow: 0 2px 2px #aaa ;
    margin: 10px;
}
.thumb {
    width: 100%;
    background-size: cover;
    background-position: center;
    height: 200px;
}
</style>
