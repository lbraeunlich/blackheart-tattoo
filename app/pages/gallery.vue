<template>
    <div class="page">

        <nav class="nav">
            <NuxtLink to="/" class="logo">Blackheart Tattoo & Piercing</NuxtLink>
            <div class="nav-links">
                <a href="#">Künstler</a>
                <NuxtLink to="/gallery" style="color:#e8dfd3">Galerie</NuxtLink>
                <NuxtLink to="/booking" class="btn">Termin buchen</NuxtLink>
            </div>
        </nav>

        <div class="hero">
            <p class="eyebrow">Unsere Arbeiten</p>
            <h1>Die <em>Galerie</em></h1>
            <p class="sub">Echte Haut. Echte Kunst. Jedes Stück erzählt eine Geschichte.</p>
        </div>

        <div class="filters">
            <button
                v-for="style in styles"
                :key="style"
                class="filter-btn"
                :class="{ active: activeFilter === style }"
                @click="activeFilter = style"
            >
                {{ style }}
            </button>
        </div>
 
        <div class="gallery">
            <div
                v-for="item in filtered"
                :key="item.id"
                class="gallery-item"
            >
                <div class="placeholder" :style="{ height: item.height + 'px' }">
                    <span>{{ item.artist.split(' ').map(w => w[0]).join('') }}</span>
                </div>
                <div class="overlay">
                    <p class="item-artist">{{ item.artist }}</p>
                    <p class="item-title">{{ item.title }}</p>
                </div>
            </div>
        </div>

    </div>
</template>

<script setup>
const styles = ['Alle', 'Blackwork', 'Fine Line', 'Neo-Traditional', 'Surrealism']
const activeFilter = ref('Alle')

const artworks = [
    { id: 1, title: 'Dunkle Seele',    artist: 'Viktor Shade', style: 'Blackwork',       height: 320 },
    { id: 2, title: 'Vergissmeinnicht', artist: 'Luna Noir',   style: 'Fine Line',        height: 260 },
    { id: 3, title: 'Der Wolf',         artist: 'Rex Burned',  style: 'Neo-Traditional',  height: 380 },
    { id: 4, title: 'Schatten',         artist: 'Viktor Shade', style: 'Surrealism',      height: 280 },
    { id: 5, title: 'Mondblume',        artist: 'Luna Noir',   style: 'Fine Line',        height: 340 },
    { id: 6, title: 'Adler',            artist: 'Rex Burned',  style: 'Neo-Traditional',  height: 300 },
    { id: 7, title: 'Abyss',            artist: 'Viktor Shade', style: 'Blackwork',       height: 360 },
    { id: 8, title: 'Ranke',            artist: 'Luna Noir',   style: 'Fine Line',        height: 240 },
    { id: 9, title: 'Totenkopf',        artist: 'Rex Burned',  style: 'Neo-Traditional',  height: 290 },
]

const filtered = computed(() =>
    activeFilter.value === 'Alle'
        ? artworks
        : artworks.filter(a => a.style === activeFilter.value)
)
</script>

<style>
* { box-sizing: border-box; margin: 0; padding: 0; }

html, body { overflow-x: hidden; background: #0a0a0a; color: #c8bfb5; font-family: Georgia, serif; }

.page { min-height: 100vh; }

.nav { display: flex; justify-content: space-between; align-items: center; gap: 1.5rem; padding: 1.5rem 2rem; border-bottom: 1px solid #222; flex-wrap: wrap; }
.logo { font-size: 1.1rem; letter-spacing: 0.15em; color: #e8dfd3; text-decoration: none; }
.nav-links { display: flex; gap: 1.5rem; align-items: center; flex-wrap: wrap; }
.nav-links a { color: #7a7065; text-decoration: none; letter-spacing: 0.1em; font-size: 0.95rem; }

.btn { background: #F5F5DC; color: #000; padding: 0.75em 1.6em; text-decoration: none; letter-spacing: 0.08em; display: inline-block; transition: 0.2s ease; }
.btn:hover { background: #000; color: #F5F5DC; }

.hero { padding: 4rem 2rem 2.5rem; border-bottom: 1px solid #222; }
.eyebrow { color: #F5F5DC; letter-spacing: 0.3em; font-size: 0.75rem; text-transform: uppercase; margin-bottom: 0.75rem; }
h1 { font-size: clamp(2.5rem, 7vw, 5rem); color: #e8dfd3; line-height: 0.95; margin-bottom: 1rem; }
h1 em { color: #F5F5DC; font-style: normal; }
.sub { color: #7a7065; font-size: 1rem; max-width: 45ch; line-height: 1.7; }

.filters { display: flex; gap: 0.75rem; flex-wrap: wrap; padding: 2rem 2rem 0; }
.filter-btn { background: transparent; border: 1px solid #222; color: #7a7065; padding: 0.4em 1.2em; font-family: Georgia, serif; font-size: 0.85rem; letter-spacing: 0.1em; cursor: pointer; transition: all 0.2s; }
.filter-btn:hover, .filter-btn.active { background: #F5F5DC; color: #000; border-color: #F5F5DC; }

.gallery { padding: 2rem; columns: 3; column-gap: 6px; }
.gallery-item { break-inside: avoid; margin-bottom: 6px; position: relative; cursor: pointer; background: #111; overflow: hidden; }
.gallery-item:hover .overlay { opacity: 1; }

.placeholder { width: 100%; background: #141414; display: flex; align-items: center; justify-content: center; }
.placeholder span { font-size: 2.5rem; color: #2a2a2a; }

.overlay { position: absolute; inset: 0; background: linear-gradient(to top, rgba(5,5,5,0.9) 0%, transparent 55%); opacity: 0; transition: opacity 0.3s; display: flex; flex-direction: column; justify-content: flex-end; padding: 1rem; }
.item-artist { color: #F5F5DC; font-size: 0.65rem; letter-spacing: 0.2em; text-transform: uppercase; margin-bottom: 0.2rem; }
.item-title { color: #e8dfd3; font-size: 1rem; }

@media (max-width: 900px) { .gallery { columns: 2; } }
@media (max-width: 640px) {
    .gallery { columns: 1; }
    .nav { flex-direction: column; align-items: flex-start; }
    .nav-links { width: 100%; justify-content: space-between; }
    .hero { padding: 3rem 1.25rem 2rem; }
    .filters { padding: 1.5rem 1.25rem 0; }
    .gallery { padding: 1.25rem; }
}
</style>