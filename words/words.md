<div class="section">
    <div>
    	<iframe id="splash" width="960" height="480" src="banners/splash.html"></iframe>
        <div style="top: 70px;font-size: 75px;font-weight: bold;">
        	Ce qui nous attend.
       	</div>
		<div style="font-weight: 500;top: 140px;left: 10px;font-size: 29px;">
			Les futurs du COVID-19, expliqués par des simulations interactives
		</div>
		<div style="font-weight: 100;top: 189px;left: 10px;font-size: 19px;line-height: 21px;">
			<b>
				🕐 30 min de jeu/lecture
				&nbsp;&middot;&nbsp;
			</b>
			by
			<a href="https://scholar.google.com/citations?user=_wHMGkUAAAAJ&amp;hl=en">Marcel Salathé</a>
			(epidemiologist)
			&
			<a href="https://ncase.me/">Nicky Case</a>
			(art/code)
		</div>
	</div>
</div>

"La seule chose dont il faille avoir peur est la peur elle-même" - Franklin D. Roosevelt. Conseil douteux.

Bien sûr, on nous rappelle à raison de ne pas se ruer sur le papier toilette. Mais si les responsables politiques craignent la peur et le désordre, ils minimiseront aussi les véritables dangers pour éviter toute panique générale. La peur n'est pas un problème. Le problème est la manière dont nous la canalisons. La peur nous donne l'énergie pour faire face aux dangers de l'instant, et nous prépare aux dangers futurs.

Pour être honnête, nous (Marcel - épidémiologiste et Nicky - art/code) sommes inquiets. Tu l'es aussi n'est-ce pas? C'est pourquoi de nos peurs sont nées ces **simulations interactives**, pour que *tu* puisses à ton tour canaliser tes peurs et comprendre:

* **Ces derniers mois** (initiation à l'épidémiologie, modèle SEIR, R et R<sub>0</sub>)
* **Les mois à venir** (confinement, traçage de contacts, masques)
* **Les années à venir** (perte d'immunité? vaccin introuvable?)

Ce guide (publié le 1er Mai 2020. clique sur cette note!→[^timestamp]) est censé *et* vous donner de l'espoir, *et* vous faire peur. Pour vaincre le COVID-19 **en préservant aussi nos santés mentals et financières**, nous devons faire preuve d'optimisme pour élaborer des plans, et de pessimisme pour élaborer des plans B. Comme l'a dit un jour Gladys Bronwyn Stern, *“L'optimiste invente l'avion, le pessimiste invente le parachute.”*

[^timestamp]: Ces notes contiendront des sources, des liens et des commentaires bonus comme celui-ci!
    
    **Ce guide a été publié le 1er Mai 2020.** De nombreux détails deviendront obsolètes, mais nous sommes convaincus que ce guide couvre 95% des futurs possibles, et que notre initiation à l'épidémiologie vous sera bien utile.

Alors accrochez-vous: nous entrons dans une zone de turbulence.

<div class="section chapter">
    <div>
		<img src="banners/curve.png" height=480 style="position: absolute;"/>
        <div>Ces derniers mois</div>
    </div>
</div>

Les pilotes utilisent des simulateurs de vol pour apprendre comment ne pas crasher des avions.

**Les épidémiologistes utilisent des simulateurs d'épidémie pour apprendre comment ne pas crasher l'humanité.**

Créons notre propre très, *très* simple "simulateur de vol épidémique" ! Dans cette simulation, les individus Infectieux <icon i></icon> peuvent transformer les individus Susceptibles de contracter la maladie <icon s></icon> en encore plus d'individus Infectieux <icon i></icon> :

![](pics/spread.png)

On estime *qu'au début* de l'épidémie de COVID-19, le virus allait d'un <icon i></icon> à un <icon s></icon> tous les 4 jours, *en moyenne*.[^serial_interval] (pour rappel, il y a beaucoup de variations)

[^serial_interval]: “The mean [serial] interval was 3.96 days (95% CI 3.53–4.39 days)”. [Du Z, Xu X, Wu Y, Wang L, Cowling BJ, Ancel Meyers L](https://wwwnc.cdc.gov/eid/article/26/6/20-0357_article) Traduction : "L'intervalle [sériel] moyen était de 3.96 jours (intervalle de confiance à 95% : 3.53–4.39 jours)". (Attention: les pré-publications ne sont pas considérées comme des versions finales)

Que se passe-t-il si nous simulons le cas "double tous les 4 jours", *et rien de plus*, sur une population qui commence avec seulement 0.001% de <icon i></icon> ? 

**Cliquez sur "Lancer" pour réaliser une simulation! Vous pouvez relancer avec d'autres paramètres quand la simulation est finie:** (limites techniques: [^caveats])

[^caveats]: **Attention: toutes ses simulations sont très simplificatrices, à des fins éducatives.**
    
    Une simplification: Quand la simulation est parametrée pour "Infecter 1 nouvelle personne tous les X jours", elle va en réalité augmenter le nombre d'infectés d'1/X chaque jour. De même pour les prochains paramètres dans ces simulations: "Guérir tous les X jours" est simulé en "réduit le nombre d'infectés d'1/X chaque jour".
    
    Ce n'est *pas* exactement la même chose, mais c'est assez proche de la réalité, et plus compréhensible que de paramétrer les taux de transmission/guérison directement.

<div class="sim">
		<iframe src="sim?stage=epi-1" width="800" height="540"></iframe>
</div>

Ceci est la *courbe de croissance exponentielle.** Ça commence petit, puis ça explose. De "Oh ce n'est juste qu'une grippe" à "Ah oui, les grippes n'engendrent pas de *fosses communes dans New-York*". 

![](pics/exponential.png)

Pour autant, cette simulation est fausse. La  croissance exponentielle, heureusement, ne peut pas durer. Si une partie de la population a *déjà*, le virus, cela empêche sa diffusion:

![](pics/susceptibles.png)

Plus il y a de <icon i></icon>, plus les <icon s></icon> deviennent des <icon i></icon> rapidement, **mais moins il y a de <icon s></icon>, *moins* les <icon s></icon>s deviennent des <icon i></icon> rapidement.**

En quoi cela change la croissance d'une épidémie ? Il n'y a qu'à le simuler:

<div class="sim">
		<iframe src="sim?stage=epi-2" width="800" height="540"></iframe>
</div>

Ceci est la **courbe de croissance logistique** "en S". Ça commence doucement, ça explose, puis ça ralenti à nouveau.

Pour autant, cette simulation est *encore* fausse. On passe à côté  du fait qu'un individu Infectieux <icon i></icon> fini par arrêter d'être infectieux, soit en étant: 1) guéri, 2) "guéri" avec des lésions pulmonaires  3) décédé.

Pour faire simple, supposons que tout les individus Infectieux <icon i></icon> deviennent guéris (**R**ecovered en anglais) <icon r></icon>. (Mais gardez en tête que la réalité est bien plus dure.) Les <icon r></icon> ne peuvent plus être infectés, et supposons – *pour l'instant!* – qu'ils sont immunisés à vie.

Pour le COVID-19, on estime qu'un individu est Infectieux <icon i></icon> pendant 10 jours, *en moyenne*.[^infectiousness] Certains guérissent en moins de 10 jours, d'autres en plus. **Voilà ce que ça donne, avec une simulation qui *commence* avec 100% de <icon i></icon>:**

[^infectiousness]: “The median communicable period \[...\] was 9.5 days.” [Hu, Z., Song, C., Xu, C. et al](https://link.springer.com/article/10.1007/s11427-020-1661-4) Traduction : "La période de contagiosité médiane \[...\] était de 9.5 jours.". Oui, nous savons qu'une "médiane" n'est pas la même chose qu'une "moyenne". C'est suffisamment proche pour notre explication simplifiée.

<div class="sim">
		<iframe src="sim?stage=epi-3" width="800" height="540"></iframe>
</div>

Ceci est l'inverse de la croissance exponentielle, c'est la **courbe de décroissance exponentielle.**

Maintenant, que se passe-t-il lorsqu'on simule la courbe de croissance logistique *avec* les guérisons ?

![](pics/graphs_q.png)

Voyons donc ça !

<b style='color:#ff4040'>La courbe Rouge</b> représente les cas <icon i></icon> *actuels* ,    
<b style='color:#999999'>La courbe Grise</b> représente le *total* de cas (actuels <icon i></icon> + guéris <icon r></icon>). 
En commencant avec seulement 0.001% de <icon i></icon>:

<div class="sim">
		<iframe src="sim?stage=epi-4" width="800" height="540"></iframe>
</div>

Et *c'est de là* que nous viens cette fameuse courbe! Ce n'est pas une courbe de Gauss, ni même une courbe "log-normale". Ça n'a pas de nom, mais vous l'avez vue des millions de fois et vous priez pour qu'elle s'aplatisse.

C'est le **Modèle SIR**, [^sir]    
(<icon s></icon>**S**usceptible <icon i></icon>**I**nfectieux <icon r></icon>**R**ecovered (guéri en anglais))      
la *deuxième* idée la plus importante de notre initiation à l'épidémiologie:

[^sir]: Pour plus d'explications techniques sur le modèle SIR, voir [the Institute for Disease Modeling](https://www.idmod.org/docs/hiv/model-sir.html#) et [Wikipedia](https://fr.wikipedia.org/wiki/Mod%C3%A8les_compartimentaux_en_%C3%A9pid%C3%A9miologie)

![](pics/sir.png)

**NB: Les simulations qui conseillent les décideurs politiques sont bien, *bien* plus sophistiquées que ça!** Néanmoins le modèle SIR suffit pour trouver un résultat global similaire, même si certaines nuances lui échappe.

Ajoutons donc une autre nuance: avant qu'un <icon s></icon> ne devienne un <icon i></icon>, il doit d'abord être Exposé <icon e></icon>. Cela correspond au moment où l'individu possède le virus mais ne peut pas encore le transmettre – infect**é** mais pas encore infect**ieux**.

![](pics/seir.png)

(Cette variante est appellée le **Modèle SEIR**[^seir], avec "E" pour "Exposé" <icon e></icon>. Notez que *ça ne correspond pas* au sens du mot "exposé" de tous les jours: quand il est possible d'avoir *ou non* le virus. La définition technique d'"Exposé" signifie que le virus est bel et bien porté. La terminologie en science est pleine d'absurdité.)

[^seir]: Pour plus d'explications techniques sur le modèle SEIR, voir [the Institute for Disease Modeling](https://www.idmod.org/docs/hiv/model-seir.html) et [Wikipedia](https://fr.wikipedia.org/wiki/Mod%C3%A8les_compartimentaux_en_%C3%A9pid%C3%A9miologie)

Pour le COVID-19, on estime qu'un individu est infecté-mais-pas-encore-infectieux <icon e></icon> pendant 3 jours, *en moyenne*.[^latent] Que se passe-t-il lorsqu'on ajoute cela à la simulation?

[^latent]: “Assuming an incubation period distribution of mean 5.2 days from a separate study of early COVID-19 cases, we inferred that infectiousness started from 2.3 days (95% CI, 0.8–3.0 days) before symptom onset” Traduction : "En supposant que la période d'incubation est en moyenne de 5.2 jours en s'appuyant sur une autre étude des premiers cas de COVID-19, nous en déduisons que la contagiosité commence au bout de 2.3 jours (intervalle de confiance à 95% : 0.8–3.0 jours) avant l'apparition des symptômes". (explication : En supposant que les symptômes commencent au 5ème jour, sachant que le caractère infectieux commence 2 jours avant, on devient infectieux au bout de 3 jours) [He, X., Lau, E.H.Y., Wu, P. et al.](https://www.nature.com/articles/s41591-020-0869-5)

<b style='color:#ff4040'>La courbe Rouge <b style='color:#FF9393'>+ Rose</b></b> représente les cas *actuels* (infectieux <icon i></icon> + exposés <icon e></icon>),    
<b style='color:#888'>La courbe Grise</b> représente le *total* de cas (actuels <icon i></icon> <icon e></icon> + guéris <icon r></icon>):

<div class="sim">
		<iframe src="sim?stage=epi-5" width="800" height="540"></iframe>
</div>

Pas beaucoup de changement! Le temps que l'on passe en Exposé <icon e></icon> change le ratio de <icon e></icon>-pour-<icon i></icon>, et la *date* du pic de cas... mais la *hauteur* du pic, et le nombre total de cas à la fin restent les mêmes.

Mais pourquoi ? A cause du *premier* concepte clé de l'épidémiologie:

![](pics/r.png)

La version courte du "Nombre de reproduction". Il s'agit du nombre *moyen* de personnes qu'un <icon i></icon> infecte *avant* qu'il ne guérisse (ou décède).

![](pics/r2.png)

**R** évolue au cours d'une vague, au fur et à mesure que l'immunité et les mesures d'intervention se développent.

**R<sub>0</sub>** est la valeur de R *au début de la vague, avant l'immunité et les mesures d'intervention*. R<sub>0</sub> reflète la force du virus-même, mais il varie quand même d'un endroit à l'autre. Par exemple, R<sub>0</sub> est plus grand dans les villes denses qu'en campagne plus espacée.

(La plupart des articles d'actualité - et même des publications scientifiques ! - confondent R et R<sub>0</sub>. Encore une fois, la terminologie scientifique est pleine d'absurdité)

Le R<sub>0</sub> pour "la" grippe saisonnière tourne autour de 1.28[^r0_flu]. Cela signifie qu'au *début* d'une vague de grippe, chaque <icon i></icon> infecte 1.28 personnes *en moyenne.* (Si ça paraît étrange de ne pas avoir un nombre entier, souvenez-vous que la maman *moyenne* a 2.4 enfants. Cela ne veut pas dire qu'il y a des demi-enfants se gambadant un peu partout.)

[^r0_flu]: “The median R value for seasonal influenza was 1.28 (IQR: 1.19–1.37)” [Biggerstaff, M., Cauchemez, S., Reed, C. et al.](https://bmcinfectdis.biomedcentral.com/articles/10.1186/1471-2334-14-480) Traduction: “La valeur médiane de R pour l'influenza saisonnière était de 1.28 (IC: 1.19-1.37)"

Le R<sub>0</sub> pour le COVID-19 est estimé à environ 2.2[^r0_covid], bien qu'une étude *pas encore finalisée* estime qu'il était de 5.7(!) à Wuhan.[^r0_wuhan]

[^r0_covid]: “We estimated the basic reproduction number R0 of 2019-nCoV to be around 2.2 (90% high density interval: 1.4–3.8)” [Riou J, Althaus CL.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7001239/) Traduction: "Nous avons estimé le nombre de reproduction de base R0 de 2019-nCoV à environ 2.2 (intervalle de confiance à 90%: 1.4-3.8)"

[^r0_wuhan]: “we calculated a median R0 value of 5.7 (95% CI 3.8–8.9)” [Sanche S, Lin YT, Xu C, Romero-Severson E, Hengartner N, Ke R.](https://wwwnc.cdc.gov/eid/article/26/7/20-0282_article) Traduction: "Nous avons calculé une valeur médiane de R0 de 5.7 (IC 95% : 3.8-8.9)"

Dans nos simulations - *au début et en moyenne* - un <icon i></icon> infecte quelqu'un tous les 4 jours et ce pendant 10 jours. Il y 2,5 fois "4 jours" dans "10 jours". Cela signifie -*au début et en moyenne* - que chaque <icon i></icon> infecte 2.5 Susceptibles <icon s></icon> . Par conséquent, R<sub>0</sub> = 2,5.(limitations techniques:[^r0_caveats_sim])

[^r0_caveats_sim]: Cela suppose qu'on est infectieux de manière constante tout au long de la "période infectieuse". Encore une fois, c'est une simplification pour aider à la compréhension.

**Jouez avec ce calculateur de R<sub>0</sub> pour voir comment R<sub>0</sub> dépend du temps de guérison et de la fréquence de nouvelle infection:**

<div class="sim">
		<iframe src="sim?stage=epi-6a&format=calc" width="285" height="255"></iframe>
</div>

Mais souvenez-vous, moins il y a de <icon s></icon>, plus les <icon s></icon> deviennent <icon i></icon> *lentement*. Le nombre de reproduction *actuel* (R) dépend non-seulement du nombre de reproduction *de base* (R<sub>0</sub>), mais *aussi* de combien de personnes ne sont plus Susceptibles  <icon s></icon>. (Par exemple, en guérissant et en devenant naturellement immunisées.)

<div class="sim">
		<iframe src="sim?stage=epi-6b&format=calc" width="285" height="390"></iframe>
</div>

Lorsque suffisament de gens sont immunisés, R < 1 et le virus est contenu ! On appelle ça **l'immunité collective**. Pour la grippe, l'immunité collective est obtenue *par la vaccination*. Essayer d'obtenir "l'immunité collective naturelle" en laissant les gens être infectés est une *très mauvaise* idée. (Mais pas pour la raison que vous avez peut-être en tête ! Nous l'expliquerons plus tard.)

Maintenant, lançons le modèle SEIR encore une fois, mais en montrant R<sub>0</sub>, l'évolution de R dans le temps et le seuil de l'immunité collective:

<div class="sim">
		<iframe src="sim?stage=epi-7" width="800" height="540"></iframe>
</div>

**Attention: le total des cas ne *s'arrête pas* au seuil de l'immunité collective, mais le dépasse !** Et il passe le seuil *exactement* au moment où le nombre actuel de cas est au maximum. (C'est ainsi quels que soient les réglages - essayez vous-même !)

Cela est dû au fait que lorsqu'il y a plus de non-<icon s></icon> que le seuil d'immunité collective, on obtient R < 1. Et lorsque R < 1, le nombre de nouveaux cas cesse d'augmenter: c'est un pic.

**Si vous ne deviez retenir qu'une seule chose de ce guide, ce serait ceci** - c'est un graphique très complexe, alors prenez le temps de l'assimiler complètement:

![](pics/r3.png)

**Cela signifie qu'il n'y a PAS besoin d'infecter tout le monde, ou même presque tout le monde, pour stopper le COVID-19 !**

C'est paradoxal. Le COVID-19 est extrêmement contagieux et pourtant, pour le contenir, il faut "seulement" éviter plus de 60% des infections. 60% ?! Si c'était une note d'école, ce serait un 12/20. Mais si R<sub>0</sub> = 2.5, alors le réduire de 61% nous donne R = 0.975, ce qui est R < 1, donc le virus est contenu ! (formule exacte:[^exact_formula])

[^exact_formula]: Gardez en tête que R = R<sub>0</sub> * le taux des transmissions encore possibles. Souvenez-vous aussi que le taux des transmissions possibles = 1 - le taux des transmissions *empêchées*.

  Donc, pour obtenir R < 1, on a besoin d'avoir R<sub>0</sub> * TransmissionsPermises < 1.

  Donc, TransmissionsPermises < 1/R<sub>0</sub>

  Donc, 1 - TransmissionsEmpêchées < 1/R<sub>0</sub>

  Donc, TransmissionsEmpêchées > 1 - 1/R<sub>0</sub>

  Par conséquent, il faut empêcher plus de **1 - 1/R<sub>0</sub>** des transmissions pour obtenir R < 1 et contenir le virus !

![](pics/r4.png)

(Si vous pensez que R<sub>0</sub> ou d'autres paramètres dans vos simulations sont trop haut/bas, c'est bien, vous défiez nos hypothèses ! Il y aura un mode "bac à sable" à la fin de ce guide, où vous pourrez entrer vos *propres* paramètres et voir ce que ça donne.)

*Toutes* les mesures contre le COVID-19 dont vous avez entendu parler - lavage des mains, distance sociale, confinements, auto-isolation, suivi des contacts et mise en quarantaine, port du masque et même "immunité collective" - elles ont toutes le même but:

Obtenir R < 1.

Maintenant, utilisons notre "simulateur de vol épidémiologique" pour répondre à la question suivante: Comment peut-on obtenir R < 1 *tout en protégeant notre santé mentale et financière ?**

Préparez-vous à un atterrissage d'urgence...

<div class="section chapter">
    <div>
		<img src="banners/curve.png" height=480 style="position: absolute;"/>
        <div>The Next Few Months</div>
    </div>
</div>

... ça aurait pu être pire. Voici un univers parallèle que l'on a évité:

###Scenario 0: On ne fait absolument rien

Environ une personne atteinte du COVID-19 sur vingt a besoin de soins intensifs.[^icu_covid] Dans un pays développé comme les États-Unis, il y a une place en soins intensifs par 2400 personnes.[^icu_us] Par conséquent, sur 3400 personnes atteintes *en même temps*, les États-Unis peuvent en gérer 20 - soit 0,6% de la population.

[^icu_covid]: ["Percentage of COVID-19 cases in the United States from February 12 to March 16, 2020 that required intensive care unit (ICU) admission, by age group"](https://www.statista.com/statistics/1105420/covid-icu-admission-rates-us-by-age-group/).Traduction: "Pourcentage de cas de COVID-19 aux États-Unis du 12 février au 26 mars 2020 nécéssitant une admission en unité de soins intesifs, par groupe d'âge". Entre 4,9% et 11,5% de *tous* les cas de COVID-19 ont eu besoin de soins intensifs. En choisissant généreusement l'estimation basse, cela nous fait 5%, soit 1 sur 20. Notez que cette proportion est propre à la pyramide des âges de ce pays. Elle sera plus haute dans les pays avec une population âgée et plus basse dans les pays avec une population jeune.

[^icu_us]: “Number of ICU beds = 96,596”. De [the Society of Critical Care Medicine](https://sccm.org/Blog/March-2020/United-States-Resource-Availability-for-COVID-19) Tradution: "Nombre de lits en unité de soins intensifs = 96'596" La population des États-Unis était de 328'200'000 en 2019. 96'596 sur 328'200'000 environ 1 sur 3400.

Même si on faisait *plus que tripler* cette capacité pour atteindre 2%, voici ce qui se serait passé *si on n'avait absolument rien fait:*

<div class="sim">
		<iframe src="sim?stage=int-1&format=lines" width="800" height="540"></iframe>
</div>

Pas bon.

C'est ce que [Le rapport du 16 mars de l'Imperial College de Londres](http://www.imperial.ac.uk/mrc-global-infectious-disease-analysis/covid-19/report-9-impact-of-npis-on-covid-19/) a trouvé: si on ne fait rien, on sature les soins intensifs, avec plus de 80% de la population contaminée.
(Souvenez-vous: le nombre total de cas *dépasse* le seuil d'immunité collective)

Même si seulement 0,5% des personnes infectées meurent - une hypothèse optimiste lorsqu'il n'y a plus de place en soins intensifs - dans un grand pays comme les États-Unis avec 300 millions d'habitants, 0,5% de 80% de 300 millions = tout de même 1,2 millions de décès... *SI on ne fait rien.*)

(Beaucoup de médias et de réseaux sociaux annonçaient que "80% des gens vont être infectés" *sans* préciser "SI on ne fait rien". La peur a été transformée en clics, pas en compréhension. *Soupir.*)

###Scenario 1: Aplatir la courbe / Immunité collective

La stratégie "Aplatir la courbe" a été promue par tous les organismes de santé publique, pendant que le plan de base "d'immunité collective" du Royaume Uni était universellement décrié. Ces deux plans étaient *les mêmes*. Le Royaume Uni a juste mal communiqué le sien.[^yong]

[^yong]: “He says that the actual goal is the same as that of other countries: flatten the curve by staggering the onset of infections. As a consequence, the nation may achieve herd immunity; it’s a side effect, not an aim. [...] The government’s actual coronavirus action plan, available online, doesn’t mention herd immunity at all.”

    Tiré de [The Atlantic article by Ed Yong](https://www.theatlantic.com/health/archive/2020/03/coronavirus-pandemic-herd-immunity-uk-boris-johnson/608065/) Traduction: "Il dit que l'objectif est en fait le même que les autres pays: aplatir la courbe en étalant le départ des infections. Par conséquent, le pays pourrait atteindre l'immunité collective; c'est un effet secondaire, pas un but en soi. [...] En fait, le plan d'action du gouvernement contre le coronavirus, disponible en ligne, ne mentionne pas du tout l'immunité collective."

Cependant, les deux plans avaient des failles littéralement fatales.

Premièrement, voyons les deux principales manières "d'aplatir la courbe": le lavage des mains et la distanciation sociale.

Intensifier le lavage des mains réduit les grippes et les rhumes, dans les pays riches, d'environ 25%[^handwashing], tandis que le confinement généralisé a réduit les contacts rapprochés d'environ 70%[^london]. Supposons alors que le lavage des mains peut réduire R *jusqu'à* 25% et que la distanciation sociale peut réduire R *jusqu'à* 70%:

[^handwashing]: “All eight eligible studies reported that handwashing lowered risks of respiratory infection, with risk reductions ranging from 6% to 44% [pooled value 24% (95% CI 6–40%)].”  [Rabie, T. and Curtis, V.](https://onlinelibrary.wiley.com/doi/full/10.1111/j.1365-3156.2006.01568.x) Traduction: "Toutes les huit études valables ont rapporté que le lavage des mains réduisait le risque d'infections respiratoires, avec une réduction des risque allant de 6% à 44% [valeur moyenne 24% (IC 95% : 6-40%)]." Note: Par simplicité, la valeur a été arrondie à 25% dans les simulations. On notera que, comme le pointe cette méta-analyse, la qualité des études sur le lavage des main (du moins dans les pays riches) est médiocre.

[^london]: “We found a 73% reduction in the average daily number of contacts observed per participant. This would be sufficient to reduce R0 from a value from 2.6 before the lockdown to 0.62 (0.37 - 0.89) during the lockdown”.  [Jarvis and Zandvoort et al](https://cmmid.github.io/topics/covid19/comix-impact-of-physical-distance-measures-on-transmission-in-the-UK.html) Traduction: "Nous avons trouvé une réduction de 73% du nombre de contacts journaliers moyen observés par participant. Cela serait suffisant pour réduire R0 de 2,6 avant le confinement à 0,62 (IC 0,37 - 0.89) pendant le confinement". Pour faire simple, le taux a été arrondi à 70% dans les simulations.

**Jouez avec ce simulateur pour voir comment le pourcentage de non-<icon s></icon>, le lavage des mains et la distanciation sociale réduisent R:** (ce calculateur visualise leurs effets *relatifs*, ce qui explique pourquoi lorsqu'un l'un d'eux est augmenté, les autres semblent diminuer.[^log_caveat])

[^log_caveat]: Cette distortion disparaîtrait si R était représenté dans une échelle logarithmique... Mais dans ce cas il faudrait aussi expliquer le concept d'*échelle logarithmique.*

<div class="sim">
		<iframe src="sim?stage=int-2a&format=calc" width="285" height="260"></iframe>
</div>

Maintenant, simulons ce qu'il arrive à une épidémie de COVID-19 si, début mars, nous avions augmenté le lavage des mains mais seulement avec une distanciation sociale *légère* - de telle sorte que R est plus bas, mais toujours au dessus de 1:

<div class="sim">
   <iframe src="sim?stage=int-2&format=lines" width="800" height="540"></iframe>
</div>

Trois observations:

1. Cela *réduit* le nombre total de cas ! **Même si on n'arrive pas à R < 1, réduire R sauve quand même des vies en réduisant le dépassement au dessus du seuil d'immunité collective.** Beaucoup de gens s'imaginent "qu'aplatir la courbe" étale les cas sans toutefois réduire leur nombre total. C'est impossible dans *n'importe lequel* des modèles de base de l'épidémiologie. Mais parce que les médias d'actualité présentaient l'affirmation "80% seront infectés" comme inévitable, les gens ont pensé que le nombre total de cas serait le même quoi qu'on fasse. *Soupir.*

2. A cause des mesures supplémentaires, le nombre de cas actuels atteint un pic *avant* que l'immunité collective ne soit atteinte. En fait, dans cette simulation, le nombre total de cas passe *un tout petit peu* au dessus du seuil d'immunité collective - le plan du Royaume Uni ! A ce moment, R < 1, on peut abandonner toutes les autres mesures d'intervention et le COVID-19 reste contenu ! Eh bien, il y a quand même un problème...

3. On sature les unités de soins intensifs. Pour plusieurs mois. (et souvenez-vous, on a pourtant *déjà* triplé la capacité pour ces simulations)

C'était l'autre conclusion du rapport du 16 mars de l'Imperial College de Londres, qui a convaincu le Royaume Uni d'abandonner sa stratégie initiale. Toute tentative d'**atténuation** (réduire R, mais R > 1) échouera. Le seul échappatoire est l'**endiguement** (réduire R afin d'atteindre R < 1).

![](pics/mitigation_vs_suppression.png)

Il ne faut donc pas simplement "aplatir" la courbe, il faut la *faire s'écrouler*. Par exemple, par le biais d'un...

###Scenario 2: Confinement de plusieurs moins

Voyons ce qu'il arrive lorsqu'on *fait s'écrouler* la courbe avec un confinement de 5 mois, qu'on réduit <icon i></icon> à presque rien, et que finalement, - *finalement* - on retrouve une vie normale:

<div class="sim">
		<iframe src="sim?stage=int-3&format=lines" width="800" height="540"></iframe>
</div>

Oh.

Voici la "seconde vague" dont tout le monde parle. Aussitôt le confinement levé, on repasse à R > 1. Un seul <icon i></icon> restant (ou un <icon i></icon> importé) peut provoquer un sursaut presque aussi méchant que si nous avions suivi le Scénario 0: "On ne fait absolument rien".

**Un confinement n'est pas un remède, c'est juste un retour à la case départ.**

Alors quoi, on se confine encore et toujours ?

###Scenario 3: Confinement intermittent

Cette solution a été suggérée en premier par le rapport du 16 mars de l'Imperial College de Londres et plus tard par un article de Harvard.[^lockdown_harvard]

[^lockdown_harvard]: “Absent other interventions, a key metric for the success of social distancing is whether critical care capacities are exceeded. To avoid this, prolonged or intermittent social distancing may be necessary into 2022.” [Kissler and Tedijanto et al](https://science.sciencemag.org/content/early/2020/04/14/science.abb5793) Traduction: Sans autres interventions, un indicateur clé du succès de la distanciation sociale est si oui ou non les soins intensifs sont saturés. Pour éviter cela, une distanciation sociale prolongée ou intermittente pourrait être nécessaire jusqu'en 2022."

**Voici une simulation:** (Après avoir lancé le scénario "pré-enregistré", vous pourrez essayer de simuler votre *propre* plan confinement, en déplaçant les curseurs *pendant* que la simulation tourne ! Gardez en tête que vous pouvez mettre en pause et reprendre la simulation, ainsi que changer la vitesse de la simulation)

<div class="sim">
		<iframe src="sim?stage=int-4&format=lines" width="800" height="540"></iframe>
</div>

Cela *pourrait* maintenir le nombre de cas en dessous de la capacité des soins intensifs! Et c'est *beaucoup* mieux qu'un confinement de 18 mois en attendant qu'un vaccin soit disponible. Il faut juste... tout fermer pendant quelques mois, rouvrir pendant quelques mois et répéter jusqu'à ce qu'un vaccin arrive. (Et s'il n'y a pas de vaccin, répéter jusqu'à ce que l'immunité collective soit atteinte... en 2022.)

Enfin bon, c'est bien joli de dessiner une ligne disant "capacité des soins intensifs", mais il a beaucoup de choses importantes qu'on *ne peut pas* simuler ici. Comme:

**La santé mentale:** La solitude est un des plus importants facteurs de risque menant à la dépression, à l'anxiété et au suicide. C'est tout aussi associé à une mort prématurée que ne l'est le fait de fumer 15 cigarettes par jour.[^loneliness]

[^loneliness]: Voir la [Figure 6 de Holt-Lunstad & Smith 2010](https://journals.sagepub.com/doi/abs/10.1177/1745691614568352). Bien sûr, grosse mise en garde: ils ont trouvé une *correlation*. Mais à moins que vous ne vouliez imposer aléatoirement à des gens d'être solitaires pour toute leur vie, des indices observationnels sont tout ce que vous pourrez avoir.

**Santé financière:** "Et l'économie alors" sonne comme si vous vous préoccupiez plus de dollars que de vies à sauver, mais "l'économie" n'est pas seulement des actions en bourse : c'est la capacité des personnes à fournir un toit et de la nourriture à leurs proches, à investir dans le futur de leurs enfants, à apprécier de l'art, de la bonne nourriture, des jeux vidéos - les trucs qui font que la vie vaut la peine d'être vécue. Par ailleurs, la pauvreté *elle-même* a un impact désastreux sur la santé mentale et physique.

Nous ne disons pas qu'on ne *devrait pas* se confiner à nouveau ! Nous verrons les confinements "disjoncteurs" plus tard. Toujours est-il que ce n'est pas idéal.

Mais attendez... Taïwan et la Corée du Sud n'ont-elles pas *déjà* contenu le COVID-19 ? Pendant 4 mois, *sans* long confinement ?

Comment ?

###Scenario 4: Test, Trace, Isolate

*"Sure, we \*could've\* done what Taiwan & South Korea did at the start, but it's too late now. We missed the start."*

But that's exactly it! “A lockdown isn't a cure, it's just a restart”... **and a fresh start is what we need.**

To understand how Taiwan & South Korea contained COVID-19, we need to understand the exact timeline of a typical COVID-19 infection[^timeline]:

[^timeline]: **3 days on average to infectiousness:** “Assuming an incubation period distribution of mean 5.2 days from a separate study of early COVID-19 cases, we inferred that infectiousness started from 2.3 days (95% CI, 0.8–3.0 days) before symptom onset” (translation: Assuming symptoms start at 5 days, infectiousness starts 2 days before = Infectiousness starts at 3 days) [He, X., Lau, E.H.Y., Wu, P. et al.](https://www.nature.com/articles/s41591-020-0869-5)  
    
    **4 days on average to infecting someone else:** “The mean [serial] interval was 3.96 days (95% CI 3.53–4.39 days)” [Du Z, Xu X, Wu Y, Wang L, Cowling BJ, Ancel Meyers L](https://wwwnc.cdc.gov/eid/article/26/6/20-0357_article)
    
    **5 days on average to feeling symptoms:** “The median incubation period was estimated to be 5.1 days (95% CI, 4.5 to 5.8 days)” [Lauer SA, Grantz KH, Bi Q, et al](https://annals.org/AIM/FULLARTICLE/2762808/INCUBATION-PERIOD-CORONAVIRUS-DISEASE-2019-COVID-19-FROM-PUBLICLY-REPORTED)

![](pics/timeline1.png)

If cases only self-isolate when they know they're sick (that is, they feel symptoms), the virus can still spread:

![](pics/timeline2.png)

And in fact, 44% of all transmissions are like this: *pre*-symptomatic! [^pre_symp]

[^pre_symp]: “We estimated that 44% (95% confidence interval, 25–69%) of secondary cases were infected during the index cases’ presymptomatic stage” [He, X., Lau, E.H.Y., Wu, P. et al](https://www.nature.com/articles/s41591-020-0869-5)

But, if we find *and quarantine* a symptomatic case's recent close contacts... we stop the spread, by staying one step ahead!

![](pics/timeline3.png)

This is called **contact tracing**. It's an old idea, was used at an unprecedented scale to contain Ebola[^ebola], and now it's core part of how Taiwan & South Korea are containing COVID-19!

[^ebola]: “Contact tracing was a critical intervention in Liberia and represented one of the largest contact tracing efforts during an epidemic in history.” [Swanson KC, Altare C, Wesseh CS, et al.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6152989/)

(It also lets us use our limited tests more efficiently, to find pre-symptomatic <icon i></icon>s without needing to test almost everyone.)

Traditionally, contacts are found with in-person interviews, but those *alone* are too slow for COVID-19's ~48 hour window. That's why contact tracers need help, and be supported by – *NOT* replaced by – contact tracing apps.

(This idea didn't come from "techies": using an app to fight COVID-19 was first proposed by [a team of Oxford epidemiologists](https://science.sciencemag.org/content/early/2020/04/09/science.abb6936).)

Wait, apps that trace who you've been in contact with?... Does that mean giving up privacy, giving in to Big Brother?

Heck no! **[DP-3T](https://github.com/DP-3T/documents#decentralized-privacy-preserving-proximity-tracing)**, a team of epidemiologists & cryptographers (including one of us, Marcel Salathé) is *already* making a contact tracing app – with code available to the public – that reveals **no info about your identity, location, who your contacts are, or even *how many contacts* you've had.**

Here's how it works:

![](pics/dp3t.png)

(& [here's the full comic](https://ncase.me/contact-tracing/))

Along with similar teams like TCN Protocol[^tcn] and MIT PACT[^pact], they've inspired Apple & Google to bake privacy-first contact tracing directly into Android/iOS.[^gapple] (Don't trust Google/Apple? Good! The beauty of this system is it doesn't *need* trust!) Soon, your local public health agency may ask you to download an app. If it's privacy-first with publicly-available code, please do!

[^tcn]: [Temporary Contact Numbers, a decentralized, privacy-first contact tracing protocol](https://github.com/TCNCoalition/TCN#tcn-protocol)

[^pact]: [PACT: Private Automated Contact Tracing](https://pact.mit.edu/)

[^gapple]: [Apple and Google partner on COVID-19 contact tracing technology ](https://www.apple.com/ca/newsroom/2020/04/apple-and-google-partner-on-covid-19-contact-tracing-technology/). Note they're not making the apps *themselves*, just creating the systems that will *support* those apps.

But what about folks without smartphones? Or infections through doorknobs? Or "true" asymptomatic cases? Contact tracing apps can't catch all transmissions... *and that's okay!* We don't need to catch *all* transmissions, just 60%+ to get R < 1.

(Rant about the confusion about pre-symptomatic vs "true" asymptomatic. "True" asymptomatics are rare:[^rant])

[^rant]: Lots of news reports – and honestly, many research papers – did not distinguish between "cases who showed no symptoms when we tested them" (pre-symptomatic) and "cases who showed no symptoms *ever*" (true asymptomatic). The only way you could tell the difference is by following up with cases later.
   
    Which is what [this study](https://wwwnc.cdc.gov/eid/article/26/8/20-1274_article) did. (Disclaimer: "Early release articles are not considered as final versions.") In a call center in South Korea that had a COVID-19 outbreak, "only 4 (1.9%) remained asymptomatic within 14 days of quarantine, and none of their household contacts acquired secondary infections."
    
    So that means "true asymptomatics" are rare, and catching the disease from a true asymptomatic may be even rarer!

Isolating *symptomatic* cases would reduce R by up to 40%, and quarantining their *pre/a-symptomatic* contacts would reduce R by up to 50%[^oxford]:

[^oxford]: From the same Oxford study that first recommended apps to fight COVID-19: [Luca Ferretti & Chris Wymant et al](https://science.sciencemag.org/content/early/2020/04/09/science.abb6936/tab-figures-data) See Figure 2. Assuming R<sub>0</sub> = 2.0, they found that:    
    
    * Symptomatics contribute R = 0.8 (40%)
    * Pre-symptomatics contribute R = 0.9 (45%)
    * Asymptomatics contribute R = 0.1 (5%, though their model has uncertainty and it could be much lower)
    * Environmental stuff like doorknobs contribute R = 0.2 (10%)

    And add up the pre- & a-symptomatic contacts (45% + 5%) and you get 50% of R!

<div class="sim">
		<iframe src="sim?stage=int-4a&format=calc" width="285" height="340"></iframe>
</div>

Thus, even without 100% contact quarantining, we can get R < 1 *without a lockdown!* Much better for our mental & financial health. (As for the cost to folks who have to self-isolate/quarantine, *governments should support them* – pay for the tests, job protection, subsidized paid leave, etc. Still way cheaper than intermittent lockdown.)

We then keep R < 1 until we have a vaccine, which turns susceptible <icon s></icon>s into immune <icon r></icon>s. Herd immunity, the *right* way:

<div class="sim">
		<iframe src="sim?stage=int-4b&format=calc" width="285" height="230"></iframe>
</div>

(Note: this calculator pretends the vaccines are 100% effective. Just remember that in reality, you'd have to compensate by vaccinating *more* than "herd immunity", to *actually* get herd immunity)

Okay, enough talk. Here's a simulation of:

1. A few-month lockdown, until we can...
2. Switch to "Test, Trace, Isolate" until we can...
3. Vaccinate enough people, which means...
4. We win.

<div class="sim">
		<iframe src="sim?stage=int-5&format=lines" width="800" height="540"></iframe>
</div>

So that's it! That's how we make an emergency landing on this plane.

That's how we beat COVID-19.

...

But what if things *still* go wrong? Things have gone horribly wrong already. That's fear, and that's good! Fear gives us energy to create *backup plans*.

The pessimist invents the parachute.

###Scenario 4+: Masks For All, Summer, Circuit Breakers

What if R<sub>0</sub> is way higher than we thought, and the above interventions, even with mild distancing, *still* aren't enough to get R < 1?

Remember, even if we can't get R < 1, reducing R still reduces the "overshoot" in total cases, thus saving lives. But still, R < 1 is the ideal, so here's a few other ways to reduce R:

**Masks For All:**

*"Wait,"* you might ask, *"I thought face masks don't stop you from getting sick?"*

You're right. Masks don't stop you from getting sick[^incoming]... they stop you from getting *others* sick.

[^incoming]: “None of these surgical masks exhibited adequate filter performance and facial fit characteristics to be considered respiratory protection devices.” [Tara Oberg & Lisa M. Brosseau](https://www.sciencedirect.com/science/article/pii/S0196655307007742)

[^outgoing]: “The overall 3.4 fold reduction [70% reduction] in aerosol copy numbers we observed combined with a nearly complete elimination of large droplet spray demonstrated by Johnson et al. suggests that surgical masks worn by infected persons could have a clinically significant impact on transmission.” [Milton DK, Fabian MP, Cowling BJ, Grantham ML, McDevitt JJ](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3591312/)

[^homemade]: [Davies, A., Thompson, K., Giri, K., Kafatos, G., Walker, J., & Bennett, A](https://www.cambridge.org/core/journals/disaster-medicine-and-public-health-preparedness/article/testing-the-efficacy-of-homemade-masks-would-they-protect-in-an-influenza-pandemic/0921A05A69A9419C862FA2F35F819D55) See Table 1: a 100% cotton T-shirt has around 2/3 the filtration efficiency as a surgical mask, for the two bacterial aerosols they tested.

![](pics/masks.png)

To put a number on it: surgical masks *on the sick person* reduce cold & flu viruses in aerosols by 70%.[^outgoing] Reducing transmissions by 70% would be as large an impact as a lockdown!

However, we don't know for sure the impact of masks on COVID-19 *specifically*. In science, one should only publish a finding if you're 95% sure of it. (...should.[^replication]) Masks, as of May 1st 2020, are less than "95% sure".

[^replication]: Any actual scientist who read that last sentence is probably laugh-crying right now. See: [p-hacking](https://en.wikipedia.org/wiki/Data_dredging), [the replication crisis](https://en.wikipedia.org/wiki/Replication_crisis))

However, pandemics are like poker. **Make bets only when you're 95% sure, and you'll lose everything at stake.** As a recent article on masks in the British Medical Journal notes,[^precautionary] we *have* to make cost/benefit analyses under uncertainty. Like so:

[^precautionary]: “It is time to apply the precautionary principle” [Trisha Greenhalgh et al \[PDF\]](https://www.bmj.com/content/bmj/369/bmj.m1435.full.pdf)

Cost: If homemade cloth masks, same as the cost of all that soap for handwashing. If surgical masks, more expensive but still pretty cheap.

Benefit: Even if it's a 50–50 chance of surgical masks reducing transmission by 0% or 70%, the average "expected value" is still 35%, same as a half-lockdown! So let's guess-timate that surgical masks reduce R by up to 35%. (Again, you can challenge our assumptions by turning the sliders up/down)

**Here's a calculator of how masks reduce R! You can switch between cloth & surgical:** (assumes cloth masks are 2/3 as effective as surgical masks[^homemade])

<div class="sim">
		<iframe src="sim?stage=int-6a&format=calc" width="285" height="380"></iframe>
</div>

(other arguments for/against masks:[^mask_args])

[^mask_args]: **"We need to save supplies for hospitals."** *Absolutely agreed.* But that's more of an argument for increasing mask production, not rationing. In the meantime, we can make cloth masks.

   **"They're hard to wear correctly."** It's also hard to wash your hands according to the WHO Guidelines – seriously, "Step 3) right palm over left dorsum"?! – but we still recommend handwashing, because imperfect is still better than nothing.
   
   **"It'll make people more reckless with handwashing & social distancing."** Sure, and safety belts make people ignore stop signs, and flossing makes people eat rocks. But seriously, we'd argue the opposite: masks are a *constant physical reminder* to be careful – and in East Asia, masks are also a symbol of solidarity!
    
    

Masks *alone* won't get R < 1. But if handwashing & "Test, Trace, Isolate" only gets us to R = 1.10, having just 2/3 of people wear *cloth* masks would tip that over to R < 1, virus contained!

**Summer:**

Okay, this isn't an "intervention" we can control, but it will help! Some news outlets report that summer won't do anything to COVID-19. They're half right: summer won't get R < 1, but it *will* reduce R.

For COVID-19, every extra 1° Celsius (2.2° Fahrenheit) makes R drop by 1.2%.[^heat] The summer-winter difference in New York City is 15°C (60°F), so summer will make R drop by 18%.

[^heat]: “One-degree Celsius increase in temperature [...] lower[s] R by 0.0225” and “The average R-value of these 100 cities is 1.83”. 0.0225 ÷ 1.83 = ~1.2%. [Wang, Jingyuan and Tang, Ke and Feng, Kai and Lv, Weifeng](https://papers.ssrn.com/sol3/Papers.cfm?abstract_id=3551767)

<div class="sim">
		<iframe src="sim?stage=int-6b&format=calc" width="285" height="220"></iframe>
</div>

Summer alone won't make R < 1, but if we have limited resources, we can scale back some interventions in the summer – so we can scale them *higher* in the winter.

**A "Circuit Breaker" Lockdown:**

And if all that *still* isn't enough to get R < 1... we can do another lockdown.

But we wouldn't have to be 2-months-closed / 1-month-open over & over! Because R is reduced, we'd only need one or two more "circuit breaker" lockdowns before a vaccine is available. (Singapore had to do this recently, "despite" having controlled COVID-19 for 4 months. That's not failure: this *is* what success takes.)

Here's a simulation a "lazy case" scenario:

1. Lockdown, then
2. A moderate amount of hygiene + "Test, Trace, Isolate" + *cloth* "Masks For All", then...
3. One more "circuit breaker" lockdown before a vaccine's found.

<div class="sim">
		<iframe src="sim?stage=int-7&format=lines&height=620" width="800" height="620"></iframe>
</div>

Not to mention all the *other* interventions we could do, to further push R down:

* Travel restrictions/quarantines
* Temperature checks at malls & schools
* Deep-cleaning public spaces
* [Replacing hand-shaking with foot-bumping](https://twitter.com/V_actually/status/1233785527788285953)
* And all else human ingenuity shall bring

. . .

We hope these plans give you hope. 

**Even under a pessimistic scenario, it *is* possible to beat COVID-19, while protecting our mental and financial health.** Use the lockdown as a "reset button", keep R < 1 with case isolation + privacy-protecting contract tracing + at *least* cloth masks for all... and life can get back to a normal-ish!

Sure, you may have dried-out hands. But you'll get to invite a date out to a comics bookstore! You'll get to go out with friends to watch the latest Hollywood cash-grab. You'll get to people-watch at a library, taking joy in people going about the simple business of *being alive.*

Even under the worst-case scenario... life perseveres.

Alors maintenant, faisons des plans pour quelques scénarios catastrophes. Amérissage, attrapez votre gilet de sauvetage et suivez les lumières vers les sorties de secours:

<div class="section chapter">
    <div>
		<img src="banners/curve.png" height=480 style="position: absolute;"/>
        <div>Les années à venir</div>
    </div>
</div>

Vous attrapez le COVID-19 et en guérissez. Ou vous recevez un vaccin. Dans les deux cas, vous êtes maintenant immunisé·e...

...*mais pour combien de temps?*

* Le COVID-19 est étroitement lié au SARS, qui rend ses survivants immunisés pour deux ans.[^SARS immunity]
* Le coronavirus causant "le" rhume procure 8 mois d'immunité.[^cold immunity]
* On a rapporté des cas de guéris du COVID-19 qui ont été, plus tard, à nouveau testés positivement, mais ce n'est pas clair ces cas sont des faux positifs.[^unclear]
* Une étude *pas encore revue par les pairs* effectuée sur des singes suggère que l'immunité au coronavirus du COVID-19 durerait au moins 28 jours.[^monkeys]

Mais pour le COVID-19 *chez les humains*, au 1er mai 2020, "Pour combien de temps" est encore une grande inconnue.

[^SARS immunity]: “SARS-specific antibodies were maintained for an average of 2 years [...] Thus, SARS patients might be susceptible to reinfection ≥3 years after initial exposure.” [Wu LP, Wang NC, Chang YH, et al.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2851497/) Traduction: "Les anticorps spécifiques au SARS sont maintenus en moyenne 2 ans [...] En conséquence, les patients du SARS pourraient être susceptibles d'être réinfectés ≥3 ans après l'exposition initiale. "Malheureusement", on ne saura jamais combien de temps l'immunité au SARS dure réellement, puisqu'il a été éradiqué très rapidement.

[^cold immunity]: “We found no significant difference between the probability of testing positive at least once and the probability of a recurrence for the beta-coronaviruses HKU1 and OC43 at 34 weeks after enrollment/first infection.” [Marta Galanti & Jeffrey Shaman (PDF)](http://www.columbia.edu/~jls106/galanti_shaman_ms_supp.pdf) Traduction: "Nous n'avons trouvé aucune différence significative entre la probabilité d'être testé positif au moins une fois et la probabilité d'une récurrence du beta-corronavirus HKU1 et OC43 34 semaines après l'exposition/la première infection."

[^unclear]: “Once a person fights off a virus, viral particles tend to linger for some time. These cannot cause infections, but they can trigger a positive test.” [from STAT News by Andrew Joseph](https://www.statnews.com/2020/04/20/everything-we-know-about-coronavirus-immunity-and-antibodies-and-plenty-we-still-dont/) Traduction: "Une fois qu'une personne combat un virus, des particules virales tendent à subsister quelques temps. Cela ne peut causer une infection, mais cela peut provoquer un test positif."

[^monkeys]: De [Bao et al.](https://www.biorxiv.org/content/10.1101/2020.03.13.990226v1.abstract) *Attention: Cet article est une pré-publication et n'a pas (encore) été vérifiée par une relecture par les pairs.* Aussi, pour le souligner: ils ont seulement testé la ré-infection 28 jours plus tard.

Pour ces simulations, disons que c'est un an.
**Voici une simulation commençant avec 100% de <icon r></icon>**, décroissant exponentiellement vers les Susceptibles et non-immunisés, <icon s></icon> après un an en *moyenne*, avec des variations:


<div class="sim">
		<iframe src="sim?stage=yrs-1&format=lines&height=600" width="800" height="600"></iframe>
</div>

Le retour du déclin exponentiel !

Il s'agit du **Modèle SEIRS**. Le dernier "S" signifie Susceptible <icon s></icon>, encore une fois.

![](pics/seirs.png)

Maintenant, simulons une vague de COVID-19 sur 10 ans, sans intervention... *si l'immunité ne dure qu'un an:*

<div class="sim">
		<iframe src="sim?stage=yrs-2&format=lines&height=600" width="800" height="600"></iframe>
</div>

Dans les simulations précédentes, nous avions seulement *un* pic dépassant la capacité en respirateurs. Maintenant, nous en avons plusieurs, *et* les cas <icon i></icon> atteignent un équilibre *permanent* égale à la capacité en respirateurs. (Que nous avons triplé pour ces simulations, souvenez-vous)

R = 1, c'est une **endémie.**

Heureusement, comme l'été réduit R, la situation va s'améliorer:

<div class="sim">
		<iframe src="sim?stage=yrs-3&format=lines&height=640" width="800" height="640"></iframe>
</div>

Oh.

contre toute attente, l'été rend les pics plus sévères *et* plus réguliers ! C'est parce que l'été réduit les nouveaux <icon i></icon>, mais en même temps réduit aussi les nouveaux immunisés <icon r></icon>. Ce qui veut dire que l'immunité chute durant l'été, *causant* des pics prononcés et réguliers en hiver.

Heureusement, la solution à ce problème est simple - vacciner les gens chaque automne/hiver, à la manière de ce que l'on fait avec le vaccin de la grippe.

**(Après avoir lancé l'enregistrement, essayez de simuler vos propres campagnes de vaccination ! Souvenez-vous que vous pouvez mettre en pause et continuer la simulation n'importe quand)**

<div class="sim">
		<iframe src="sim?stage=yrs-4&format=lines" width="800" height="540"></iframe>
</div>

Mais voici venue la question qui fait peur:

Et s'il n'y a pas de vaccin avant *plusieurs années* ? Voire *jamais* ?

**Pour être clair: c'est improbable.** La plupart des épidémiologistes s'attendent à un vaccin d'ici un ou deux ans. Alors oui, il n'y a jamais eu de vaccin pour aucun des autres coronavirus dans le passé, mais c'est parce que le SARS a été rapidement éradiqué et que "le" rhume n'en valait pas la peine.

Mais quand même, des chercheurs des maladies infectieuses ont exprimé des inquiétudes: Et si on ne pouvait en fabriquer assez ?[^vax_enough] Et si il arrivait bâclé et qu'il n'était pas sûr ?[^vax_safe]

[^vax_enough]: “If a coronavirus vaccine arrives, can the world make enough?” [by Roxanne Khamsi, on Nature](https://www.nature.com/articles/d41586-020-01063-8) Traduction: "Si un vaccin de coronavirus arrive, le monde peut-il en produire assez ?"

[^vax_safe]: “Don’t rush to deploy COVID-19 vaccines and drugs without sufficient safety guarantees” [by Shibo Jiang, on Nature](https://www.nature.com/articles/d41586-020-00751-9) Traduction: "Ne bâclez pas le deployement de médicaments et de vaccins du COVID-19 sans garanties de sécurité suffisantes"

Même dans le scénario catastrophe "sans vaccin", nous avons 3 échappatoires. Du plus au moins terrible:

1) Intervenir temporairement ou modérément pour garantir R<1 dans le but d'atteindre "l'immunité collective naturelle". (Attention: cela va provoquer de nombreuses morts et séquelles pulmonaires. *Et* ça ne fonctionne pas si l'immunité ne dure pas.)

2) Intevenir de manière permanente pour maintenir R<1. Les suivis des contacts et le port du masque deviennent alors la nouvelle norme du monde post-COVID-19, tout comme les tests de MST et le port du préservatif sont devenus la nouvelle norme dans le monde post-VIH.

3) Intervenir pour maintenir R<1 jusqu'à que soient développés des traitements qui rendent le COVID-19 bien, bien moins probable de demander des soins critiques. (Ce qu'on devrait faire de *toute façon !*) Diviser le besoin de respirateur par 10 est équivalent à multiplier la capacité en respirateurs par 10:

**Voici une simulation *sans* immunité durable, *sans* vaccin et sans même aucune intervention - seule la capacité à survivre aux longs pics augmente lentement*:**

<div class="sim">
		<iframe src="sim?stage=yrs-5&format=lines" width="800" height="540"></iframe>
</div>

Même dans le *pire* des scénarios cauchemardesques... La vie continue.

. . .


Vous voudrez peut-être remettre en question nos hypothèses et essayer différents R<sub>0</sub> ou nombres. Ou même essayer de simuler vos *propres* combinaisons de plans d'intervention !

**Voici un mode (optionel) "bac à sable", où *tout* est disponible. (Fais défiler pour voir tous les contrôles.) Simule et joue autant que le coeur t'en dit:**

<div class="sim">
		<iframe src="sim?stage=SB&format=sb" width="800" height="540"></iframe>
</div>

Ce "simulateur de vol épidémiologique" nous a tant appris. Il nous a permis de répondre à des questions sur les derniers mois, sur ceux à venir et sur les prochaines années.

Finalement, retournons à la...

<div class="section chapter">
    <div>
		<img src="banners/curve.png" height=480 style="position: absolute;"/>
        <div>The Now</div>
    </div>
</div>

L'avion a coulé. Nous nous sommes précipités sur des canots de sauvetages. C'est le moment de trouver la terre ferme.[^dry_land]

[^dry_land]: La métaphore de la terre ferme [de Marc Lipsitch & Yonatan Grad, sur STAT News](https://www.statnews.com/2020/04/01/navigating-covid-19-pandemic/)

Des équipes d'épidémiologistes et de décideurs ([de gauche](https://www.americanprogress.org/issues/healthcare/news/2020/04/03/482613/national-state-plan-end-coronavirus-crisis/), [de droite](https://www.aei.org/research-products/report/national-coronavirus-response-a-road-map-to-reopening/ ), et [multi-partisanes](https://ethics.harvard.edu/covid-roadmap)) sont arrivées à un consensus sur la manière de battre le COVID-19, tout en protégeant nos vies *et* nos libertés.

Voilà grossièrement l'idée, avec quelques plans de rechange (moins consensuels):

![](pics/plan.png)

Qu'est ce que ça veut dire pour vous maintenant ?

**Pour tout le monde:** Respectez le confinement pour qu'on puisse sortir de la Phase I aussi vite que possible. Lavez-vous les mains. Fabriquez vos propres masques. Téléchargez une application de suivi des contacts *respectueuse de vos données personnelles* lorsqu'elles seront disponibles le mois prochain. Restez en forme, physiquement et mentalement ! Et écrivez à votre décideur local de bouger ses fesses et...

**Pour les décideurs:** Faites des lois qui supportent ceux qui doivent se mettre en auto-isolement/quarantaine. Engagez plus d'agents de suivi manuel des contacts, *supportés** par des applications de suivi des contacts qui respectent la vie privée. Dirigez plus de fonds vers les trucs qu'on devrait fabriquer, comme...

**Pour les fabriquants:** Fabriquez des tests. Fabriquez des respirateurs. Fabriquez de l'équipement de protection personnel pour les hôpitaux. Fabriquez des tests. Fabriquez des masques. Fabriquez des applications. Fabriquez des antiviraux, des prophylactiques et autres traitements qui ne sont pas vaccins. Fabriquez des vaccins. Fabriquez des tests. Fabriquez des tests. Fabriquez de l'espoir.

Ne minimisez pas la peur pour fabriquer de l'espoir. Notre peur devrait faire *équipe* avec notre espoir, comme les inventeurs de l'avions et du parachute. C'est en se préparant à des futurs épouvantables qu'on *crée* un futur plein d'espérance.

La seule chose à craindre est l'idée que la seule chose dont il faille avoir peur est la peur elle-même.
