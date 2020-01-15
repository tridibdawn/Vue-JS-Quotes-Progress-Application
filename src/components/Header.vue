<template>
    <div>
        <h3>Progress</h3>
        <div class="progress">
            <div class="progress-bar" role="progressbar" aria-valuenow="75" aria-valuemin="0" aria-valuemax="100"
             :style="{width: (quoteCounts/maxQuotes) * 100 + '%'}">
                <span v-if="quoteCounts > 0">{{ quoteCounts }} / {{ maxQuotes }}</span>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['quoteCounts', 'maxQuotes']
}
</script>

<style scoped>

</style>