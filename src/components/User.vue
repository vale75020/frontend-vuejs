<template>
    <div class="user">
        <div class="user__identity">{{ info.firstname }} {{ info.lastname }}</div>
        <div class="user__city">{{ info.address.city }}</div>
        <div class="user__email">{{ info.username }}</div>
        <!--{{info}}-->
    </div>
</template>

<script>
    export default {
        name: 'User',
        props: ['info']
        //props : ['firstname', 'lastname', 'address']
    }
</script>

<style scoped lang="scss">
    .user {
        color: #333;
        &__identity {
            font-weight: bold;
            font-size: 30px;
        }
        &__email{
            font-size: 12px;
            color: green;
        }
    }
</style>