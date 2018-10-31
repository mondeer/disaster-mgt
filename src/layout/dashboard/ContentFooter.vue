<template>
  <footer class="footer">
    <div class="container-fluid">
      <ul class="nav">
        <li class="nav-item">
          <a class="nav-link" href="http://twitter.com/mondeer">
            Twitter
          </a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="http://www.github.com/mondeer">
            Github
          </a>
        </li>
      </ul>
      <div class="copyright">
        © {{year}} made with <i class="tim-icons icon-heart-2"></i> by
        <a href="https://www.imond.com" target="_blank">iMond Solutions</a> for a better Disaster Management.
      </div>
    </div>
  </footer>
</template>
<script>
  export default {
    data() {
      return {
        year: new Date().getFullYear()
      }
    }
  };
</script>
<style>
</style>
