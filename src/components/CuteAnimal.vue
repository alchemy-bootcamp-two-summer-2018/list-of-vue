<template>
    <li>
        <h3>Meet {{ cuteAnimal.name }} the {{ cuteAnimal.type }}</h3>
    </li>
</template>

<script>
export default {
    props: {
        cuteAnimal: Object,
    }
};
</script>