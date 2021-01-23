<template>
    <div>
        <h1>Hello From results route {{ $route.params.id }}</h1>
        {{ albumDatas }}
    </div>
</template>

<script>
import axios from 'axios'
export default {
    // middleware: 'search'
    asyncData({params}) {
        return axios
        .get(`https://itunes.apple.com/search?term=${params.id}&entity=album`)
        .then(response => {
            return { albumDatas: response.data.results }
        });
    },
}
</script>