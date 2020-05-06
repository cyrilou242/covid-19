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

Ce guide (publié le 1er Mai 2020. clique sur cette note!→[^timestamp]) est censé *et* vous donner de l'espoir, *et* vous faire peur. Pour vaincre le COVID-19 **en préservant aussi nos santés mentales et financières**, nous devons faire preuve d'optimisme pour élaborer des plans, et de pessimisme pour élaborer des plans B. Comme l'a dit un jour Gladys Bronwyn Stern, *“L'optimiste invente l'avion, le pessimiste invente le parachute.”*

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

Et *c'est de là* que nous viens cette fameuse courbe! Ce n'est pas une courbe de Gauss, ni même une courbe "log-normale". Ça n'a pas de nom, mais vous l'avez vue des millions de fois et vous priez pour qu'elle s'applatisse.

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

...could have been worse. Here's a parallel universe we avoided:

###Scenario 0: Do Absolutely Nothing

Around 1 in 20 people infected with COVID-19 need to go to an ICU (Intensive Care Unit).[^icu_covid] In a rich country like the USA, there's 1 ICU bed per 3400 people.[^icu_us] Therefore, the USA can handle 20 out of 3400 people being *simultaneously* infected – or, 0.6% of the population.

[^icu_covid]: ["Percentage of COVID-19 cases in the United States from February 12 to March 16, 2020 that required intensive care unit (ICU) admission, by age group"](https://www.statista.com/statistics/1105420/covid-icu-admission-rates-us-by-age-group/). Between 4.9% to 11.5% of *all* COVID-19 cases required ICU. Generously picking the lower range, that's 5% or 1 in 20. Note that this total is specific to the US's age structure, and will be higher in countries with older populations, lower in countries with younger populations.

[^icu_us]: “Number of ICU beds = 96,596”. From [the Society of Critical Care Medicine](https://sccm.org/Blog/March-2020/United-States-Resource-Availability-for-COVID-19) USA Population was 328,200,000 in 2019. 96,596 out of 328,200,000 = roughly 1 in 3400. 

Even if we *more than tripled* that capacity to 2%, here's what would've happened *if we did absolutely nothing:*

<div class="sim">
		<iframe src="sim?stage=int-1&format=lines" width="800" height="540"></iframe>
</div>

Not good.

That's what [the March 16 Imperial College report](http://www.imperial.ac.uk/mrc-global-infectious-disease-analysis/covid-19/report-9-impact-of-npis-on-covid-19/) found: do nothing, and we run out of ICUs, with more than 80% of the population getting infected. 
(remember: total cases *overshoots* herd immunity)

Even if only 0.5% of infected die – a generous assumption when there's no more ICUs – in a large country like the US, with 300 million people, 0.5% of 80% of 300 million = still 1.2 million dead... *IF we did nothing.*

(Lots of news & social media reported "80% will be infected" *without* "IF WE DO NOTHING". Fear was channelled into clicks, not understanding. *Sigh.*)

###Scenario 1: Flatten The Curve / Herd Immunity

The "Flatten The Curve" plan was touted by every public health organization, while the United Kingdom's original "herd immunity" plan was universally booed. They were *the same plan.* The UK just communicated theirs poorly.[^yong]

[^yong]: “He says that the actual goal is the same as that of other countries: flatten the curve by staggering the onset of infections. As a consequence, the nation may achieve herd immunity; it’s a side effect, not an aim. [...] The government’s actual coronavirus action plan, available online, doesn’t mention herd immunity at all.”
    
    From a [The Atlantic article by Ed Yong](https://www.theatlantic.com/health/archive/2020/03/coronavirus-pandemic-herd-immunity-uk-boris-johnson/608065/)

Both plans, though, had a literally fatal flaw.

First, let's look at the two main ways to "flatten the curve": handwashing & physical distancing.

Increased handwashing cuts flus & colds in high-income countries by ~25%[^handwashing], while the city-wide lockdown in London cut close contacts by ~70%[^london]. So, let's assume handwashing can reduce R by *up to* 25%, and distancing can reduce R by *up to* 70%:

[^handwashing]: “All eight eligible studies reported that handwashing lowered risks of respiratory infection, with risk reductions ranging from 6% to 44% [pooled value 24% (95% CI 6–40%)].” We rounded up the pooled value to 25% in these simulations for simplicity. [Rabie, T. and Curtis, V.](https://onlinelibrary.wiley.com/doi/full/10.1111/j.1365-3156.2006.01568.x) Note: as this meta-analysis points out, the quality of studies for handwashing (at least in high-income countries) are awful.

[^london]: “We found a 73% reduction in the average daily number of contacts observed per participant. This would be sufficient to reduce R0 from a value from 2.6 before the lockdown to 0.62 (0.37 - 0.89) during the lockdown”. We rounded it down to 70% in these simulations for simplicity. [Jarvis and Zandvoort et al](https://cmmid.github.io/topics/covid19/comix-impact-of-physical-distance-measures-on-transmission-in-the-UK.html)

**Play with this calculator to see how % of non-<icon s></icon>, handwashing, and distancing reduce R:** (this calculator visualizes their *relative* effects, which is why increasing one *looks* like it decreases the effect of the others.[^log_caveat])

[^log_caveat]: This distortion would go away if we plotted R on a logarithmic scale... but then we'd have to explain *logarithmic scales.*

<div class="sim">
		<iframe src="sim?stage=int-2a&format=calc" width="285" height="260"></iframe>
</div>

Now, let's simulate what happens to a COVID-19 epidemic if, starting March 2020, we had increased handwashing but only *mild* physical distancing – so that R is lower, but still above 1:

<div class="sim">
		<iframe src="sim?stage=int-2&format=lines" width="800" height="540"></iframe>
</div>

Three notes:

1. This *reduces* total cases! **Even if you don't get R < 1, reducing R still saves lives, by reducing the 'overshoot' above herd immunity.** Lots of folks think "Flatten The Curve" spreads out cases without reducing the total. This is impossible in *any* Epidemiology 101 model. But because the news reported "80%+ will be infected" as inevitable, folks thought total cases will be the same no matter what. *Sigh.*

2. Due to the extra interventions, current cases peak *before* herd immunity is reached. In fact, in this simulation, total cases only overshoots *a tiny bit* above herd immunity – the UK's plan! At that point, R < 1, you can let go of all other interventions, and COVID-19 stays contained! Well, except for one problem...

3. You still run out of ICUs. For several months. (and remember, we *already* tripled ICUs for these simulations)

That was the other finding of the March 16 Imperial College report, which convinced the UK to abandon its original plan. Any attempt at **mitigation** (reduce R, but R > 1) will fail. The only way out is **suppression** (reduce R so that R < 1).

![](pics/mitigation_vs_suppression.png)

That is, don't merely "flatten" the curve, *crush* the curve. For example, with a...

###Scenario 2: Months-Long Lockdown

Let's see what happens if we *crush* the curve with a 5-month lockdown, reduce <icon i></icon> to nearly nothing, then finally – *finally* – return to normal life:

<div class="sim">
		<iframe src="sim?stage=int-3&format=lines" width="800" height="540"></iframe>
</div>

Oh.

This is the "second wave" everyone's talking about. As soon as we remove the lockdown, we get R > 1 again. So, a single leftover <icon i></icon> (or imported <icon i></icon>) can cause a spike in cases that's almost as bad as if we'd done Scenario 0: Absolutely Nothing.

**A lockdown isn't a cure, it's just a restart.**

So, what, do we just lockdown again & again?

###Scenario 3: Intermittent Lockdown

This solution was first suggested by the March 16 Imperial College report, and later again by a Harvard paper.[^lockdown_harvard]

[^lockdown_harvard]: “Absent other interventions, a key metric for the success of social distancing is whether critical care capacities are exceeded. To avoid this, prolonged or intermittent social distancing may be necessary into 2022.” [Kissler and Tedijanto et al](https://science.sciencemag.org/content/early/2020/04/14/science.abb5793)

**Here's a simulation:** (After playing the "recorded scenario", you can try simulating your *own* lockdown schedule, by changing the sliders *while* the simulation is running! Remember you can pause & continue the sim, and change the simulation speed)

<div class="sim">
		<iframe src="sim?stage=int-4&format=lines" width="800" height="540"></iframe>
</div>

This *would* keep cases below ICU capacity! And it's *much* better than an 18-month lockdown until a vaccine is available. We just need to... shut down for a few months, open up for a few months, and repeat until a vaccine is available. (And if there's no vaccine, repeat until herd immunity is reached... in 2022.)

Look, it's nice to draw a line saying "ICU capacity", but there's lots of important things we *can't* simulate here. Like:

**Mental Health:** Loneliness is one of the biggest risk factors for depression, anxiety, and suicide. And it's as associated with an early death as smoking 15 cigarettes a day.[^loneliness]

[^loneliness]: See [Figure 6 from Holt-Lunstad & Smith 2010](https://journals.sagepub.com/doi/abs/10.1177/1745691614568352). Of course, big disclaimer that they found a *correlation*. But unless you want to try randomly assigning people to be lonely for life, observational evidence is all you're gonna get.

**Financial Health:** "What about the economy" sounds like you care more about dollars than lives, but "the economy" isn't just stocks: it's people's ability to provide food & shelter for their loved ones, to invest in their kids' futures, and enjoy arts, foods, videogames – the stuff makes life worth living. And besides, poverty *itself* has horrible impacts on mental and physical health.

Not saying we *shouldn't* lock down again! We'll look at "circuit breaker" lockdowns later. Still, it's not ideal.

But wait... haven't Taiwan and South Korea *already* contained COVID-19? For 4 whole months, *without* long-term lockdowns?

How?

###Scénario 4 : Test, Suivi, Isolement

*« Bien sûr, on \*pourrait\* avoir fait comme Taïwan et la Corée du Sud ont fait au début, mais c'est désormais trop tard. On a loupé le départ. »*

Mais c'est justement ça ! « Un confinement n'est pas un remède, c'est juste un redémarrage »… **et c'est exactement d'un nouveau départ dont nous avons besoin.**

Pour comprendre comment Taïwan et la Corée du Sud ont contenu le Covid-19, nous devons comprendre le déroulement précis d'une infection typique au Covid-19[^timeline] :

[^timeline]: **3 jours en moyenne jusqu'à l'infectiosité :** « En présumant une distribution de la période d'incubation avec une moyenne de 5,2 jours grâce à une autre étude des premiers cas de Covid-19, nous avons déduit que l'infectiosité démarrait 2,3 jours (IC 95%, 0,8–3,0 jours) avant l'apparition des symptômes » (traduction : En présumant que les symptômes démarrent à 5 jours, l'infectiosité démarre 2 jours plus tôt = l'nfectiosité démarre à 3 jours) [He, X., Lau, E.H.Y., Wu, P. et al.](https://www.nature.com/articles/s41591-020-0869-5)  
    
	**4 jours en moyenne pour infecter quelqu'un d'autre :** « L'intervalle moyen [en série] était de 3,96 jours (IC 95% 3,53–4,39 jours) » [Du Z, Xu X, Wu Y, Wang L, Cowling BJ, Ancel Meyers L](https://wwwnc.cdc.gov/eid/article/26/6/20-0357_article)
    
	**5 jours en moyenne pour ressentir des sypmtômes :** « La période d'incubation moyenne a été estimée à 5,1 jours (IC 95%, 4,5 à 5,8 jours) » [Lauer SA, Grantz KH, Bi Q, et al](https://annals.org/AIM/FULLARTICLE/2762808/INCUBATION-PERIOD-CORONAVIRUS-DISEASE-2019-COVID-19-FROM-PUBLICLY-REPORTED)

![](pics/timeline1.png)

Si les cas s'auto-isolent seulement quand ils savent qu'ils sont malades (c'est-à-dire quand ils ressentent des symptômes), le virus peut encore se répandre :

![](pics/timeline2.png)

Et en fait, 44% de toutes les transmissions se font de cette façon: *pré*-symptomatique ! [^pre_symp]

[^pre_symp]: « Nous avons estimé que 44% (intervall de confiance de 95%, 25–69%) des cas secondaires avaient été infectés pendant l'étape présymptomatique des cas index » [He, X., Lau, E.H.Y., Wu, P. et al](https://www.nature.com/articles/s41591-020-0869-5)

Mais, si nous trouvons *et mettons en quarantaine* les contacts récents d'un cas symptomatique… on arrête la propagation, en ayant toujours un coup d'avance !

![](pics/timeline3.png)

C'est ce qu'on appelle le **traçage des contacts**. C'est une vieille idée, elle a été utilisée à une échelle sans précédent pour contenir Ebola[^ebola], and maintenant elle est une partie centrale de comment Taïwan et la Corée du Sud contiennent le Covdi-19 !

[^ebola]: « Le traçage des contacts a été une intervention critique au Liberia et a représenté un des plus grands efforts de traçage de contacts de l'histoire. » [Swanson KC, Altare C, Wesseh CS, et al.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6152989/)

(Il nous permet aussi d'utiliser nos tests limités plus efficacement, pour trouver les <icon i></icon>s pré-symptomatiques sans avoir besoin de tester tout le monde.)

Traditionnellement, les contacts sont trouvés grâce à des entretiens physiques, mais à eux *seuls*, ils sont trop lents pour la fenêtre d'environ 48 heures du Covid-19. C'est pourquoi les traceurs de contacts ont besoin d'aide, et sont aidés par — *PAS* remplacés par — des applis de traçage de contacts.

(Cette idée n'est pas venus des « techos » : utiliser une appli pour combattre le Covid-19 a été proposé en premier par [une équipe d'épidémiologistes d'Oxford](https://science.sciencemag.org/content/early/2020/04/09/science.abb6936).)

Attendez, des applis qui tracent avec qui vous avez été en contact ?… Est-ce que ça veut dire abandonner toute confidentialité, céder à Big Brother ?

Sûrement pas ! **[DP-3T](https://github.com/DP-3T/documents#decentralized-privacy-preserving-proximity-tracing)**, une équipe d'épidémiologistes et de cryptographeurs (y compris l'un de nous, Marcel Salathé) est *déjà* en train de créer une appli de traçage de contacts — dont le code est publique — qui ne révèle **aucune info à propos de votre identité, position, qui sont vos contacts ou même *avec combien de personnes* vous avez été en contact.**

Voici comment ça marche :

![](pics/dp3t.png)

(et [voici la BD entière](https://ncase.me/contact-tracing/))

Avec d'autres équipes similaires comme TCN Protocol[^tcn] et MIT PACT[^pact], ils ont inspiré Apple et Google à intégrer un traçage de contacts avec confidentialité avant tout dans Android/iOS.[^gapple] (Vous ne faites pas confiance à Google/Apple ? Bien ! La beauté de ce système est qu'il n'a *pas besoin* de confiance !) Bientôt, votre agence de santé publique locale pourrait vous demander de télécharger une appli. Si c'est avec confidentialité avant tout et du code publique, je vous en prie !

[^tcn]: [Temporary Contact Numbers, un protocole de traçage de contact décentralisé, avec confidentialité avant tout](https://github.com/TCNCoalition/TCN#tcn-protocol)

[^pact]: [PACT: Private Automated Contact Tracing](https://pact.mit.edu/)

[^gapple]: [Apple et Google collaborent sur une technologies de traçage de contact pour le Covid-19](https://www.apple.com/ca/newsroom/2020/04/apple-and-google-partner-on-covid-19-contact-tracing-technology/). Notez qu'ils ne font pas les applis *eux-mêmes*, ils créent juste les systèmes qui vont *permettre* ces applis.

Mais quid des gens sans smartphones ? Ou des infections par les poignées de portes ? Ou des cas « vraiment » asymptomatiques ? Les applis de traçage de contacts ne peuvent pas détecter toutes les transmissions… *et ce n'est pas un problème !* On n'a pas besoin de détecter *toutes* les transmissions, seulement 60% pour avoir R < 1.

(Diatribe à propos du mélange entre pré-symtpomatique et « vrai » asymptomatique. Les « vrais » asymptomatiques sont rares :[^rant])

[^rant]: Beaucoup de journaux — et franchement, beaucoup d'articles de recherche — n'ont pas fait la distinction entre « les cas qui ne montrent pas de symptômes quand on les a testés » (pré-symptomatique) et « les cas qui n'ont *jamais* montré de symptômes » (vrai asymptomatique). La seule manière de faire la différence est de suivre les cas par la suite.
   
    Ce qui est ce que [cette étude](https://wwwnc.cdc.gov/eid/article/26/8/20-1274_article) a fait. (Avertissement : « Les distributions préliminaires ne sont pas considérées des versions finales. ») Dans un centre d'appel en Corée du Sud qui a eu une épidémie de Covid-19, « seulement 4 (1,9%) sont restés asymptomatiques pendant 14 jours de quarantaine et aucun de leurs contacts domestiques n'ont eu d'infections secondaires. »
    
	Donc ça veut dire que les « vrais asymptomatiques » sont rares et qu'attraper la maladie d'un vrai asymptomatique pourrait être encore plus rare !

Isoler les cas *symptomatiques* réduirait R jusqu'à 40% et mettre en quarantaine leurs contact *pré/a-symptomatiques* réduirait R jusqu'à 50%[^oxford] :

[^oxford]: De la même étude d'Oxford qui a recommandé en premier de combattre le Covid-19 avec des applis : [Luca Ferretti & Chris Wymant et al](https://science.sciencemag.org/content/early/2020/04/09/science.abb6936/tab-figures-data) Regardez la Figure 2. En présumant que R<sub>0</sub> = 2.0, ils ont trouvé que :
    
	* Les symptomatiques contribuent R = 0,8 (40%)
	* Les pré-symptomatiques contribuent R = 0,9 (45%)
	* Les asymptomatiques contribuent R = 0,1 (5%, quoique leur modèle a de l'incertitude et cela pourrait être bien plus bas)
	* Les trucs environnementaux comme les poignées de porte contribuent R = 0,2 (10%)

	Et ajoutez les contacts pré- et a-symptomatiques (45% et 5%) et vous obtenez 50% de R !

<div class="sim">
		<iframe src="sim?stage=int-4a&format=calc" width="285" height="340"></iframe>
</div>

Ainsi, même sans mettre en quarantaine 100% des contacts, on peut obtenir R < 1 *sans confinement !* Bien mieux pour notre santé mentale et financière. (Et pour le coût pour les gens qui doivent s'auto-isoler ou se mettre en quarantaine, *les gouvernements devraient les soutenir* — payer pour les tests, la protection de l'emploi, subventionner les congés maladie, etc. C'est toujours bien moins cher que du confinement intermittent.)

On garde alors R < 1 jusqu'à ce qu'on ait un vaccin, qui transforme les susceptibles <icon s></icon>s en immunisés <icon r></icon>s. L'immunité grégaire, de la *bonne* manière :

<div class="sim">
		<iframe src="sim?stage=int-4b&format=calc" width="285" height="230"></iframe>
</div>

(Note : ce calculateur fait semblant que les vaccins sont efficaces à 100%. Rappelez-vous qu'en réalité, il faudrait compenser en vaccinant *plus* que « l'immunité grégaire », pour *vraiment* obtenir l'immunité grégaire)

OK, assez parlé. Voici une simulation de :

1. Un confinement de quelques mois, jusqu'à ce qu'on puisse…
2. Passer à « Tester, Tracer, Isoler » jusqu'à ce qu'on puisse…
3. Vacciner assez de gens, ce qui veut dire que…
4. On a gagné.

<div class="sim">
		<iframe src="sim?stage=int-5&format=lines" width="800" height="540"></iframe>
</div>

Et c'est tout ! Voilà comment on fait un atterrissage d'urgence avec cet avion.

Voilà comment on bat le Covid-19.

…

Mais et si les choses se passent *quand même* mal ? Les choses se sont déjà horriblement mal passées. C'est de la peur, et c'est bien ! La peur nous donne l'énergie de créer des *plans de secours*.

Le pessimiste invente le parachute.

###Scenario 4+ : Masques pour tous, été, "Disjoncteur" 

Et si R<sub>0</sub> était bien plus grand que ce que l'on pense, et que les actions précédentes, même aidées d'une légère distanciation, n'était *toujours* pas suffisantes pour rendre R < 1?

Souvenez-vous, même si on ne peut rendre R < 1, minimiser R permet quand même de réduire le "débordement" du total de cas, donc de sauver des vies. Pour autant, R < 1 reste l'idéal, et voici d'autres moyens pour le réduire:

**Masques pour tous:**

*"Attendez,"* vous nous demanderez, *"Je pensais que les masques n'empêchaient pas de tomber malade ?"*

Et vous avez raison. Les masques n'empêchent pas de tomber malade[^incoming]... ils vous empêchent de faire tomber malade *les autres*.

[^incoming]: “None of these surgical masks exhibited adequate filter performance and facial fit characteristics to be considered respiratory protection devices.” [Tara Oberg & Lisa M. Brosseau](https://www.sciencedirect.com/science/article/pii/S0196655307007742) Traduction : "Aucun des masques chirurgicaux n'a présenté des performances de filtrage et des caractéristiques d'ajustement facial suffisantes pour être considéré comme un dispositif de protection respiratoire."

[^outgoing]: “The overall 3.4 fold reduction [70% reduction] in aerosol copy numbers we observed combined with a nearly complete elimination of large droplet spray demonstrated by Johnson et al. suggests that surgical masks worn by infected persons could have a clinically significant impact on transmission.” [Milton DK, Fabian MP, Cowling BJ, Grantham ML, McDevitt JJ](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3591312/) Traduction : "La réduction globale de 3,4 fois (70% de réduction) du nombre de particules aériennes que nous avons observées, combinée à l'élimination quasi complète des projections des grosses goutelettes démontrée par Johnson et al. suggère que le port du masque par les personnes infectées pourrait avoir un impact cliniquement significatif sur la transmission."

[^homemade]: [Davies, A., Thompson, K., Giri, K., Kafatos, G., Walker, J., & Bennett, A](https://www.cambridge.org/core/journals/disaster-medicine-and-public-health-preparedness/article/testing-the-efficacy-of-homemade-masks-would-they-protect-in-an-influenza-pandemic/0921A05A69A9419C862FA2F35F819D55) Voir Table 1: un T-shirt en coton a environ deux tiers de l'efficacité de filtration d'un masque chirurgical, pour les deux aérosols bactériens qu'ils ont testés.

![](pics/masks.png)

Pour mettre un chiffre là-dessus: les masques chirugicaux *portés par la personne malade* réduisent ses projections de rhumes et grippes de 70%.[^outgoing] Réduire les transmissions de 70% aurait un impact aussi important qu'un confinement !

Cependant, on ne connait pas encore précisément l'impact des masques sur le COVID-19 *en particulier*. En science, on ne devrait publier un résultat que si l'on en est (statistiquement) sûr à 95%. (...devrait.[^replication]) L'usage de masques, au 1er mai 2020, n'est pas "sûr à 95%".

[^replication]: N'importe quel véritable scientifique qui lit cette dernière phrase est probalement plié de rire. Voir: [p-hacking](https://fr.wikipedia.org/wiki/Data_dredging), [crise de la reproductibilité](https://fr.wikipedia.org/wiki/Crise_de_la_reproductibilit%C3%A9))

Pour autant, les pandémies c'est comme le poker. **Ne pariez que lorsque vous êtes sûr à 95%, et vous perdrez tout ce qui est en jeu.** Comme le fait noter un récent article du British Medical Journal,[^precautionary] dans un contexte d'incertitude, il est *nécessaire* d'appliquer des analyses coûts-avantages. Par exemple:

[^precautionary]: “It is time to apply the precautionary principle” [Trisha Greenhalgh et al \[PDF\]](https://www.bmj.com/content/bmj/369/bmj.m1435.full.pdf) Traduction: "Il est temps d'appliquer le principe de précaution."

Coûts: Pour des masques en tissu faits maison, même coût que le savon et le lavage des mains. Pour des masques chirurgicaux, un peu plus cher mais encore peu coûteux.

Bénéfices: Même s'il y avait 50% de chances que les masques chirurgicaux réduisent la transmission ou de 0%, ou de 70%, cela donnerait en moyenne 35%, autant qu'un demi-confinement ! Estimons donc que les masques réduisent R jusqu'à 35%. (Encore une fois, vous pouvez changer nos hypothèses en ajustant les curseurs)

**Voici un calculateur de réduction de R grâce aux masques! Vous pouvez choisir entre tissu et chirurgical:** (en supposant que les masques en tissu ont deux tiers de l'efficacité d'un masque chirurgical[^homemade])

<div class="sim">
		<iframe src="sim?stage=int-6a&format=calc" width="285" height="380"></iframe>
</div>

(autres arguments pour/contre le port du masque:[^mask_args])

[^mask_args]: **"Nous devons garder les provisions pour les hôpitaux."** *Absolument d'accord.* Mais c'est plus un argument en faveur de l'augmentation de la production, pas du rationnement. En attendant, nous pouvons faire des masques en tissu.

   **"C'est difficile de les porter correctement."** C'est aussi difficile de se laver les mains en respectant les indications de l'OMS - vraiment, "Etape 5) les dos des doigts en les tenant dans la paume des mains opposées"?! – bien sûr nous recommandons quand même le lavage des mains, l'imperfection vaut mieux que rien du tout.
   
   **"Cela va rendre les gens imprudents pour le lavage des mains et la distanciation sociale."** Bien sûr, et les ceintures de sécurité font que les gens ignorent les panneaux stop, et les fils dentaires font que les gens mangent des pierres. Plus sérieusement, nous dirions le contraire: les masques sont un *rappel visuel constant* à la prudence – et en Asie de l'Est, les masques sont aussi un symbole de solidarité !
    
    

Les masques *seuls* ne vont pas rendre R < 1. Mais si le lavage des mains et la méthode "Test, suivi, isolement" ne nous amène qu'à R = 1.10, avoir ne serait-ce que deux tiers de la population portant des masque *en tissu* permettra d'atteindre R < 1, et le virus sera contenu!

**Eté:**

D'accord, ce n'est pas une "intervention" que nous pouvons contrôler, mais ça va aider! Certains médias rapportent que l'été n'aura pas d'impact sur le COVID-19. Ils ont à moitié raison : l'été ne va pas rendre R < 1, mais *il va réduire* R.

Pour le COVID-19, chaque degré Celsius supplémentaire (2.2° Fahrenheit) fait diminuer R de 1.2%.[^heat] La différence été-hiver à Paris est de 15°C (60°F), donc l'été devrait faire diminuer R de 18%.

[^heat]: “One-degree Celsius increase in temperature [...] lower[s] R by 0.0225” and “The average R-value of these 100 cities is 1.83”. 0.0225 ÷ 1.83 = ~1.2%. [Wang, Jingyuan and Tang, Ke and Feng, Kai and Lv, Weifeng](https://papers.ssrn.com/sol3/Papers.cfm?abstract_id=3551767) Traduction : "Une augmentation d'un degré Celsius de la température [...] diminue R de 0,0225" et "La valeur moyenne de R dans ces 100 villes est de 1,83." 0.0225 ÷ 1.83 = ~1,2%.

<div class="sim">
		<iframe src="sim?stage=int-6b&format=calc" width="285" height="220"></iframe>
</div>

L'été seul ne va pas rendre R < 1, mais en cas de resources limitées, permettra de réduire certaines interventions en été – afin de pouvoir les *intensifier* en hiver.

**Un confinement "disjoncteur":**

Et si tout cela ne permet *toujours* pas d'atteindre R < 1... nous pouvons nous confiner à nouveau.

Mais nous n'aurions pas à alterner 2 mois confinés/1 mois ouvert encore et encore! R ayant diminué, nous n'aurions qu'à réaliser ce confinement "disjoncteur" une ou deux fois avant que le vaccin ne soit disponible. (Singapour a procédé ainsi récemment, "même" s'ils avaient réussi à contrôler le virus pendant 4 mois. Ce n'est pas un échec: c'est *ce qu'il faut* pour réussir.)

Voici une simulation d'un scenario "pas trop d'effort":

1. Confinement, puis
2. Un niveau correct d'hygiène + "Test, suivi, isolement" + "Masques pour tous" en *tissu*, et...
3. Un dernier confinement "disjoncteur" avant que le vaccin ne soit trouvé.

<div class="sim">
		<iframe src="sim?stage=int-7&format=lines&height=620" width="800" height="620"></iframe>
</div>

Sans parler de toutes les *autres* actions qui peuvent être mises en place pour minimiser R encore plus:

* Restrictions des voyages/quarantaines
* Contrôle de la température dans les centres commerciaux et les écoles
* Nettoyage en profondeur des espaces publics
* [Remplacer la poignée de main par le "check des pieds"](https://twitter.com/V_actually/status/1233785527788285953)
* Et tout ce que l'ingéniosité humaine peut approter

. . .

Nous espérons que ces plans vous donnent de l'espoir.  

**Même dans les cas les plus défavorables, *il est possible* de vaincre le COVID-19 tout en protégeant notre santé mentale et financière.** Utiliser le confinement comme un "bouton de remise à zéro", garder R < 1 avec isolation des cas + suivi des contacts respecteux de la vie privée + des masques *au moins* en tissus pour tous... et la vie peut reprendre son cours !

Bien sûr, vous aurez sans doute les mains sèches. Mais vous pourrez inviter la personne qui vous plaît à la librairie ! Vous pourrez dilapider vos économies dans les derniers film hollywoodiens avec vos amis. Vous pourrez espionner les gens à la bibliothèque, vous réjouissant de les voir s'adonner à la simple activité d'*être en vie*.

Même dans les pires scénarios... la vie continue.

Donc maintenant, faisons des plans pour quelques scénarios catastrophes. Amérissage, attrapez votre gilet de sauvetage et suivez les lumières vers les sorties de secours:

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

Même dans *le pire* des pires scénarios... La vie continue.

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
