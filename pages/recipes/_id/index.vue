<template>
    <section class="single-recipe">
        <h1>{{recipe.title}}</h1>
        <div>
            <img :src="recipe.thumbnail" :alt="recipe.title">
            <p>{{recipe.description}}</p>
        </div>
    </section>
</template>

<script>
export default {
    //context is a special keyword from nuxt
    asyncData(context) {
        return new Promise ((resolve,reject) => {
            setTimeout(() => {
                resolve({
                    recipe: [
                        {
                            id: "1",
                            title: "Delish",
                            preview: "yum yum",
                            description: "kjsdfklsdhjfkldjsklfjs memememe",
                            thumbnail: "https://images.dailyhive.com/20201028135237/sugotoronto_119532360_649255475710285_1291059132088708725_n.jpg"
                        },
                        {
                            id: "2",
                            title: "Pizza",
                            preview: "yum yum tasy",
                            description: "hsjkdhfjksdhfiusdhfjkhsdfjkhsdjkfhsjf IT ME!",
                            thumbnail: "https://post.healthline.com/wp-content/uploads/2020/07/pizza-beer-1200x628-facebook-1200x628.jpg"
                        }
                    ].find(el => el.id === context.params.id)
                })
            }, 1500);
        })
    }
}
</script>
<style>
.single-recipe{
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 30px;
    flex-flow: column;
}
</style>