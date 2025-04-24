Yassmine doggaz & Salwa chaouachi \- 1ére Master BC

# **Génération automatique de slogans publicitaires via des modèles de NLP : Approche comparative**

![][image1]

**Phase 1 : Problématique et état de l’art**

1. **Présentation de la problématique**  
    La communication publicitaire repose fortement sur des slogans percutants, capables de résumer l’identité d’une marque en quelques mots. La création manuelle de tels slogans est souvent coûteuse, subjective et chronophage. Avec l’émergence de l’intelligence artificielle et du traitement automatique du langage naturel (NLP), il est désormais possible d’automatiser cette tâche créative. Dans ce projet, nous avons cherché à explorer différentes approches de génération automatique de slogans publicitaires à partir d’un corpus existant. Notre objectif était d’évaluer la capacité de ces approches à produire des slogans originaux, pertinents et proches du langage marketing humain.

2. **État de l’art**  
    L’état de l’art en génération automatique de texte se divise en plusieurs grandes familles de méthodes :

* **Modèles statistiques (N-grammes)**  
   Les N-grammes sont des modèles probabilistes simples qui capturent la cooccurrence locale des mots. Bien qu’ils soient peu coûteux en calcul, ils manquent de cohérence globale.

* **Modèles séquentiels (RNN, LSTM, GRU)**  
   Ces modèles apprennent les dépendances dans des séquences de texte. Ils sont capables de générer du texte plus fluide mais souffrent parfois de problèmes de mémoire à long terme.

* **Modèles transformeurs (GPT-2, GPT-3.5, GPT-4)**  
   Ces modèles pré entraînés sur de très grands corpus sont aujourd’hui les plus performants. GPT-2 permet un fine-tuning sur des données spécifiques, tandis que GPT-3.5/4 peuvent être utilisés via des prompts sans entraînement supplémentaire.

* **Prompt engineering**  
   Cette approche consiste à utiliser des instructions bien formulées pour guider un grand modèle de langage (comme GPT-4) à produire du contenu adapté sans avoir besoin de données d’apprentissage supplémentaires.

**Sources :**

* Jurafsky, D., & Martin, J. H. (2020). Speech and Language Processing. Pearson.

* Brown, T. et al. (2020). Language Models are Few-Shot Learners. NeurIPS.

* Bengio, Y. et al. (2003). A Neural Probabilistic Language Model.

* Survey: “A Survey on Text Generation Techniques for Marketing Content”, 2022, arXiv.

* OpenAI documentation: [https://platform.openai.com/docs](https://platform.openai.com/docs)

**Phase 2 : Implémentation et analyse des méthodes**

1. **Choix des méthodes à utiliser**  
    À partir de l’état de l’art, nous avons choisi quatre méthodes à implémenter :

* **N-grammes :** une approche classique basée sur des probabilités statistiques.

* **Réseaux de neurones récurrents (RNN)** : une approche séquentielle permettant de modéliser des dépendances temporelles.

* **GPT-2** : un modèle pré entraîné basé sur les transformateurs, offrant une génération de texte fluide.

* **GPT-3.5 ou GPT-4 avec prompt engineering** : une approche moderne utilisant des invités bien formulés pour produire des slogans sans fine-tuning.

2. **Compréhension et analyse des méthodes choisies**

* **N-grammes :**  
   Principe : Nous avons utilisé les probabilités de cooccurrence des mots pour prédire le mot suivant dans une séquence.  
   Avantages : Simplicité et faible besoin en données.  
   Inconvénients : Manque de prise en compte du contexte global.

* **Réseaux de neurones récurrents (RNN) :**  
   Principe : Les RNN prennent en compte l’historique d’une séquence grâce à une mémoire interne.  
   Avantages : Bonne gestion du contexte local.  
   Inconvénients : Difficile à entraîner sur de longues séquences.

* **GPT-2 :**  
   Principe : GPT-2 est basé sur les transformateurs et prédit chaque mot à partir du contexte précédent.  
   Avantages : Excellente qualité de génération, surtout avec un fine-tuning léger.  
   Inconvénients : Consommation élevée de ressources.

* **GPT-3.5 ou GPT-4 avec prompt engineering :**  
   Principe : Nous avons conçu des prompts pour guider un grand modèle pré entraîné dans la génération de slogans.  
   Avantages : Très bonne qualité de génération sans entraînement.  
   Inconvénients : Dépendance à l’API d’OpenAI et coût associé.

3. **Implémentation des méthodes**  
    Nous avons implémenté chaque méthode en Python, en utilisant le fichier slogans.csv comme base de données. L’ensemble du code source est disponible dans le fichier Python associé à ce rapport.

4. **Étude comparative et simulations**  
    Une fois les méthodes implémentées, nous avons réalisé des simulations pour comparer leurs performances sur les mêmes données.

**Critères de comparaison :**

* Qualité des slogans générés : créativité, pertinence, et longueur.

* Temps de calcul : durée moyenne nécessaire pour générer un slogan.

* Complexité de l’implémentation : facilité de mise en œuvre et de déploiement.

Voici un tableau comparatif clair des quatre méthodes de génération automatique de slogans que vous avez implémentées :

| Critère | N-grammes | RNN | GPT-2 | GPT-3.5 / GPT-4 (Prompt Engineering) |
| ----- | ----- | ----- | ----- | ----- |
| **Principe** | Modèle statistique basé sur la cooccurrence de mots | Réseau neuronal séquentiel | Modèle Transformer pré entraîné | Utilisation de prompts sur modèle pré entraîné |
| **Qualité des slogans** | Faible : souvent répétitif ou incohérent | Moyenne : syntaxe correcte, peu créatif | Bonne : fluide et plus naturel | Très bonne : slogans cohérents et marketing |
| **Pertinence marketing** | Faible à moyenne | Moyenne | Bonne | Excellente |
| **Créativité** | Très limitée | Moyenne | Bonne | Très bonne |
| **Prise en compte du contexte** | Très locale (2-3 mots maximum) | Moyenne (contexte court à moyen) | Bonne (contexte long possible) | Excellente (contexte étendu avec instructions) |
| **Temps de calcul** | Très rapide | Moyen à élevé | Élevé | Très rapide (côté utilisateur) |
| **Complexité d’implémentation** | Très simple | Moyenne | Complexe (besoin de ressources) | Simple (via API, sans entraînement) |
| **Ressources nécessaires** | Très faibles | Moyennes | Élevées | Faibles (externalisées via API) |
| **Facilité de personnalisation** | Faible | Moyenne (nécessite entraînement) | Bonne (fine-tuning possible) | Très bonne (prompting flexible) |
| **Coût d’utilisation** | Aucun | Aucun | Aucun (en local, si GPU dispo) | Coût lié à l’API OpenAI |

🔍 Synthèse :

* Si l’on cherche la simplicité et la rapidité → N-grammes.

* Si l’on veut apprendre à modéliser du texte en profondeur → RNN.

* Si l’on veut un bon compromis entre qualité et contrôle → GPT-2.

* Si l’objectif est la performance maximale sans entraîner de modèle → GPT-3.5 / GPT-4 avec prompt engineering.

**Conclusion**  
 À travers ce travail, nous avons pu explorer quatre approches différentes pour la génération automatique de slogans publicitaires. Notre étude comparative a mis en évidence les forces et faiblesses de chaque méthode. Si les modèles simples comme les N-grammes sont accessibles et rapides à mettre en œuvre, ils restent limités dans la qualité des résultats. Les RNN offrent de meilleurs résultats mais nécessitent plus de ressources. Les modèles de type GPT, notamment avec l’usage du prompt engineering, se sont révélés particulièrement efficaces pour générer des slogans originaux et pertinents.

Ce projet nous a permis d’approfondir nos connaissances en NLP et d’expérimenter concrètement différentes techniques modernes de génération de texte.

[image1]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAnAAAAAECAYAAAAOPwJdAAAANElEQVR4Xu3WMQ0AMAwEseAOoJIpqGYvgrzkwcshuLqnHwAAOeoPAADsZuAAAMIYOACAMAOTpGslhjl7rwAAAABJRU5ErkJggg==>