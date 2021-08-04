# docs

New instantOS documentation based on mkdocs instead of jekyll

## Adding new translation

To add new translation, you should follow these steps:
- go to `extra.alternate` section in `mkdocs.yml`
    - add new item with your language data, eg.:
        ```
        - name: English
          link: /en
          lang: en
        ```
- create new file with your language's short form as its name (eg. `en.html`) in `/meterial-i18n/partials/nav-translations` folder and copy its content from other files with translations (eg. `pl.html`). **Remember that `en.html` file should be empty!**
- populate created file with your translations for navbar links
- create directory with your language name's short form as its name (eg. `en`) is `/docs` directory.
- copy content from `/en` directory and paste it in your folder
- write docs in your language!