/**
 * Ice Roller Dropship Theme - Main JavaScript
 */

document.addEventListener('DOMContentLoaded', function() {
  // Initialize all components
  initAddToCart();
  initTestimonialSlider();
  initCountdownTimer();
  initSmoothScroll();
  initIntersectionObserver();
});

// === ADD TO CART FUNCTIONALITY ===
function initAddToCart() {
  const forms = document.querySelectorAll('form[action="/cart/add"]');
  
  forms.forEach(form => {
    form.addEventListener('submit', function(e) {
      const button = this.querySelector('button[type="submit"]');
      const originalText = button.innerHTML;
      
      // Add loading state
      button.innerHTML = `
        <div style="display: flex; align-items: center; gap: 8px;">
          <div class="spinner"></div>
          Adding to Cart...
        </div>
      `;
      button.classList.add('loading');
      button.disabled = true;
      
      // Simulate processing
      setTimeout(() => {
        button.innerHTML = `
          <div style="display: flex; align-items: center; gap: 8px;">
            ✅ Added to Cart!
          </div>
        `;
        button.classList.remove('loading');
        
        // Optional: Open cart drawer or redirect
        setTimeout(() => {
          // window.location.href = '/cart';
          // Or trigger custom cart drawer
          document.body.classList.add('cart-open');
        }, 1000);
        
        // Reset button after 3 seconds
        setTimeout(() => {
          button.innerHTML = originalText;
          button.disabled = false;
        }, 3000);
      }, 1500);
    });
  });
}

// === TESTIMONIAL SLIDER ===
function initTestimonialSlider() {
  const sliders = document.querySelectorAll('.testimonials-grid');
  
  sliders.forEach(slider => {
    let currentIndex = 0;
    const slides = slider.querySelectorAll('.testimonial');
    const totalSlides = slides.length;
    
    if (totalSlides <= 1) return;
    
    setInterval(() => {
      slides[currentIndex].style.opacity = '0';
      slides[currentIndex].style.transform = '...
