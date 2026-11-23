---
title: "Sugerir un artista"
slug: suggest-an-artist
---

Me encanta conocer a músicos y artistas que siguen a Jesús. Si conoces a alguien sobre quien debería escribir, a quien entrevistar o sobre quien hacer un vídeo de reacción, cuéntamelo aquí.

Un nombre y un enlace bastan — y unas palabras sobre por qué esa persona. Leo todo lo que llega. Muchas gracias.

¿Conoces a alguien? Toca su foto y el formulario se rellena solo — luego añade unas palabras sobre por qué esa persona y envíalo.

<div class="suggest-carousel" role="list" aria-label="Músicos y artistas que puedes sugerir">
{% for artist in suggest_carousel %}
  <button type="button" class="suggest-pick" role="listitem" data-artist="{{ artist.name }}" data-link="{{ artist.profile }}" title="Sugerir a {{ artist.name }}">
    <img src="{{ artist.img }}" alt="{{ artist.name }}" loading="lazy" width="150" height="150">
    <span class="suggest-pick__name">{{ artist.name }}</span>
    <span class="suggest-pick__note">{{ artist.note }}</span>
  </button>
{% endfor %}
</div>

<p class="suggest-carousel__more">O sugiere a alguien nuevo abajo — a cualquiera que creas que debería conocer.</p>

Este sitio no es para personas menores de 18 años.

<form id="suggest-form" class="suggest-form">
  <label for="suggest-artist">Nombre del artista</label>
  <input id="suggest-artist" name="artist" type="text" maxlength="200" placeholder="¿A quién debería conocer?" required>

  <label for="suggest-link">Enlace a su perfil en redes sociales</label>
  <input id="suggest-link" name="link" type="url" maxlength="500" placeholder="https://www.instagram.com/…" required>

  <fieldset class="suggest-kinds">
    <legend>¿Qué hago con esa persona?</legend>
    <label><input type="checkbox" name="kind" value="write"> Escribir sobre esa persona</label>
    <label><input type="checkbox" name="kind" value="interview"> Entrevistar a esa persona</label>
    <label><input type="checkbox" name="kind" value="reaction"> Hacer un vídeo de reacción sobre esa persona</label>
  </fieldset>

  <label for="suggest-why">¿Por qué esa persona?</label>
  <textarea id="suggest-why" name="why" rows="3" maxlength="500" placeholder="Unas palabras bastan…"></textarea>

  <label for="suggest-name">Tu nombre <span class="optional">(opcional)</span></label>
  <input id="suggest-name" name="fromName" type="text" maxlength="100" placeholder="Para poder darte las gracias">

  <label for="suggest-from-link">Enlace a tu perfil en redes sociales <span class="optional">(opcional)</span></label>
  <input id="suggest-from-link" name="fromLink" type="url" maxlength="500" placeholder="https://www.instagram.com/…">

  <button id="suggest-button" type="button">Enviar sugerencia</button>

  <p id="suggest-result" aria-live="polite"></p>
</form>
