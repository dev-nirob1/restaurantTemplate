<script setup>
import BaseParagraph from '../Elements/BaseParagraph.vue';
import BaseTitle from '../Elements/BaseTitle.vue';
import ListItem from '../Elements/ListItem.vue';
</script>

<template>
  <!-- ======== Why Choose Us section ======== -->
  <section class="statistics bg-light">
    <div class="container">
      <ul class="small-2 larger-3 justify-center align-center gap-2">
        <!-- Dishes Served -->
        <ListItem class="flex-center">
          <i class="fa-solid fa-utensils fa-3x"></i>
          <div>
            <BaseTitle>15k+</BaseTitle>
            <BaseParagraph>Dishes Served</BaseParagraph>
          </div>
        </ListItem>

        <!-- Happy Customers -->
        <ListItem class="flex-center">
          <i class="fa-solid fa-smile-beam fa-3x"></i>
          <div>
            <BaseTitle>10k+</BaseTitle>
            <BaseParagraph>Happy Customers</BaseParagraph>
          </div>
        </ListItem>

        <!-- Years of Culinary Excellence -->
        <ListItem class="flex-center">
          <i class="fa-solid fa-award fa-3x"></i>
          <div>
            <BaseTitle>20+</BaseTitle>
            <BaseParagraph>Years of Culinary Excellence</BaseParagraph>
          </div>
        </ListItem>
      </ul>
    </div>
  </section>
</template>


<style scoped>
.statistics {
  padding: 3.75rem 0;
}
.statistics ul {
  padding: 0;
}

.statistics ul li {
  gap: 1rem;
  padding: 2rem .5rem;
  background-color: var(--white-color);
  color: var(--primary-color)
}
.statistics ul i {
  height: 80px;
  width: 80px;
  line-height: 80px;
  text-align: center;
  color: var(--alternative-color);
}
.statistics ul p {
  margin: 0;
}
</style>