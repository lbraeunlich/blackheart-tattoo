<template>
    <div class="page">

        <nav class="nav">
            <span class="logo">Blackheart Tattoo & Piercing</span>
            <div class="nav-links">
                <a href="#">Künstler</a>
                <NuxtLink to="/gallery" class="btn">Galerie</NuxtLink>
                <NuxtLink to="/booking" class="btn">Termin buchen</NuxtLink>
            </div>
        </nav>

        <section class="hero">
            <p class="eyebrow">Seit 2018 — Wallmerod</p>
            <h1>Kunst, die<br><em>bleibt.</em></h1>
            <p class="sub">Kein Kompromiss. Kein Einheitsdesign. Nur Tattoos, hinter denen wir wirklich stehen — für immer auf deiner Haut.</p>
            <NuxtLink to="/booking" class="btn">Jetzt Termin buchen</NuxtLink>
        </section>

        <section class="section">
            <p class="eyebrow">Das Kollektiv</p>
            <h2>Lern unsere Künstler kennen</h2>
            <div class="grid">
                <div class="artist-card">
                    <div class="photo">VS</div>
                    <p class="specialty">Blackwork & Surrealismus</p>
                    <p class="name">Viktor Shade</p>
                </div>
                <div class="artist-card">
                    <div class="photo">LN</div>
                    <p class="specialty">Fine Line & Botanik</p>
                    <p class="name">Luna Noir</p>
                </div>
                <div class="artist-card">
                    <div class="photo">RB</div>
                    <p class="specialty">Neo-Traditional</p>
                    <p class="name">Rex Burned</p>
                </div>
            </div>
        </section>

        <section class="cta">
            <h2>Bereit für etwas Bleibendes?</h2>
            <p>Erzähl uns deine Idee — wir finden den richtigen Künstler für dich und machen daraus etwas Unvergessliches.</p>
            <NuxtLink to="/booking" class="btn">Termin vereinbaren</NuxtLink>
        </section>

    </div>
</template>

<script setup>
</script>

<style>
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

html,
body {
    overflow-x: hidden;
    background: #0a0a0a;
    color: #c8bfb5;
    font-family: Georgia, serif;
}

body {
    width: 100%;
}

.page {
    min-height: 100vh;
    width: 100%;
}

/* NAV */

.nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 1.5rem;
    padding: 1.5rem 2rem;
    border-bottom: 1px solid #222;
    flex-wrap: wrap;
}

.logo {
    font-size: 1.1rem;
    letter-spacing: 0.15em;
    color: #e8dfd3;
    line-height: 1.3;
}

.nav-links {
    display: flex;
    gap: 1.5rem;
    align-items: center;
    flex-wrap: wrap;
}

.nav-links a {
    color: #7a7065;
    text-decoration: none;
    letter-spacing: 0.1em;
    font-size: 0.95rem;
}

.nav-links a:hover {
    color: #e8dfd3;
}

/* BUTTON */

.btn {
    background: #F5F5DC;
    color: #000000;
    padding: 0.75em 1.6em;
    text-decoration: none;
    letter-spacing: 0.08em;
    display: inline-block;
    transition: 0.2s ease;
    text-align: center;
}

.btn:hover {
    background: #000000;
    color: #F5F5DC;
}

/* HERO */

.hero {
    min-height: 90vh;
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    padding: 5rem 2rem;
    border-bottom: 1px solid #222;
    background-image: url('/needle.jpg');
    background-size: cover;
    background-position: center;
}

.eyebrow {
    color: #F5F5DC;
    letter-spacing: 0.3em;
    font-size: 0.75rem;
    margin-bottom: 1rem;
    text-transform: uppercase;
}

h1 {
    font-size: clamp(2.8rem, 9vw, 6rem);
    color: #e8dfd3;
    line-height: 0.95;
    margin-bottom: 1.5rem;
    max-width: 10ch;
}

h1 em {
    color: #F5F5DC;
    font-style: normal;
}

.sub {
    color: #e8dfd3;
    font-size: 1.05rem;
    max-width: 40ch;
    margin-bottom: 2rem;
    line-height: 1.7;
}

/* SECTIONS */

.section {
    padding: 5rem 2rem;
    width: 100%;
}

.section h2 {
    font-size: clamp(2rem, 5vw, 2.8rem);
    color: #e8dfd3;
    margin-bottom: 2.5rem;
    line-height: 1.1;
}

/* GRID */

.grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1.5rem;
}

.artist-card {
    background: #111;
    padding: 2rem;
    border: 1px solid #222;
}

.photo {
    aspect-ratio: 1;
    width: 100%;
    background: #1a1a1a;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 3rem;
    color: #333;
    margin-bottom: 1rem;
}

.specialty {
    color: #F5F5DC;
    font-size: 0.8rem;
    letter-spacing: 0.15em;
    margin-bottom: 0.4rem;
    line-height: 1.4;
}

.name {
    color: #e8dfd3;
    font-size: 1.3rem;
}

/* CTA */

.cta {
    padding: 5rem 2rem;
    text-align: center;
    background: #111;
    border-top: 1px solid #222;
    width: 100%;
}

.cta h2 {
    font-size: clamp(2rem, 5vw, 2.8rem);
    color: #e8dfd3;
    margin-bottom: 1rem;
    line-height: 1.2;
}

.cta p {
    color: #7a7065;
    margin-bottom: 2rem;
    max-width: 45ch;
    margin-inline: auto;
    line-height: 1.7;
}

/* TABLET */

@media (max-width: 900px) {
    .grid {
        grid-template-columns: repeat(2, 1fr);
    }

    .hero {
        padding: 4rem 1.5rem;
    }

    .section,
    .cta {
        padding: 4rem 1.5rem;
    }
}

/* MOBILE */

@media (max-width: 640px) {
    .nav {
        flex-direction: column;
        align-items: flex-start;
        padding: 1.25rem;
    }

    .nav-links {
        width: 100%;
        justify-content: space-between;
        gap: 1rem;
    }

    .hero {
        min-height: 80vh;
        padding: 3rem 1.25rem;
        justify-content: center;
    }

    h1 {
        max-width: 100%;
    }

    .sub {
        font-size: 1rem;
    }

    .grid {
        grid-template-columns: 1fr;
    }

    .artist-card {
        padding: 1.5rem;
    }

    .section,
    .cta {
        padding: 3rem 1.25rem;
    }

    .btn {
        width: 100%;
    }

    .nav-links .btn {
        width: auto;
    }
}
</style>