# Parcours Hybridation

[![Actions Status](https://github.com/LUniversiteNumerique/parcours-hybridation/workflows/Yamllint/badge.svg)](https://github.com/LUniversiteNumerique/parcours-hybridation/actions)

## Structure d'un fichier de diplome :

```yaml
id: ID UNIQUE DU DIPLOME
name: NOM DU DIPLÔME
description:
years:
  - name: NOM DE L'ANNÉE
    ue:
      - name: NOM DE L'UE
        resources:
          - name: NOM DE LA RESSOURCE
            type: TYPE DE LA RESSOURCE
            volume: VOLUME DE LA RESSOURCE
            url: URL DE LA RESSOURCE
            licence:
              - name: "CC"
                image: "https://luniversitenumerique.fr/images/cc.svg"
              - name: "BY"
                image: "https://luniversitenumerique.fr/images/by.svg"
              - name: "NC"
                image: "https://luniversitenumerique.fr/images/nc.svg" LICENCE DE LA RESSOURCE (ou vide)
```

## Ajouter une nouvelle entrée dans un champ disciplinaire :

1. Insérer une entrée dans le fichier `fields.yml` en respectant la hiérarchie :

```yaml
fields:
  - name: NOM DU CHAMP DISCIPLINAIRE
    diplomas:
      - id: ID UNIQUE DU DIPLOME
      name: NOM DU DIPLÔME
```

2. Créer le fichier `.yml` dans le dossier correspondant en le nommant avec son ID UNIQUE en début de fichier.
   Exemple : `46-nom-du-diplome.yml`

## Github Workflows

This repository performs the `url_scan` workflow on push on the main branch.

It should triggers a repository dispatch to perform the URL scan in another repository.

This requires an active **Personal Access Token (PAT)**.

To create a PAT, go in your Github profile under _Developer settings > Personal access tokens > Fine-grained tokens_ and generate a new token.

Settings : `Only select repositories` (select the target repos)

- Contents: `Read & write`
- Actions: `Read & write`
- Webhooks: `Read & write`
