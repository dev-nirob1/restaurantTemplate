<script setup>
import BaseButton from '../Elements/BaseButton.vue';
import BaseTitle from '../Elements/BaseTitle.vue'
import InputField from '../Elements/InputField.vue'

</script>
<template>
  <section id="reservation" class="reservation-section">
    <div class="reservation-container">
      <!-- Left: Form -->
      <div class="reservation-form">
        <BaseTitle>Reserve a Table</BaseTitle>
        <BaseParagraph>Book your table and enjoy a delightful dining experience.</BaseParagraph>
        <form>
          <div class="form-row">
            <InputField type="text" placeholder="Full Name" required />
            <InputField type="tel" placeholder="Phone Number" required />
          </div>
          <div class="form-row">
            <InputField type="date" required />
            <InputField type="time" required />
          </div>
          <textarea placeholder="Special Requests (Optional)"></textarea>
          <BaseButton type="submit" class="bg-primary text-white width-full">Book Now</BaseButton>
        </form>
      </div>

      <!-- Right: Image -->
      <div class="reservation-image">
        <img src="https://images.unsplash.com/photo-1555992336-03a23c4a4e6b?auto=format&fit=crop&w=800&q=80" alt="Reservation" />
      </div>
    </div>
  </section>
</template>


<style scoped>
/* Section base */
.reservation-section {
  padding: 4rem 1rem;
  background-color: #f9f9f9;
}

/* Layout */
.reservation-container {
  max-width: 1100px;
  margin: auto;
  display: flex;
  flex-wrap: wrap;
  gap: 2rem;
  align-items: center;
  justify-content: center;
}

/* Form Styling */
.reservation-form {
  flex: 1 1 450px;
}

.reservation-form h2 {
  font-size: 2rem;
  margin-bottom: 0.5rem;
  color: #333;
}

.reservation-form p {
  margin-bottom: 1.5rem;
  color: #666;
}

.reservation-form form {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.form-row {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
}

.form-row input {
  flex: 1;
  padding: 0.75rem;
  font-size: 1rem;
  border: 1px solid #ccc;
  border-radius: 6px;
}

textarea {
  width: 100%;
  padding: 0.75rem;
  font-size: 1rem;
  border: 1px solid #ccc;
  border-radius: 6px;
  resize: vertical;
  min-height: 100px;
}
/* Image Styling */
.reservation-image {
  flex: 1 1 400px;
  text-align: center;
}

.reservation-image img {
  width: 100%;
  max-width: 500px;
  border-radius: 12px;
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
}

/* Responsive */
@media (max-width: 768px) {
  .reservation-container {
    flex-direction: column;
  }

  .form-row {
    flex-direction: column;
  }
}
</style>
