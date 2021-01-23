<template>
    <div>
        <v-container>
            <v-row dense>
                <v-col cols="12">
                    {{ uri }}
                    <v-card :color="color" target="_blank" :href="uri" dark>
                        <div class="d-flex flex-no-wrap justify-space-between">
                            <v-card-title class="headline" v-text="title"></v-card-title>
                            <v-card-subtitle v-text="artistName"></v-card-subtitle>
                            <v-avatar class="ma-3" size="125" tile>
                                <v-img :src="image"></v-img>
                            </v-avatar>
                        </div>
                    </v-card>
                </v-col>
            </v-row>
        </v-container>
    </div>
</template>

<script>
export default {
    props: ['title', 'image', 'artistName', 'uri', 'color'],
}
</script>