# huaweicloud-knowledge-base

This repository hosts the public collaborative knowledge base for Huawei Cloud services, containing technical guides for specific implementation scenarios.

Access the published site here: <https://knowledge-base-hwc.duck.tec.br>

Available in English and Portuguese. Use the search bar or the navigation menu to browse the knowledge base.

## Contributing

1. [**Fork the preview repository**](https://github.com/huaweicloud-latam/knowledge-base-preview/fork)
2. Add or update documentation in Markdown format (`docs` folder);
3. Upload related assets to `assets/images` folder
4. Enable GitHub Pages under repository Settings > Pages
5. Enable Actions workflows
6. Run `Deploy Jekyll site to Pages` manually
7. Verify the generated preview website (should be something like `https://{your-username}.github.io/huaweicloud-knowledge-base-preview`)
8. If your preview website looks OK, submit a pull request to the knowledge-base-preview repository.

**Important:** There are two repository versions:

- `huaweicloud-latam/knowledge-base-preview`: staging repository used for review and validation
- `huaweicloud-latam/knowledge-base`: production repository, accepts sync updates only

All pull requests must target `knowledge-base-preview`.

## Repository structure

This repository is structured as follows:

- `/docs`: directory where documentation files are stored. In this directory, upload the desired documentation following the structure `/docs/{service-category}/{service-name}/{documentation-name}.md`. If the documentation is written in Portuguese, modify the file suffix to `.pt.md`;
- `/assets/images`: directory where images of documentation files are stored. In this directory, upload the documentation assets following the structure `/assets/images/{service-category}/{service-name}/{documentation-name}/example.png`

You may refer to the documentation files present in this repository as examples.

### Document Headers

All Markdown files **must** have the following header for proper indexing:

```yaml
---
title: {documentation title}
layout: default
parent: {HWC service name} ({HWC service acronym})
grand_parent: {HWC service category}
permalink: /docs/{HWC service category}/{HWC service acronym}/{documentation title}
lang: pt  # only for Portuguese version
---
```

Example (English):

```yaml
---
title: Migrating K8S Cluster Using Velero
layout: default
parent: Cloud Container Engine (CCE)
grand_parent: Containers
permalink: /docs/containers/cce/migrating-k8s-cluster-using-velero
---
```

Example (Portuguese):

```yaml
---
title: Migrando Cluster K8S Usando Velero
layout: default
parent: Cloud Container Engine (CCE)
grand_parent: Containers
lang: pt
permalink: /docs/containers/cce/migrating-k8s-cluster-using-velero
---
```

## Adding a Custom Domain

It is also possible to add a custom domain name for the GitHub Pages deployment of this knowledge base. In order to do so:

1. Add the following repository variable in the target repository settings: `CUSTOM_PAGES_DOMAIN`, in which the variable value is the domain to be used;
2. Add a custom domain name to the GitHub Pages on the Settings page of the repository. For reference on this topic, you can consult the following page: [documentation](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site).

## Roadmap

- [ ] Compress large image files and rewrite repository history to reduce repository storage space;
- [ ] Optimize documentation writer experience, especially related to images (images in the Markdown file can't be previewed locally);
- [ ] Record and publish training video showing how to contribute.

## Acknowledgments

Based on [Just the Docs](https://just-the-docs.com/) Jekyll theme.

## Maintainers

This project is maintained by the Brazil Cloud Delivery & Service Department of Huawei Cloud.

Led by:

- [Gabriel Gutierrez Pereira Soares](https://github.com/gutierrezps)
- [Diogo Lourenzon Hatz](https://github.com/Hatz-D)
