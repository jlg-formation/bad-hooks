# ⚠️ Après avoir lu ce repository et compris son fonctionnement, vous ne téléchargerez plus de repo sur GitHub avec le même sentiment de sécurité.

# bad-hooks

## Référence

Pour comprendre ce qu'est un hook dans le contexte de GitHub Copilot et Visual Studio Code, consultez la documentation officielle :
https://code.visualstudio.com/docs/copilot/customization/hooks

## But du dépôt

Ce dépôt a pour objectif de démontrer la dangerosité potentielle des hooks dans un projet. Il illustre comment un simple clonage ou téléchargement du dépôt, suivi de l'ouverture d'un chat dans VS Code avec GitHub Copilot, peut déclencher l'exécution automatique d'un hook qui lance du code sur la machine de l'utilisateur.

Dans cet exemple, le hook crée simplement un fichier quelque part sur l'ordinateur sous Windows, mais il pourrait tout aussi bien exécuter du code malveillant.

## Comment ça fonctionne

1. **Clonage ou téléchargement** : L'utilisateur clone ou télécharge ce dépôt sur sa machine Windows.
2. **Ouverture dans VS Code** : L'utilisateur ouvre le dossier dans Visual Studio Code.
3. **Activation du hook** : Lorsqu'un chat est ouvert avec GitHub Copilot, un hook est appelé automatiquement.
4. **Exécution du code** : Le hook exécute un script qui crée un fichier sur l'ordinateur (démonstration de l'exécution automatique de code).

## Mise en garde

- Ce dépôt est à but pédagogique et démontre un risque de sécurité.
- N'exécutez jamais de code ou de hooks provenant de dépôts non fiables.
- Vérifiez toujours le contenu des hooks dans `.github/hooks/` ou `.git/hooks/` avant d'ouvrir un projet téléchargé.

## Exemple de hook

Le script concerné se trouve dans le dossier `.github/hooks/` et s'exécute automatiquement dans certains contextes.

---

**Attention :** Ce dépôt ne doit pas être utilisé à des fins malveillantes. Il sert uniquement à sensibiliser sur les risques liés aux hooks dans les projets partagés.

---

Après avoir lu ce repository et compris son fonctionnement, vous ne téléchargerez plus de repo sur GitHub avec le même sentiment de sécurité.
