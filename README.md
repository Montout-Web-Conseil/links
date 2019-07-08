# links
Plugin de gestion de liens externes sous WordPress

## Fonctionnalités
Permet de gérer (ajouter, supprimer, affiche) une liste de liens sur un site WordPress.

## Versions
### Version 1.0
L'utilisateur rentre manuellement les informations.

## Structure
|champ|type|cpt|contenu|
|:-----|:----|:---|:-------|
|title|-|-|Nom de l'assocition ou de l'organisme = nom du lien|
|ref|url|oui|Référence du lien|
|e_blank|boolean|oui|Target _blank|
|thumbnail|-|-|Thumbnail (image - image par défaut)|
|commentaire|text|oui|Commentaire|

## Methodes

### mwc_get_links()
```php
mwc_get_links( $options = array() )
```
- Renvoie un tableau des liens.
  - html : la structure html du lien
  - img_url : l'url de l'illustration
  - img_tag : la structure html de l'illustration
  - comment : le commentaire

### mwc_display_links()
```php
mwc_display_links( $options = array() )
```
- Affiche une liste **simple** de liens.

### $options
```php
array(
    'class_name' => 'mwc-lien',
    'img_size' => 'thumbnail',
    'display_external_link_icon' => true,
    'category'=> slug_de_la_catégorie
);
```
Class names `class_name` (string | array) will be added to default.


Customs images size `img_size` (string) : medium, medium_large, large.
Will replace default.

Display external link icon `display_external_link_icon` (boolean).

Filtre sur **une** catégorie.
`category` (string) : le slug de la catégorie.
Par défaut ce paramètre est absent de la requête.


### Shortcode
Un shortcode est disponible pour afficher une liste de liens :
```php
[mwc_display_links]
[mwc_display_links class="col-xs-12 col-md-10" display_external_link_icon="false"]
[mwc_display_links categorie="slug_de_la_catégorie"]
```
**Attention !** Si on utilise Gutenberg, penser à choisir un bloc **paragraphe**.
