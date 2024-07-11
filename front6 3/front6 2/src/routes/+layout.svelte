<script>
  import { onMount } from 'svelte';
  import '../app.css'

  onMount(() => {
    document.title = 'Mark Petrov';
  });
</script>

<svelte:head>
  <meta name="author" content="Mark Petrov">
  <meta name="description" content="Mark Petrov's personal website showcasing work, projects, and more.">
</svelte:head>

<header class="container1">
  <div class="left">
    <p>ru</p>
  </div>
  <nav class="right">
    <div class="menu">
      <p>about</p>
      <p>work</p>
      <p>contacts</p>
    </div>
    <div class="icons">
      <a href="https://t.me/pavorkmert"><img src="images/telegram.png" alt="Telegram"></a>
      <a href="https://github.com/pavorkmert"><img src="images/git.png" alt="GitHub"></a>
      <a href="mailto:MarkPetrov2015@mail.ru"><img src="images/mail.png" alt="Email"></a>
    </div>
  </nav>
</header>

<main>
  <slot />
</main>

<footer class="container4">
  <p>2024 Mark Petrov</p>
</footer>

<style>
  /* Copy the styles for .container1, .container4, and other relevant styles from app.css */
</style>
