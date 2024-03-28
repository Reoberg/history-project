<script setup>

</script>

<template>
  <div class="footer">
    <div class="footer-content">
      <div class="footer-section">
        <h4>Quick Links</h4>
        <ul>
          <li><a href="#">Link 1</a></li>
          <li><a href="#">Link 2</a></li>
          <li><a href="#">Link 3</a></li>
        </ul>
      </div>
      <div class="footer-section">
        <h4>Contact Us</h4>
        <p>Email: example@example.com</p>
        <p>Phone: (123) 456-7890</p>
      </div>
      <div class="footer-section">
        <h4>Follow Us</h4>
        <div class="social-icons">
          <a href="#"><img src="/path-to-your-icon/facebook-icon.svg" alt="Facebook" /></a>
          <a href="#"><img src="/path-to-your-icon/twitter-icon.svg" alt="Twitter" /></a>
          <a href="#"><img src="/path-to-your-icon/instagram-icon.svg" alt="Instagram" /></a>
          <!-- Add more icons as needed -->
        </div>
      </div>
    </div>
    <div class="footer-bottom">
      <p>&copy; 2024 Your Site Name. All rights reserved.</p>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.footer {
  background-color: #333;
  color: #fff;
  text-align: center;
  padding: 20px 0;
}

.footer-content {
  display: flex;
  justify-content: space-around;
  margin-bottom: 20px;
}

.footer-section {
  h4 {
    margin-bottom: 15px;
  }

  ul {
    list-style: none;
    padding: 0;

    li {
      margin-bottom: 10px;

      a {
        color: #fff;
        text-decoration: none;

        &:hover {
          text-decoration: underline;
        }
      }
    }
  }
}

.social-icons {
  a {
    display: inline-block;
    margin-right: 10px;

    img {
      width: 24px;
      height: 24px;
    }
  }
}

.footer-bottom {
  font-size: 14px;
}
</style>