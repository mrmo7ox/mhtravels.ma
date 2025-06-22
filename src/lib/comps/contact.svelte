<script>
  import emailjs from '@emailjs/browser';

  let submitting = false;
  let success = false;

  const PUBLIC_KEY = import.meta.env.VITE_EMAILJS_PUBLIC_KEY;
  const SERVICE_ID = import.meta.env.VITE_EMAILJS_SERVICE_ID;
  const TEMPLATE_ID = import.meta.env.VITE_EMAILJS_TEMPLATE_ID;

  async function handleSubmit(e) {
    e.preventDefault();
    submitting = true;
    success = false;

    try {
      await emailjs.sendForm(
        SERVICE_ID,
        TEMPLATE_ID,
        e.target,
        {
          publicKey: PUBLIC_KEY,
        }
      );
      success = true;
      e.target.reset();
    } catch (error) {
      console.error('Échec de l\'envoi :', error);
      alert("Erreur lors de l'envoi. Veuillez réessayer.");
    } finally {
      submitting = false;
    }
  }
</script>

<section id="contact" class="bg-black text-white px-6 py-24">
  <div class="max-w-3xl mx-auto text-center">
    <h2 class="text-4xl font-extrabold text-lime-400 mb-4">Contactez-nous</h2>
    <p class="text-gray-300 mb-8">Réservez votre offre en quelques secondes</p>

    {#if success}
      <p class="bg-green-500 text-black p-4 rounded mb-6">
        Votre demande a été envoyée !
      </p>
    {/if}

    <form on:submit|preventDefault={handleSubmit} class="space-y-6">
      <input
        type="text"
        name="full_name"
        required
        placeholder="Nom complet"
        class="w-full px-4 py-3 rounded bg-neutral-800 border border-white/10 text-white"
      />

      <input
        type="tel"
        name="phone"
        required
        placeholder="Numéro de téléphone"
        class="w-full px-4 py-3 rounded bg-neutral-800 border border-white/10 text-white"
      />

      <select
        name="offer"
        required
        class="w-full px-4 py-3 rounded bg-neutral-800 border border-white/10 text-white"
      >
        <option value="" disabled selected hidden>
          Choisissez une offre
        </option>
        <option value="Week-end à Marrakech">Week-end à Marrakech</option>
        <option value="Aventure dans le désert">Aventure dans le désert</option>
        <option value="Évasion à Chefchaouen">Évasion à Chefchaouen</option>
      </select>

      <textarea
        name="message"
        placeholder="Message (optionnel)"
        class="w-full px-4 py-3 rounded bg-neutral-800 border border-white/10 text-white"
      ></textarea>

      <button
        type="submit"
        class="bg-lime-400 text-black px-6 py-3 rounded font-bold hover:bg-lime-300 transition"
        disabled={submitting}
      >
        {submitting ? "Envoi..." : "Envoyer"}
      </button>
    </form>
  </div>
</section>
