# Crockery public documentation and support site

Static files for the Shopify Theme Store listing.

Public URLs, after GitHub Pages is enabled on the public `larder` repo:

- Documentation: https://sohofisohofi6-ux.github.io/larder/
- Support form: https://sohofisohofi6-ux.github.io/larder/support.html

Do not point Theme Store or `theme_info` URLs at the password-protected demo store. Client transfer demo stores must stay password-protected while they remain in the Partner organization. Theme Store demo links bypass that password for listing visitors; merchants still need public docs and a public support form.

This folder is deploy-ready. It does not include internal drafts such as the listing preview or submission checklist.

## Hosting

**GitHub Pages** for the static docs, plus **FormSubmit** (`https://formsubmit.co`) for the support form.

- GitHub Pages is free on this public repository.
- FormSubmit needs no paid plan and no account. It accepts file uploads up to 10 MB and can send an auto-reply (`_autoresponse`) on the free service. Auto-reply only works if reCAPTCHA stays enabled and the form uses a normal POST, not AJAX. Official docs: https://formsubmit.co/documentation
- Do not host docs or the support form on `larder-demo-wmejyz0g.myshopify.com`. Do not change anything on the Lauvna store.

## Support form configuration

In `support.html`:

1. The form action is `https://formsubmit.co/allmarwanacc-emmc9c@mail.grokbot.com`.
2. The `_next` thank-you URL is `https://sohofisohofi6-ux.github.io/larder/thanks.html`.

The first real submission sends a FormSubmit activation email to that inbox. The form does not deliver tickets until the confirmation link in that email is opened. After confirmation, a second test with a screenshot should arrive in the support inbox, with Reply-To set to the merchant email, a subject starting with `Crockery support:`, and an auto-reply to the submitter. Keep reCAPTCHA enabled. Add `theme-submissions@shopify.com`, `themes@shopify.com`, and `noreply@shopify.com` to the inbox allow list, and watch for mail from FormSubmit so the activation message is not filed as spam.

After the Pages URLs work, set `theme_documentation_url` and `theme_support_url` in the theme `config/settings_schema.json` to the two public URLs above, then package the theme. Use those same public URLs on the Theme Store listing form.

## Form field mapping

The support form includes the Theme Store fields: name, email, store URL (with the required example), description of the problem (textarea), file upload, theme name (pre-filled "Crockery"), and subject (copied into the email subject line). An auto-response message is set, and a thank-you page is at `thanks.html`.
