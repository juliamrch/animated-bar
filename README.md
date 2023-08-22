
# Docura Theme for Clever Cloud

This repo is a migartion test for Clever Cloud. Files are being progressively imported to fit into the theme.

## How to...

### ... include files in the sidebar

Files need to be properly indexed in order to appear in the sidebar, to work with [Hugo Data Templates](https://gohugo.io/templates/data-templates/).

1. Add the file's title in `data/en/docs`, for example:
  
  ```yaml
  - title: Get Started
  pages:
    - title: Quickstart
    - title: SSH Keys
```

2. Add the following metadata to the file:

```yaml

url: "/docs/<slug>"

aliases:
- "/docs"
```

For example, for `ssh-keys.md`, the following metadata has been added:

```yaml
url: "/docs/ssh-keys"

aliases:
- "/docs"
```

Now, no matter the file's localization, the file url will be `http://<domain>/docs/ssh-keys/`.

### ...build/serve locally the site

If you just import content from the previous site, Hugo won't be able to build your site, because files contains obsolete path references and inexistent shortocdes in this theme.

If you want to import old content and build the site, follow this procedure:

1. Import a folder containing the files
2. Comment all shortcodes with {{/*< shortcode, etc >*/}}
3. Comment all references as well {{/*< ref, etc >*/}}
4. Serve the site with `hugo server`

Importing shortcodes is tricky, so no documentation is available right now until test had have been performed.

💡 Add any desired feature using /label ~feature labels.
