<template>
  <div id="contact" class="py-32 flex align-center justify-evenly">
    <form class="contact-left" action="https://api.web3forms.com/submit" method="POST">
      
      <div class="contact-left-title text-transparent bg-clip-text bg-gradient-to-br from-indigo-600 via-pink-600 to-purple-600">
        <h2>Get in touch</h2>
        <hr>
      </div>
      <input type="hidden" name="access_key" value="">
      <input type="text" name="name" placeholder="Your Name" class="contact-inputs" required>
      <input type="email" name="email" placeholder="Your Email Address" class="contact-inputs" required>
      <textarea name="message" placeholder="Your Message" class="contact-inputs" required></textarea>
      <button type="submit" class="">Submit<i class="bi bi-arrow-right"></i></button>
    </form>
    <div class="contact-right">
      <i class="bi bi-envelope-at-fill message-icon text-transparent bg-clip-text bg-gradient-to-br from-indigo-600 via-pink-600 to-purple-600"></i>
    </div>
  </div>
</template>

<script>
export default {
};
</script>

<style scoped>

.contact-left {
  display: flex;
  flex-direction: column;
  align-items: start;
  gap: 20px;
}

.contact-left-title h2 {
  font-weight: 600;
  font-size: 40px;
  margin-bottom: 5px;
}

.contact-left-title hr {
  border: none;
  width: 120px;
  height: 5px;
  background-color: #a363aa;
  border-radius: 10px;
  margin-bottom: 20px;
}

.contact-inputs {
  width: 400px;
  height: 50px;
  border: none;
  outline: none;
  padding-left: 25px;
  font-weight: 500;
  color: #666;
  border-radius: 50px;
}

.contact-left textarea {
  height: 140px;
  padding-top: 15px;
  border-radius: 20px;
}

.contact-inputs:focus {
  border: 2px solid #9333ea;
}

.contact-inputs::placeholder {
  color: #a9a9a9;
}

.contact-left button {
  display: flex;
  align-items: center;
  padding: 15px 30px;
  font-size: 16px;
  color: #fff;
  gap: 10px;
  border: none;
  border-radius: 50px;
  background: linear-gradient(270deg, #4f46e5, #db2777);
}

.contact-left button img {
  height: 15px;
}

.contact-right img {
  width: 500px;
}
@media (max-width:800px) {
  .contact-inputs {
    width: 80vw;
  }
  .contact-right {
    display: none;
  }
}

.message-icon {
  font-size: 15rem;
}

</style>
