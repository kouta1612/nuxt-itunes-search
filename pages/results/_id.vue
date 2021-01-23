<template>
    <div>
        <h1>Results for {{ $route.params.id }}</h1>
        <div v-for="(album, index) in albumDatas" :key="index">
            <card
                :title="album.collectionCensoredName"
                :image="album.artworkUrl100"
                :artistName="album.artistName"
                :uri="album.artistViewUrl"
                :color="picker(index)"
            />
        </div>
        <div v-if="albumExists">
            {{ albumDatas }}
        </div>
        <div v-else>
            <h1>Could Not Find Albums</h1>
        </div>
    </div>
</template>

<script>
import axios from 'axios'
import Card from '~/components/Card'
export default {
    asyncData({params}) {
        return axios
        .get(`https://itunes.apple.com/search?term=${params.id}&entity=album`)
        .then(response => {
            return { albumDatas: response.data.results }
        });
    },
    methods: {
        picker(index) {
            return index % 2 == 0 ? '#0345fc' : '#fc1303'
        }
    },
    computed: {
        albumExists() {
            return this.albumDatas.length > 0
        },
    },
    components: {
        Card
    }
}
</script>