<template>
	<section id="contact">
    <div class="container">
        <h2 class="text-center mb-5 section-heading text-success">Contact</h2>
        
        <div class="row justify-content-center">
            
            <!-- Map Column -->
            <div class="col-lg-6 mb-4 mb-lg-0">
                <div class="map-container shadow-lg">
                    <iframe 
                        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3861.328325695843!2d121.07722731484055!3d14.57723298980839!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3397c7e97d4b4a67%3A0x7d0a28f86f345a33!2sPasig%20City%20Hall!5e0!3m2!1sen!2sph!4v1633000000000!5m2!1sen!2sph" 
                        allowfullscreen="" 
                        loading="lazy" 
                        referrerpolicy="no-referrer-when-downgrade"
                        class="contact-map"
                        title="Pasig City Location">
                    </iframe>
                </div>
            </div>

            <!-- Contact Form Column -->
            <div class="col-lg-6">
                <form @submit.prevent="submitForm" class="contact-form shadow-lg">
                    <div class="mb-3">
                        <label for="contactName" class="form-label visually-hidden">Full Name</label>
                        <input v-model="name"
                            type="text" 
                            class="form-control" 
                            placeholder="First Name M.I. Last Name" 
                            id="contactName" 
                            required>
                    </div>
                    <div class="mb-3">
                        <label for="contactEmail" class="form-label visually-hidden">Email Address</label>
                        <input v-model="email"
                            type="email" 
                            class="form-control" 
                            placeholder="Email" 
                            id="contactEmail" 
                            required>
                    </div>
                    <div class="mb-3">
                        <label for="contactMessage" class="form-label visually-hidden">Message</label>
                        <textarea v-model="message"
                            class="form-control" 
                            placeholder="Message" 
                            id="contactMessage" 
                            rows="5" 
                            required>
                        </textarea>
                    </div>
                    
                    <div class="d-flex justify-content-between align-items-center mt-4">
                        <!-- Social Media Icons -->
                        <div class="social-icons">
                            <a href="https://www.linkedin.com/in/yourprofile" target="_blank" rel="noopener noreferrer" class="text-decoration-none me-3 social-link" title="LinkedIn">
                                <i class="fab fa-linkedin fa-2x"></i>
                            </a>
                            <a href="https://github.com/yourusername" target="_blank" rel="noopener noreferrer" class="text-decoration-none me-3 social-link" title="GitHub">
                                <i class="fab fa-github fa-2x"></i>
                            </a>
                            <a href="https://gitlab.com/yourusername" target="_blank" rel="noopener noreferrer" class="text-decoration-none social-link" title="GitLab">
                                <i class="fab fa-gitlab fa-2x"></i>
                            </a>
                        </div>
                        
                        <!-- Submit Button -->
                        <button type="submit" class="submit-btn pl-5 pr-5" :disabled="isLoading">{{isLoading ? "Sending ...": "Submit"}}</button>
                    </div>
                </form>
            </div>

        </div>
    </div>
</section>
</template>

<script setup>
import { ref } from "vue";
import { Notyf } from "notyf";
import 'notyf/notyf.min.css';

const WEB3FORMS_ACCESS_KEY = "f2a27b89-2bf1-49b7-8ab3-c79fa654cb59";
const name = ref("");
const email = ref("");
const message = ref("");

// Loading state
const isLoading =ref(false);

const notyf = new Notyf();

const submitForm = async () => {
    isLoading.value = true;
    try {
  const response = await fetch("https://api.web3forms.com/submit", {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
      Accept: "application/json",
    },
    body: JSON.stringify({
      access_key: WEB3FORMS_ACCESS_KEY,
      name: name.value,
      email: email.value,
      message: message.value,
    }),
  });

          const result = await response.json();
          if (result.success) {
            console.log(result);
            isLoading.value = false;

            notyf.success("Message Sent!")
          }
        }
        catch(error){
            console.log(error);
            isLoading.value = false;
            notyf.error("Failed to send message.")
    }
}
</script>