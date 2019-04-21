<h1>SOMMAIRE</h1>
<details>
  <summary>Afficher / Masquer le sommaire</summary>
<p>
  
### [Unix-Terminal](https://github.com/Gab0o/Unix-Terminal#unix-terminal)  
- [Raccourcis clavier](https://github.com/Gab0o/Unix-Terminal/blob/master/README.md#raccourcis)
- [Commandes](https://github.com/Gab0o/Unix-Terminal/blob/master/README.md#commandes)
- [Gestion des fichiers et des dossiers](https://github.com/Gab0o/Unix-Terminal/blob/master/README.md#gestion-des-fichiers-et-dossiers)
### [Homebrew](https://github.com/Gab0o/Unix-Terminal#homebrew--)
- [Installation de Homebrew](https://github.com/Gab0o/Unix-Terminal#installation-de-homebrew)
- [Installation d'un package (eg. Tree)](https://github.com/Gab0o/Unix-Terminal#installation-dun-package-eg-tree)
- [Liste des packages installés](https://github.com/Gab0o/Unix-Terminal#packages-install%C3%A9s)
- [Désinstaller un package](https://github.com/Gab0o/Unix-Terminal#d%C3%A9sinstaller-un-package)
### [Python 3](https://github.com/Gab0o/Unix-Terminal/blob/master/README.md#python-3-1)
- [Installation via Anaconda3](https://github.com/Gab0o/Unix-Terminal/blob/master/README.md#installation-via-anaconda3)
- [Installation de Python 3 sans passer par Anaconda](https://github.com/Gab0o/Unix-Terminal/blob/master/README.md#installation-de-python-3-sans-passer-par-anaconda)

</p>
</details>

***

# Unix-Terminal

### RACCOURCIS
|Raccourci    | Description 
|:-----------:|:-----------------------------------------------
|**Tab**      | Auto-completion des noms de fichiers et dossiers
|**Ctrl + A** | Placer le curseur en début de ligne
|**Ctrl + E** | Placer le curseur en fin de ligne
|**Ctrl + U** | Effacer la ligne avant le curseur
|**Ctrl + K** | Effacer la ligne après le curseur
|**Ctrl + W** | Effacer le mot avant le curseur
|**Ctrl + T** | Inverser les 2 carcatères avant le curseur
|**Esc + T**  | Inverser les 2 carcatères après le curseur
|**Ctrl + C** | Kill la commande en cours d'éxecution
|**Ctrl + D** | Sortir du Shell en cours

### COMMANDES
|Commande          | Description 
|:-----------------|:-----------------------------------------------
| cd               | Répertoire source
| cd `[folder]`    | Changer de répertoire
| cd ../..         | Remonter deux répertoires parents
| ls               | Lister les fichiers
| ls -al           | Listing long avec fichiers cachés
| sudo `[command]` | Executer une commande en superuser
| open `[file]`    | Ouvrir un fichiers du répertoire actuel
| open .           | Ouvrir le répertoire actuel
| top              | Afficher les processus actifs ( *Press q to quit* ) 
| nano `[file]`    | Ouvrir le fichier dans l'éditeur du terminal
| clear            | Effacer le terminal

### GESTION DES FICHIERS ET DOSSIERS
|Commande                      | Description 
|:-----------------------------|:-----------------------------------------------
| touch `[file]`               | Créer un nouveau fichier
| mkdir `[dir]`                | Créer un nouveau dossier
| pwd                          | Afficher le chemin complet du répertoire actuel
| rm `[file]`                  | Supprimer un fichier
| rm -i `[file]`               | Supprimer avec confirmation
| rm -f `[file]`               | Forcer la suppression sans confirmation
| rm -i `[file]`               | Affichera un prompt avant la suppression
| cp `[file]` `[newfile]`      | Copier le fichier `file` vers `newfile`
| cp `[file]` `[dir]`          | Copier le fichier `file` vers le répertoire `directory`
| mv `[file]` `[new filename]` | Déplacer / Renommer le fichier `file` vers la destination `new filename`
| rmdir `[dir]`                | Supprimer le répertoire ( *Ne fonctionne que dans un répertoire vide* )
| rm -R `[dir]`                | Supprimer le répertoire et son contenu

# Homebrew <a href ="https://brew.sh/index_fr"> <img src="https://upload.wikimedia.org/wikipedia/commons/3/34/Homebrew_logo.png" width="50" height="40">  

### Installation de Homebrew
Pour installer Homebrew, taper la commande suivante dans le terminal  
```
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

### Installation d'un package (eg. Tree)
Tree est un utilitaire permettant d'afficher contenu du dossier actuel sous forme d'arborescence.  

<img src="https://i.stack.imgur.com/NejY0.png" width="350" height="300">  

```
$ brew install tree
```
Il est possible de limiter le nombre de sous-dossiers affichés en utilisant la commande `-L`
```
$ tree -L 1
```

### Packages installés
Pour afficher la liste des packages Homebrew installés, taper la commande suivante.
```
$ brew deps --tree --installed
```

### Désinstaller un package
Pour désinstaller un package Homebrew, taper la commande suivante.
```
$ brew remove [package name]
```

# Python 3
### Installation via Anaconda3  
<a href ="https://docs.anaconda.com/anaconda/install/mac-os/"> <img src="https://docs.anaconda.com/_static/images/logos/logo-docs.svg" width="400">  
</a>
Une fois l'installation effectuée, il faut modifier le fichier bash pour indiquer l'emplacement de l'installation d'Anaconda. Cela permet d'utiliser les gestionnaires de package pip et conda.  
Pour modifier le fichier bash, lancer la commande `$ sudo nano ~/.bash_profile`.   
Y ajouter la ligne suivante:
```
export PATH=~/anaconda3/bin:$PATH
```
Rafraichir le fichier .bash avec la commande suivante:
```
$ source ~/.bash_profile
```

### Installation de Python 3 sans passer par Anaconda
```
$ brew install python3
$ brew install python3-pip
```

# Extensions pour Jupyter Notebook  
### Installation  
Avant tout, il faut mettre à jour le notebook Jupyter.  
La commande suivante va installer, mettre à jour et vérifier que Jupyter Notebook est installé sur la machine.
```
$ conda install jupyter notebook nb_conda
```  
Il faut ensuite installer 2 packages depuis le channel conda-forge: `jupyter_contrib_nbextensions` and `jupyter_nbextensions_configurator`.  
Le premier package installe les extensions, et le second (configurator) permet de gérer ces extensions.
```
$ conda install -c conda-forge jupyter_contrib_nbextensions jupyter_nbextensions_configurator
```  
Pour gérer les extensions, il faut d'abore lancer un Jupyter Notebook.
```
$ jupyter notebook
```
Il faut ensuite se rendre sur la page `localhost:6006/extensions` pour voir la liste des extensions et modifier leurs paramètres.  

<img src="https://www.endtoend.ai/assets/blog/jupyter-notebook-extensions-to-enhance-your-efficiency/configurator.png">

### Hinterland  
Hinterland permet d'activer l'autocompletion pour chaque touche tapée dans le notebook, plutot que de l'appeler avec la touche `Tab`.  

### Variable Inspector  
Variable Inspector permet d'afficher les variables déclarées dans une fenêtre flottante, avec leur type, taille et contenu.  
<img src="https://www.endtoend.ai/assets/blog/jupyter-notebook-extensions-to-enhance-your-efficiency/variable_inspector.gif">
