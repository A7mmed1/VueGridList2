<template>
    <div class="product">
        <slot> </slot>
    </div>
</template>

<script>

export default {
    props: ['name','price']

}
</script>

<style lang="scss" scoped>
.product{
    padding: 1rem;
    margin: 1rem;
    border: 1px solid #ccc;
    // box-shadow: 3px 3px 8px rgba(0,0,0.2);
}
</style>
