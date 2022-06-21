# Slider 
## Nouvelles compétences
Vous connaissez désormais les outils qui permettent de créer une interface dynamique en faisant dialoguer 
***JavaScript*** avec le code source ***HTML*** du document grâce à l'***API DOM***.

## Ressources
### Gérer les classes des éléments du DOM avec l'API classList

[API classList (mdn)](https://developer.mozilla.org/fr/docs/Web/API/Element/classList)

    element.classList.add('classe');
    element.classList.remove('classe');
    element.classList.toggle('classe');
    
### Sélection d'un élément à partir d'un attribut
Il est possible de sélectionner un élément à partir de la valeur d'un ***attribut***, comme par exemple un attribut-data.

[Sélection à partir d'attributs (mdn)](https://developer.mozilla.org/fr/docs/Web/CSS/S%C3%A9lecteurs_d_attribut)

    const element = document.querySelector('[attribut="value"]');
    
### Gérer les événements clavier

- [Evénément keydown (mdn)](https://developer.mozilla.org/fr/docs/Web/API/Document/keydown_event)
- [Evénément keyup (mdn)](https://developer.mozilla.org/fr/docs/Web/API/Document/keyup_event)

### Annuler le comportement par défaut du navigateur
Il est parfois nécessaire d'annuler ce que le navigateur fait par défaut lorsqu'un événement particulier se produit. 

#### Exemples de comportements par défaut :

- Soumettre un formulaire au clic sur le bouton de soumission
- Changer de page au clic sur un lien
- Faire défiler la page lorsqu'on appuie sur la barre d'espace


    function myEventHandler(event){
        event.preventDefault();
        
## Bonus 1 / 2
### Création d'éléments et insertion dans le DOM
L'API DOM permet non seulement de modifier les éléments du DOM existants dès le départ dans le code source HTML, mais également de créer de nouveaux éléments.

#### Création d'un élément

    const element = document.createElement('li');    
    
[document.createElement (mdn)](https://developer.mozilla.org/fr/docs/Web/API/Document/createElement)
    
### Insertion d'un élément dans le DOM

    parentElement.appendChild(childElement); 
    
[document.appendChild (mdn)](https://developer.mozilla.org/fr/docs/Web/API/Node/appendChild)
        
### Délégation d'événement
Il est parfois nécessaire d'installer un gestionnaire d'événement sur des éléments qui seront créés
de manière dynamique et qui n'existent pas encore au moment où on souhaite installer le gestionnaire d'événement. 

Une solution est la délégation d'événement : installer le gestionnaire sur un élément parent qui existe bien au départ
dans le code source HTML. Dans la fonction gestionnaire d'événement, on regardera ensuite quel élément précisément intervient dans l'événement,
grâce à la propriété target de l'objet event récupéré en paramètre. On peut vérifier si cet élément possède telle classe, ou tel id, 
ou si l'élément correspond à un sélecteur particulier grâce à element.matches().

    function myEventHandler(event){
        const target = event.target;
        if(target.matches('selector')){
        
- [element.matches (mdn)](https://developer.mozilla.org/fr/docs/Web/API/Element/matches)
- [Délégation d'événement (en)](https://davidwalsh.name/event-delegate)

### API dataset
Les attributs data- sont des attributs HTML personnalisables et manipulables en JavaScript comme n'importe quel attribut. 
Ils vont permettre de stocker une information associée intrinsèquement à un élément du DOM. 

    element.dataset.myAttribute = 'some value';

    const value = element.dataset.myAttribute
    
[API dataset (mdn)](https://developer.mozilla.org/fr/docs/Web/API/HTMLElement/dataset)