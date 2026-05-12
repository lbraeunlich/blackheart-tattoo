<template>
  <div class="page">

    <nav class="nav">
      <span class="logo">Blackheart Tattoo & Piercingstudio</span>
      <div class="nav-links">
        <a href="#">Artists</a>
        <a href="#">Gallery</a>
        <a href="#" class="btn">Book Now</a>
      </div>
    </nav>

    
  </div>
</template>

<script setup>
</script>

<style>
body { margin: 0; background: #0a0a0a; color: #c8bfb5; font-family: Georgia, serif; }

.page { min-height: 100vh; }

.nav { display: flex; justify-content: space-between; align-items: center; padding: 1.5rem 2rem; border-bottom: 1px solid #222; }
.logo { font-size: 1.5rem; letter-spacing: 0.2em; color: #e8dfd3; }
.nav-links { display: flex; gap: 2rem; align-items: center; }
.nav-links a { color: #7a7065; text-decoration: none; letter-spacing: 0.1em; }
.nav-links a:hover { color: #e8dfd3; }

.btn { background: #F5F5DC; color: #e8dfd3; padding: 0.6em 1.8em; text-decoration: none; letter-spacing: 0.1em; display: inline-block; }
.btn:hover { background: #cc1010; }

.hero { min-height: 90vh; display: flex; flex-direction: column; justify-content: flex-end; padding: 4rem 2rem; border-bottom: 1px solid #222; }
.eyebrow { color: #F5F5DC; letter-spacing: 0.3em; font-size: 0.8rem; margin-bottom: 1rem; }
h1 { font-size: clamp(3rem, 8vw, 6rem); color: #e8dfd3; line-height: 1; margin-bottom: 1.5rem; }
h1 em { color: #F5F5DC; font-style: normal; }
.sub { color: #7a7065; font-size: 1.1rem; max-width: 40ch; margin-bottom: 2rem; line-height: 1.7; }

.section { padding: 5rem 2rem; }
.section h2 { font-size: 2.5rem; color: #e8dfd3; margin-bottom: 2.5rem; }
.grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.5rem; }

.artist-card { background: #111; padding: 2rem; border: 1px solid #222; }
.photo { aspect-ratio: 1; background: #1a1a1a; display: flex; align-items: center; justify-content: center; font-size: 3rem; color: #333; margin-bottom: 1rem; }
.specialty { color: #F5F5DC; font-size: 0.8rem; letter-spacing: 0.15em; margin-bottom: 0.4rem; }
.name { color: #e8dfd3; font-size: 1.3rem; }

.cta { padding: 5rem 2rem; text-align: center; background: #111; border-top: 1px solid #222; }
.cta h2 { font-size: 2.5rem; color: #e8dfd3; margin-bottom: 1rem; }
.cta p { color: #7a7065; margin-bottom: 2rem; }
</style>