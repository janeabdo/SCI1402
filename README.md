# SCI1402
<h1> Classification de types de mouvements imaginés à partir de signaux EcoG  </h1>
<h3> <strong>Introduction:</strong> </h3>
Une variété de types de mouvements peuvent être décodés à partir des signaux cérébraux pendant l'exécution du mouvement, incluant: flexion et extension du poignet, saisie, mouvement des doigts…  (<a href= "https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6901702/ "> Volkova et al, 2019</a>). Ces signaux décodés peuvent ensuite être utilisés pour contrôler des appareils externes, tels qu'un curseur d'écran, une souris ou une prothèse. Certaines populations handicapées, comme les personnes paralysées ou amputées, pourraient grandement bénéficier du contrôle de ces appareils. Comme ils ne reçoivent pas de signaux cérébraux associés à l'exécution du mouvement, d'autres moyens de contrôler les dispositifs externes sont nécessaires. Heureusement, des études ont montré que l'imagerie motrice (imaginer l’exécution d’un mouvement) et le contrôle moteur (exécuter réellement un mouvement) partagent des mécanismes neuronaux, en activant des régions cérébrales similaires (<a href= "https://pubmed.ncbi.nlm.nih.gov/18819106/ "> Guillot et al, 2009</a>).
<br> La question est donc : pouvons-nous décoder les types de mouvements en fonction des signaux cérébraux provenant de mouvements imaginés ? 
<br> Il existe de nombreuses méthodes d'extraction des signaux cérébraux, la moins invasive (et en réalité non invasive) étant l'EEG (électroencéphalographie). Cependant, en raison de la localisation des électrodes sur le cuir chevelu, le signal est déformé par le cuir chevelu et le crâne. D'autres techniques plus invasives incluent l'EcoG (électrocorticographie), où les électrodes sont placées à la surface du cortex. Cette technique s'est avérée offrir une meilleure qualité de signal.
<br> La question devient alors : pouvons-nous décoder les types de mouvements à partir des signaux cérébraux EcoG issus de mouvements imaginés ?
<br> Un groupe d'étudiants a posé les bases de cette question lors d'un cours en ligne de neurosciences computationnelles appelé  <a href= "https://compneuro.neuromatch.io/"> Neuromatch</a>. Ils ont notamment développé un classificateur permettant de décoder les types de mouvements à partir de signaux EcoG imaginés et exécutés. Ce classificateur constituera la base de mon projet.
<h3> <strong>Données:</strong> </h3>
Les données brutes proviennent d’une source publique  (<a href= "https://pubmed.ncbi.nlm.nih.gov/31451738/ "> Miller et al, 2019</a>). Les données utilisées pour ce projet ont été téléchargées à partir d'une source prétraitée provenant du site web de <a  href = "https://osf.io/ksqv8"> Neuromatch Academy </a>.
<h3> <strong>Livrables:</strong> </h3>
Deux notebooks Jupyter : un pour le traçage 3D des cerveaux, et un pour le prétraitement, la classification et la visualisation des données des performances du classificateur.<h3> <strong> Tools :</strong> </h3> 
Un fichier requirements.txt.
<h3> <strong> Méthodes & Résultats:</strong> </h3>
L’examen des données a été le point de départ. Ce faisant, j’ai constaté que le positionnement des électrodes variait selon les sujets. L’étude ayant été réalisée dans le cadre d’un monitorage épileptique préopératoire, l’emplacement des électrodes dépendait de la source approximative de l’épilepsie. Les cerveaux 3D avec les électrodes de chaque individu ont été représentés. Seules les électrodes présentes dans les gyrus précentraux et postcentraux ont été sélectionnées, car ces régions sont impliquées dans l’exécution et l’imagination du mouvement.
<img src="https://github.com/janeabdo/SCI1402/blob/main/cerveaux.png"> 
Cliquez <a href="https://brainhack-school2024.github.io/abdo_project/images/3dbrain_electrodes.html">ici</a> pour la version interactive : 
Les performances du classificateur sur chaque individu ont ensuite été tracées.

Les étapes suivantes visaient à améliorer la classification. Trois classificateurs ont été comparés.
<br>Le premier, appelé SVM original, est une machine à vecteurs de support issue du projet NeuroMatch original.
<br> Le deuxième, appelé SVM RFE, est une version modifiée du premier SVM, avec une standardisation des données supplémentaire et une sélection de caractéristiques (par RFE).
<br> Le troisième, appelé Random Forest, est un classificateur de forêt aléatoire avec une standardisation des données et une sélection de caractéristiques par RFE.

Les trois classificateurs ont été comparés dans les conditions de mouvement réelles et imaginaires.
<br> Pour le mouvement réel :
<img src="https://github.com/janeabdo/SCI1402/blob/main/mouvement_reel_classifie.png" >
Cliquez <a href="https://github.com/janeabdo/SCI1402/blob/main/Mouvement_Reel.html">ici</a> pour la version interactive.
<br> Pour le mouvement imaginé:
<img src="https://github.com/janeabdo/SCI1402/blob/main/mouvement_imagine_classifie.png" >
Cliquez <a href="https://github.com/janeabdo/SCI1402/blob/main/Mouvement_Imagine.html">ici</a> pour la version interactive.
<h3> <strong> Conclusion :</strong> </h3>
Contrairement à ce que je pensais, il semble qu’aucun classificateur ne soit optimal pour tous ; les données de chaque individu nécessitent une approche personnalisée pour une performance optimale.
<br>Heureusement, chaque individu disposait d’au moins un classificateur avec une précision supérieure à 50 %.
<br>Pour revenir à la question initiale : peut-on décoder les types de mouvement à l’aide de signaux EcoG de mouvement imaginés ?
<br>Les résultats de ce projet sont quelque peu peu concluants. Certains individus présentent une assez bonne précision de classificateur, mais le niveau de précision nécessaire pour confirmer que les types de mouvement sont décodables reste incertain.
<br>Les causes possibles de ce manque de fiabilité sont : les données EcoG sont trop bruitées pour être correctement classées, les données sont insuffisantes et/ou l’imagination du mouvement n’était pas suffisamment fiable chez certains individus. Les futurs projets devraient expérimenter des techniques d’augmentation des données et différentes approches de classificateur.
<h3> <strong> Références :</strong> </h3>
<ol>
<li> Volkova K, Lebedev MA, Kaplan A, Ossadtchi A. Decoding Movement From Electrocorticographic Activity: A Review. Front Neuroinform. 2019 Dec 3;13:74. doi: 10.3389/fninf.2019.00074. PMID: 31849632; PMCID: PMC6901702.</li>
<li>Miller KJ. A library of human electrocorticographic data and analyses. Nat Hum Behav. 2019 Nov;3(11):1225-1235. doi: 10.1038/s41562-019-0678-3. Epub 2019 Aug 26. PMID: 31451738.</li>
<li>Guillot A, Collet C, Nguyen VA, Malouin F, Richards C, Doyon J. Brain activity during visual versus kinesthetic imagery: an fMRI study. Hum Brain Mapp. 2009 Jul;30(7):2157-72. doi: 10.1002/hbm.20658. PMID: 18819106; PMCID: PMC6870928.</li>
