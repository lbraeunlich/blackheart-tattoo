<template>
    <div class="page">

        <nav class="nav">
            <NuxtLink to="/" class="logo">Blackheart Tattoo & Piercing</NuxtLink>
            <div class="nav-links">
                <a href="#">Künstler</a>
                <a href="#">Galerie</a>
                <NuxtLink to="/booking" class="btn">Termin buchen</NuxtLink>
            </div>
        </nav>

        <section class="booking-hero">
            <p class="eyebrow">Bereit für dein nächstes Tattoo?</p>
            <h1>Termin <em>buchen</em></h1>
            <p class="sub">Füll das Formular aus — wir melden uns innerhalb von 48 Stunden bei dir.</p>
        </section>

        <section class="section">
            <form class="form" @submit.prevent="submit">

                <div class="form-row">
                    <div class="form-group">
                        <label>Dein Name *</label>
                        <input v-model="form.name" type="text" placeholder="Max Mustermann" required />
                    </div>
                    <div class="form-group">
                        <label>E-Mail *</label>
                        <input v-model="form.email" type="email" placeholder="max@beispiel.de" required />
                    </div>
                </div>

                <div class="form-row">
                    <div class="form-group">
                        <label>Telefon</label>
                        <input v-model="form.phone" type="tel" placeholder="+49 151 000 000" />
                    </div>
                    <div class="form-group">
                        <label>Künstler</label>
                        <select v-model="form.artist">
                            <option value="">Keine Präferenz</option>
                            <option>Viktor Shade</option>
                            <option>Luna Noir</option>
                            <option>Rex Burned</option>
                        </select>
                    </div>
                </div>

                <div class="form-group">
                    <label>Stil</label>
                    <select v-model="form.style">
                        <option value="">Bitte wählen</option>
                        <option>Blackwork</option>
                        <option>Fine Line</option>
                        <option>Neo-Traditional</option>
                        <option>Surrealismus</option>
                        <option>Realism</option>
                        <option>Geometric</option>
                        <option>Sonstiges</option>
                    </select>
                </div>

                <div class="form-group">
                    <label>Deine Idee *</label>
                    <textarea v-model="form.description" placeholder="Beschreib dein Tattoo — Motiv, Größe, Körperstelle..." required></textarea>
                </div>

                <div class="form-group">
                    <label>Wunschtermin</label>
                    <input v-model="form.date" type="date" />
                </div>

                <div v-if="success" class="success-msg">
                    ✓ Anfrage gesendet! Wir melden uns bald bei dir.
                </div>

                <button type="submit" class="btn submit-btn" :disabled="loading">
                    {{ loading ? 'Wird gesendet...' : 'Anfrage absenden' }}
                </button>

            </form>
        </section>

    </div>
</template>

<script setup>
const form = ref({
    name: '',
    email: '',
    phone: '',
    artist: '',
    style: '',
    description: '',
    date: '',
})

const loading = ref(false)
const success = ref(false)

async function submit() {
    loading.value = true
    // Backend kommt später — erstmal nur simulieren
    await new Promise(resolve => setTimeout(resolve, 1000))
    success.value = true
    loading.value = false
    form.value = { name: '', email: '', phone: '', artist: '', style: '', description: '', date: '' }
}
</script>

<style>
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

html, body {
    overflow-x: hidden;
    background: #0a0a0a;
    color: #c8bfb5;
    font-family: Georgia, serif;
}

.page {
    min-height: 100vh;
    width: 100%;
}

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
    text-decoration: none;
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

.nav-links a:hover { color: #e8dfd3; }

.btn {
    background: #F5F5DC;
    color: #000000;
    padding: 0.75em 1.6em;
    text-decoration: none;
    letter-spacing: 0.08em;
    display: inline-block;
    transition: 0.2s ease;
    text-align: center;
    border: none;
    cursor: pointer;
    font-family: Georgia, serif;
    font-size: 1rem;
}

.btn:hover { background: #000000; color: #F5F5DC; }
.btn:disabled { opacity: 0.5; cursor: not-allowed; }

.booking-hero {
    padding: 5rem 2rem 3rem;
    border-bottom: 1px solid #222;
}

.eyebrow {
    color: #F5F5DC;
    letter-spacing: 0.3em;
    font-size: 0.75rem;
    margin-bottom: 1rem;
    text-transform: uppercase;
}

h1 {
    font-size: clamp(2.8rem, 9vw, 5rem);
    color: #e8dfd3;
    line-height: 0.95;
    margin-bottom: 1.5rem;
}

h1 em { color: #F5F5DC; font-style: normal; }

.sub {
    color: #7a7065;
    font-size: 1.05rem;
    max-width: 45ch;
    line-height: 1.7;
}

.section {
    padding: 4rem 2rem;
    max-width: 800px;
}

.form {
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
}

.form-row {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1.5rem;
}

.form-group {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
}

label {
    font-size: 0.75rem;
    letter-spacing: 0.2em;
    text-transform: uppercase;
    color: #7a7065;
}

input, select, textarea {
    background: #111;
    border: 1px solid #222;
    color: #e8dfd3;
    padding: 0.85rem 1rem;
    font-family: Georgia, serif;
    font-size: 1rem;
    width: 100%;
    outline: none;
    transition: border-color 0.2s;
    -webkit-appearance: none;
}

input:focus, select:focus, textarea:focus {
    border-color: #F5F5DC;
}

textarea {
    min-height: 140px;
    resize: vertical;
}

select option { background: #111; }

.submit-btn {
    align-self: flex-start;
    font-size: 1rem;
}

.success-msg {
    background: #111;
    border: 1px solid #F5F5DC;
    color: #F5F5DC;
    padding: 1rem 1.5rem;
    letter-spacing: 0.05em;
}

@media (max-width: 900px) {
    .section { padding: 4rem 1.5rem; }
}

@media (max-width: 640px) {
    .nav {
        flex-direction: column;
        align-items: flex-start;
        padding: 1.25rem;
    }

    .nav-links {
        width: 100%;
        justify-content: space-between;
    }

    .booking-hero {
        padding: 3rem 1.25rem 2rem;
    }

    .form-row {
        grid-template-columns: 1fr;
    }

    .section {
        padding: 3rem 1.25rem;
    }

    .submit-btn {
        width: 100%;
    }
}
</style>