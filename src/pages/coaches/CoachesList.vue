<script>
import CoachItem from '../../components/coaches/CoachItem.vue';
    export default {
        components: {
            CoachItem,
        },
        computed: {
            filteredCoaches() {
                return this.$store.getters['coaches/coaches'];
            },
            hasCoaches() {
                return this.$store.getters['coaches/hasCoaches'];
            }
        }
    }
</script>

<template>
    <section>FILTER</section>
    <section>
        <base-card>
        <div class="controls">
            <base-button mode="outline">Refresh</base-button>
            <base-button link to="/register">Register as a Reviewer</base-button>
        </div>

        <ul v-if="hasCoaches">
            <coach-item
            v-for="coach in filteredCoaches"
            :key="coach.id"
            :id="coach.id"
            :first-name="coach.firstName"
            :last-name="coach.lastName"
            :rate="coach.hourlyRate"
            ></coach-item>
        </ul>

        <h3 v-else>No Reviewers found</h3>
        </base-card>
    </section>
</template>

<style scoped>
    ul {
  list-style: none;
  margin: 0;
  padding: 0;
}

.controls {
  display: flex;
  justify-content: space-between;
}
</style>