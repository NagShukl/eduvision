<template>
  <footer
    class="footer"
    :class="{ [`footer-${type}`]: type }"
    :data-background-color="backgroundColor"
  >
    <div class="container">
      <nav>
        <ul>
          <li>
            <a href="https://twitter.com/nagshukl">
              Nagendra Shukla
            </a>
          </li>
          <li>
            <a href="javasctipt:void(0);">
              About Us
            </a>
          </li>
          <li>
            <a href="javasctipt:void(0);">
              Blog
            </a>
          </li>
          <li>
            <a href="javasctipt:void(0);">
              Licenses
            </a>
          </li>
        </ul>
      </nav>
      <div class="copyright">
        &copy; {{ year }}, made with <md-icon>favorite</md-icon> by
        <a href="https://eduvision.com.au/" style="color:#ffffff" target="_blank">Eduvision</a>
        for a better future.
      </div>
    </div>
  </footer>
</template>
<script>
export default {
  props: {
    backgroundColor: String,
    type: String
  },
  data() {
    return {
      year: new Date().getFullYear()
    };
  }
};
</script>
<style></style>
