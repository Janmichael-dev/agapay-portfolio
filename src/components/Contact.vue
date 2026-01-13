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
                <form class="contact-form shadow-lg">
                    <div class="mb-3">
                        <label for="contactName" class="form-label visually-hidden">Full Name</label>
                        <input 
                            type="text" 
                            class="form-control" 
                            placeholder="First Name M.I. Last Name" 
                            id="contactName" 
                            required>
                    </div>
                    <div class="mb-3">
                        <label for="contactEmail" class="form-label visually-hidden">Email Address</label>
                        <input 
                            type="email" 
                            class="form-control" 
                            placeholder="Email" 
                            id="contactEmail" 
                            required>
                    </div>
                    <div class="mb-3">
                        <label for="contactMessage" class="form-label visually-hidden">Message</label>
                        <textarea 
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
                        <button type="submit" class="btn btn-success contact-submit-btn">Submit</button>
                    </div>
                </form>
            </div>

        </div>
    </div>
</section>
</template>