---
layout: default
title: Contact
permalink: /contact/
---

# Contact

Have a question, a correction, or a topic you'd like covered? Send a note below.

<!--
  SETUP REQUIRED: this form posts to Formspree (https://formspree.io), a
  free-tier form backend that emails submissions to you — no server code
  needed on a static Jekyll/Cloudflare site.
  1. Create a free account at formspree.io and add a new form.
  2. Replace REPLACE_ME_FORM_ID below with the form ID Formspree gives you
     (the URL will look like https://formspree.io/f/abc123).
-->
<form action="https://formspree.io/f/REPLACE_ME_FORM_ID" method="POST" class="contact-form">
  <div class="form-field">
    <label for="contact-name">Name</label>
    <input id="contact-name" name="name" type="text" autocomplete="name" required>
  </div>

  <div class="form-field">
    <label for="contact-email">Email</label>
    <input id="contact-email" name="email" type="email" autocomplete="email" required aria-describedby="contact-privacy-note">
  </div>

  <div class="form-field">
    <label for="contact-message">Message</label>
    <textarea id="contact-message" name="message" rows="6" required></textarea>
  </div>

  <!-- Honeypot field to deter simple spam bots — hidden from sighted and AT users, never filled by humans -->
  <input type="text" name="_gotcha" class="sr-only" tabindex="-1" autocomplete="off">

  <button type="submit" class="contact-submit">Send message</button>

  <p id="contact-privacy-note" class="contact-privacy-note">
    Submitting this form sends your name, email, and message to Formspree so it can be
    relayed to us by email. See our <a href="{{ '/privacy/' | relative_url }}">Privacy Policy</a>
    for details. We don't use this information for anything other than replying to you.
  </p>
</form>
