<script setup>
import BaseButton from '../Elements/BaseButton.vue';
import BaseParagraph from '../Elements/BaseParagraph.vue';
import BaseTextArea from '../Elements/BaseTextArea.vue';
import BaseTitle from '../Elements/BaseTitle.vue'
import InputField from '../Elements/InputField.vue'

</script>
<template>
    <section id="reservation" class="reservation-section">
        <div class="container">
            <div class="medium-2 gap-2 align-center">
                <!-- reservation Form -->
                <div class="reservation-form">
                    <div class="mb-1">
                        <BaseTitle>Reserve a Table</BaseTitle>
                    <BaseParagraph>Book your table and enjoy a delightful dining experience.</BaseParagraph>
                    </div>

                    <form>
                        <div class="medium-2 gap-1">
                            <InputField type="text" placeholder="Full Name" required />
                            <InputField type="tel" placeholder="Phone Number" required />
                        </div>
                        <div class="medium-2 gap-1">
                            <InputField type="date" required />
                            <InputField type="time" required />
                        </div>
                        <BaseTextArea placeholder="Special Requests (Optional)"></BaseTextArea>
                        <BaseButton type="submit" class="bg-primary text-white width-full">Book Now</BaseButton>
                    </form>
                </div>
                <!-- Right: Image -->
                <div class="reservation-image">
                    <img src="https://cdn.pixabay.com/photo/2021/07/20/06/04/restaurant-6479818_1280.jpg"
                        alt="Restaurant Table" class="reservation-img" />
                </div>
            </div>
        </div>
    </section>
</template>


<style scoped>
.reservation-section {
    padding: 3.75rem 0;
}

.reservation-section input,
.reservation-section textarea {
    border-color: var(--border-color);
    padding: .9rem 1.5rem;
    border-radius: 1.5rem;
}

.reservation-section .btn {
    border-radius: 1.5rem;
    padding: .9rem 1.5rem;
}
.reservation-image{
    width: 100%;
    height: auto;
}
.reservation-image img{ 
    width: 100%;
    object-fit: cover;
 }
</style>
