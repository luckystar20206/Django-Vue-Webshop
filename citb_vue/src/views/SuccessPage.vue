<template>
    <div class="page-success">
        <div class="columns is-multiline">
            <div class="column is-12">
                <h1 class="title">Thank you</h1>

                <p>Your order will be processed as soon as possible.</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Success Page',
    mounted() {
        document.title = 'Success | Chef-in-the-Box'
    },
}
</script>