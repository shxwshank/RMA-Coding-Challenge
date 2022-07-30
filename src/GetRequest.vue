<template>
  <div class="card-text-center-m-3">
    <ul>
        <li v-for="item in totalVuePackages" :key="item.name">
        <div class="Card">
        <img
        class="rounded-full-w-full"
            :src="item.avatar" />
            <div class="det">
        <h3 className="itemna">{{item.name}}</h3>
        <h3 class="itemjob">{{item.job}}</h3>
        </div>
        </div>
        </li>
    </ul>
  </div>
</template>
<style>
    
</style>

<script>
    export default {
        name: "get-request",
        data() {
            return {
            totalVuePackages: null
            };
        },
        created() {
        // Simple GET request using fetch
        fetch("https://62e3dff33c89b95396d2a865.mockapi.io/users")
            .then(response => response.json())
            .then(data => {
                this.totalVuePackages = data
            });
        }
    }
</script>