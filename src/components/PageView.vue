<template>
    <div class="container">
            <h2>{{ page.pageTitle }}</h2>
            <p>{{page.content}}</p>
        </div>
</template>

<script>
export default{
    props:['page']
}
</script>
