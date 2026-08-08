# Headingsmap Translations

This repository is meant to be the place to have the translations of the texts and labels that the extension has. The
texts are divided into two groups:
* Translations that are added programmatically. They are labels that are in json files under the directory "_locales".
* HTML contents that are static. They are HTML files that are located in different folders under the directory "html".

So far there are five language versions (English, French, Spanish, Polish and Japanese). If you want to contribute
translating it, you will be very welcome, so thank you in advance. Just follow the normal github process (fork the
repository, etc.). And if you don't know how to do it, there is no problem. In that case you can download everything,
translate it and then send it back to me directly. Or just contact me and I can send you the files.

If you have any doubt, concern, or there are texts that are not clear, do not hesitate to write to me, or alternatively
create an issue in the repository.

## A couple of comments

* The release notes files are long, and they are growing. There are entries that correspond with versions from 2018. 
Because of that, I would say that you don't need to translate them completely. For instance, translating the latest ones
would be enough.
* Since adding (or updating) the translations is a change, I would like to ask you also for a translation of 
a thank-you sentence to be included in the release notes. I am always grateful to these contributions, so the sentence
could be something like: "*Translated to (language) by (name, alias,... what you prefer). Thank you very much for your
willingness to collaborate*". Adding this to the release notes is the least I can do to thank you for helping the
project this way.

## A few conventions

Small things, but they keep the files consistent, and a couple of them matter for an accessibility tool:

* **Mark untranslated text as English.** If you leave something in English (release notes entries are the usual case),
add a language attribute to it: `<dd lang="en-US">...</dd>`, or `<dl lang="en">` around a whole block. Otherwise a
screen reader will read the English text using the pronunciation rules of your language — which is exactly the kind of
problem this extension is meant to help people find (WCAG 3.1.2, Language of Parts).
* **Keep every key in `messages.json`.** Each file under `_locales` must have exactly the same keys as
`_locales/en/messages.json`, and placeholders such as `{level}` must be left as they are.
* **A heading is not a header.** The extension reports on HTML headings (h1–h6) and, separately, on landmarks such as
`banner` or `contentinfo`. Please use the word your language uses for a *document heading*, not the one for a page
header or an HTTP header. In the languages already here that means *encabezado* (not *cabecera*) in Spanish, *titre*
(not *en-tête*) in French, 見出し (not ヘッダー) in Japanese, *nagłówek* in Polish. The same care is worth taking with
"keyboard shortcut", which in some languages has a different word from a desktop shortcut (Spanish *atajo de teclado*,
not *acceso directo*).
* **Use the same wording in the settings and in the help.** The help page refers to the options by name, so an option
named one way in `html/configuration/` has to be named the same way in `html/help/`.
* **Don't change the markup.** In particular, keep the `data-version` attributes in the release notes, the `id` and
`for` attributes in the settings page, and the `<code>` elements around role names such as `banner` — those are the
literal role names and are not translated.
