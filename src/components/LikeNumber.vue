<template>
<div>
    <p>{{number}}</p>
    <button @click="increment"></button>
</div>
</template>
<script>
exports default {
    data() {
        return {
            number: 5
        };
    }
}
</script>