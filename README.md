# Révision interactive — CSI 4506

Ouvrir `index.html` dans un navigateur récent. Le site fonctionne localement, sans installation ni dépendance externe.

## Contenu et format

- Huit chapitres reliés à `Slides_PDF/01.pdf` à `08.pdf`.
- Chaque banque initiale contient 15 vrai/faux et 10 choix multiples.
- Une séance standard tire 15 V/F et 10 QCM et dure au maximum 60 minutes, conformément aux indications du Quiz 1 dans `Slides_PDF/FAQ.pdf`.
- Le mode révision montre les corrections au fil de la séance; le mode examen les réserve aux résultats.
- Il s'agit de questions d'entraînement générées à partir des supports, pas de questions officielles.

## Modifier et agrandir la banque

Les questions vivent dans `question-bank.js`; l'interface est dans `app.js` et l'apparence dans `styles.css`. Les données sont définies dans l'objet `data`, séparément du rendu. Pour enrichir un chapitre, ajoute une rangée dans son tableau `tf` ou `mc` :

- V/F : `[énoncé, réponseBooléenne, indice, explication, concept, difficulté, pagePDF]`.
- QCM : `[question, indexCorrect0à3, choixABCD, indice, explicationsParChoix, concept, difficulté, pagePDF]`.

Conserve au moins 15 questions V/F et 10 QCM dans chaque banque pour remplir une session standard. Dès qu'une catégorie dépasse le quota, l'application tire aléatoirement les questions de cette catégorie. Chaque identifiant est généré à partir du chapitre et de sa position dans le tableau.

## Données et export

Les tentatives terminées sont gardées dans le `localStorage` de ce navigateur. Les exports incluent les choix, la réponse, l'indice, la difficulté, le concept, le corrigé et la source; l'export des erreurs inclut aussi les questions passées. Aucune donnée n'est envoyée à un service externe.
