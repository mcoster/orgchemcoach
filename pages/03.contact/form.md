---
title: 'Get In Touch'
description: 'Use the form below to contact Mark regarding Org Chem Coaching.'
body_class: contact
icon: envelope
menu: Enquire
form:
    name: my-nice-form
    fields:
        -
            name: name
            label: Name
            framework_size: half
            placeholder: 'Your name'
            autofocus: 'on'
            autocomplete: 'on'
            type: text
            validate:
                required: true
        -
            name: email
            framework_size: half
            label: Email
            placeholder: name@example.com
            type: text
            validate:
                rule: email
                required: true
        -
            name: message
            framework_size: full
            label: Message
            size: long
            placeholder: 'Your message here'
            type: textarea
            validate:
                required: true
    buttons:
        -
            type: submit
            value: Submit
    process:
        -
            email:
                from: '{{ config.plugins.email.from }}'
                to:
                    - '{{ config.plugins.email.from }}'
                    - '{{ form.value.email }}'
                subject: '[orgchemcoach.net] {{ form.value.name|e }}'
                body: '{% include ''forms/data.html.twig'' %}'
        -
            save:
                fileprefix: feedback-
                dateformat: Ymd-His-u
                extension: txt
                body: '{% include ''forms/data.txt.twig'' %}'
        -
            message: 'Thank you for your message!'
        -
            display: thankyou
---

I offer a free 15 minute introductory session - no obligations! Beyond that, I offer packages based on the total coaching time you would like to buy:
* 1 hour = $150
* 2 hours = $240
* 4 hours = $400
* 10 hours = $800
Other arrangements are possible - just let me know what you are looking for.