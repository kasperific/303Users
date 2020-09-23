<template>
    <div class="user-card">
        <h2>{{user.name}}</h2>
        <div>
            <p>Username: {{user.username}}</p>
            <p>Email: {{user.email}}</p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'UserCard',
    props: [
        'user'
    ]
}
</script>

<style scoped>
    .user-card {
        padding: 1rem 4rem;
        background: tan;
        border-radius: 4px;
    }
</style>