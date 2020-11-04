---
layout: default
id: overview

competition-form:
  id: comp
  post-url: https://getform.io/f/bd27df03-c05f-4f19-a9b6-60cba0ce1b39
  expiry-date: 2021-04-01
  fields:
    - id: email
      type: email
      label: Email
      required: true
  submit: Claim voucher
  terms: "*The credit will be added to your account within 5 working days. A&nbsp;minimum spend of £125 applies"
---

<div class="vpad--xl">
  <div class="container vpad--sm text--center theme--dark">
    <a class="logo logo--se" href="{{site.data.locale.uk.core-site}}">
      <img src="{{site.img}}/logo/secret-escapes.svg" alt="Secret Escapes logo">
    </a>
    <div class="space--xl"></div>
    <h1 class="width width--lg h h--lg">Claim your Light & Free voucher now</h1>
  </div>
  <div class="container">
    <div id="entry-form" class="vpad--md">
      <div class="bg--white boxpad--lg width width--md">
      {% assign form = page.competition-form %}
      <form class="form boilerform competition-form" action="{{form.post-url}}" method="POST" data-expires="{{form.expiry-date}}" novalidate>
        {% include form/messages.html %}
        <div class="form__content width width--md">
          <p class="p--xl">Please submit your registered Secret Escapes email address to claim your £25 Secret Escapes credit*.</p>
          <div class="space--md"></div>
          {% for item in form.fields %}
            <div class="form__input js-form-input">
              {% case item.type %}
                {% when 'text' %}
                  {% include form/text.html data=item %}
                {% when 'text-long' %}
                  {% include form/text-long.html data=item %}
                {% when 'email' %}
                  {% include form/email.html data=item %}
                {% when 'radio' %}
                  {% include form/radio.html data=item %}
                {% when 'checkbox' %}
                  {% include form/checkbox.html data=item %}
                {% when 'select' %}
                  {% include form/select.html data=item %}
              {% endcase %}
            </div>
          {% endfor %}
          <div class="space--md"></div>
          <input class="js-form-entry-time" id="entry-time" name="entry-time" type="hidden">
          <button type="submit" class="btn" disabled>{{form.submit}}</button>
        </div>
      </form>
      </div>
      <div class="text--center theme--dark width width--md boxpad--xs">
        <p class="p--sm text--normal">{{form.terms}}</p>
      </div>
    </div>
  </div>
<div class="space--xl"></div>
</div>