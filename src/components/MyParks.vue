<template>
  <section>
    <h1>My Saved Parks</h1>
    <h2 v-if="!$store.state.email">Sign in with your email to view your saved parks.</h2>
    <h2 v-else-if="!$store.state.savedParks.length">Save a park to view it here!</h2>
    <article v-else>
      <section :key='i' v-for='(result, i) in $store.state.savedParks'>
        <results-list-item :result='result'></results-list-item>
      </section>
    </article>
  </section>
</template>

<script>
import ResultsListItem from './ResultsListItem.vue';
export default {
  components: { ResultsListItem }
}
</script>