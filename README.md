# Blogu' lu' Yeti

Tema site-ului personal yeti.albascout.ro: bară laterală cu logo, fundal închis, articole pe carduri albe (după Twenty Fifteen).

Temă de publicare pentru VolunHub (slug: `yeti`). Este doar șabloane, fișiere
statice și un manifest (`theme.toml`), fără cod Python. Referință completă:
`docs/publishing-themes.md` din repository-ul VolunHub.

## Structură

```
theme.toml                                   manifest: versiune, tokeni, configurare
templates/themes/yeti/publishing/
    base_site.html                           învelișul paginii; începe de aici
    static_page.html, article_page.html,
    blog_index_page.html                     paginile suprascrise (restul cad pe șabloanele platformei)
static/themes/yeti/css/theme.css, fonts.css    stiluri; fonturile (Lora, Encode Sans Condensed, Noto Sans) sunt în static/themes/yeti/fonts/ (SIL OFL)
static/themes/yeti/img/logo.png              logo implicit (suprascris de cheia `logo`)
```

## Previzualizare locală

Din repository-ul VolunHub, cu mediul activat:

```bash
python manage.py theme_preview /calea/către/yeti
# Site-uri -> editează site-ul -> Temă vizuală = „Blogu' lu' Yeti”, apoi:
python manage.py runserver 8003
# la final:
python manage.py theme_preview /calea/către/yeti --remove
```

## Publicare

1. Urcă directorul pe GitHub (`volunhub-theme-yeti`): `theme.toml` trebuie să fie în rădăcina repository-ului.
2. Pune un tag SemVer care să coincidă cu `version` din `theme.toml`: `git tag v0.1.0 && git push --tags`.
3. În VolunHub, `/publicare/teme/` -> lipește adresa repository-ului și alege tag-ul.
4. Rulează `collectstatic` o dată, apoi alege tema în formularul Site-ului.
