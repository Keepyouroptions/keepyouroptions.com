---
layout: default
title: Contact
permalink: /contact/
---

# Contact

Have a question, a correction, or a topic you'd like covered? Send a note below.

<form class="contact-form" id="contact-form" novalidate>
  <div class="form-field">
    <label for="contact-name">Name</label>
    <input id="contact-name" name="name" type="text" autocomplete="name" required>
  </div>

  <div class="form-field">
    <label for="contact-subject">Subject</label>
    <input id="contact-subject" name="subject" type="text" required>
  </div>

  <div class="form-field">
    <label for="contact-message">Message</label>
    <textarea id="contact-message" name="message" rows="6" required></textarea>
  </div>

  <button type="submit" class="contact-submit">Send message</button>

  <p class="contact-privacy-note">
    This opens your email app with your message pre-filled — nothing is sent through a
    third-party form service, and no message content is stored anywhere by this site. If
    nothing opens (common if you only use webmail in a browser), copy the address below and
    send it that way instead. See our <a href="{{ '/privacy/' | relative_url }}">Privacy Policy</a>
    for details.
  </p>

  <div class="email-fallback">
    <code id="fallback-email">hello@keepyouroptions.com</code>
    <button type="button" class="copy-btn" id="copy-email-btn" aria-live="polite">Copy</button>
  </div>
</form>

<script>
  document.getElementById('contact-form').addEventListener('submit', function (e) {
    e.preventDefault();
    var name = document.getElementById('contact-name').value;
    var subject = document.getElementById('contact-subject').value;
    var message = document.getElementById('contact-message').value;
    var body = message + '\n\n— ' + name;
    var mailto = 'mailto:hello@keepyouroptions.com'
      + '?subject=' + encodeURIComponent(subject)
      + '&body=' + encodeURIComponent(body);
    window.location.href = mailto;
  });

  document.getElementById('copy-email-btn').addEventListener('click', function () {
    var email = document.getElementById('fallback-email').textContent;
    var btn = this;
    navigator.clipboard.writeText(email).then(function () {
      var original = btn.textContent;
      btn.textContent = 'Copied!';
      setTimeout(function () { btn.textContent = original; }, 2000);
    });
  });
</script>
