<div class="section">
    <div>
    	<iframe id="splash" width="960" height="480" src="banners/splash.html"></iframe>
        <div style="top: 70px;font-size: 75px;font-weight: bold;">
        	¿Qué ocurrirá ahora?
       	</div>
		<div style="font-weight: 500;top: 140px;left: 10px;font-size: 29px;">
			Los futuros de la COVID-19, explicados con simulaciones
		</div>
		<div style="font-weight: 100;top: 189px;left: 10px;font-size: 19px;line-height: 21px;">
			<b>
				🕐 30 min ver/leer
				&nbsp;&middot;&nbsp;
			</b>
			por
			<a href="https://scholar.google.com/citations?user=_wHMGkUAAAAJ&amp;hl=en">Marcel Salathé</a>
			(epidemiólogo)
			&
			<a href="https://ncase.me/">Nicky Case</a>
			(arte/código)
		</div>
	</div>
</div>

«Sólo tenemos que tener miedo al propio miedo» fue un consejo estúpido.

Por supuesto, no hay que hacer acopio del papel higiénico, pero si los responsables públicos tienen miedo al miedo, tenderán a minimizar los peligros reales para evitar la «histeria colectiva». El problema no es el miedo, es cómo *canalizamos* nuestro miedo. El miedo nos da fuerzas para enfrentarnos a los peligros actuales y para prepararnos para los futuros.

Sinceramente, nosotros (Marcel, epidemiólogo + Nicky, arte/código) estamos preocupados. ¡Y pensamos que tú también lo estarás! Por eso hemos canalizado nuestro miedo en hacer estas **simulaciones interactivas**, para que *tu* puedes canalizar tu miedo en comprensión:

* **Los últimos meses** (introducción a la epidemiología, modelo SEIR, R y R<sub>0</sub>).
* **Los próximos meses** (confinamientos, rastreo de contactos, mascarillas).
* **Los próximos años** (¿pérdida de inmunidad? ¿ausencia de vacunas?).

El objetivo de esta guía (publicada el 1 de mayo de 2020, haga clic en esta nota al pie de página→[^timestamp]) es darle esperanza *y* miedo. Para ganar a la COVID-19 **de una forma que también proteja nuestra salud mental y financiera**, necesitamos optimismo para  crear planes, y pesimismo para crear planes de contingencia. Como Gladys Bronwyn Stern dijo una vez: *«El optimismo inventa el avión y el pesimismo el paracaídas».*

[^timestamp]: Estas notas al pie de página mostrarán fuentes, enlaces y comentarios extra. ¡Como este comentario!
    
    **Esta guía se publicó el 1 de mayo de 2020.** Muchos de los detalles caducarán eventualmente, pero estamos seguros de que la guía cubre el 95% de los futuros posibles, y que la introducción a la epidemiología será un recurso útil perenne.

Abróchese el cinturón: vamos a sufrir algunas turbulencias.

<div class="section chapter">
    <div>
		<img src="banners/curve.png" height=480 style="position: absolute;"/>
        <div>Los próximos meses</div>
    </div>
</div>

Los pilotos usan simuladores de vuelo para aprender cómo evitar que los aviones se estrellen.

**Los epidemiólogos usan simuladores para aprender cómo evitar que la humanidad se estrelle.**

Así que, venga, ¡hagamos un "simulador de vuelo de epidemias" muy, *muy* simple! En esta simulación, las personas <icon i></icon> Infecciosas pueden convertir a las personas <icon s></icon> Susceptibles en aún más personas <icon i></icon> Infecciosas:

![](pics/spread.png)

Se estima que, *al comienzo* de un brote de la COVID-19, el virus salta de una <icon i></icon> a una <icon s></icon> cada 4 días, *en promedio*.[^serial_interval] (recuerde, hay mucha variabilidad)

[^serial_interval]: «The mean [serial] interval was 3.96 days (95% CI 3.53–4.39 days)». [Du Z, Xu X, Wu Y, Wang L, Cowling BJ, Ancel Meyers L](https://wwwnc.cdc.gov/eid/article/26/6/20-0357_article) (Aviso: La publicación temprana de estos artículos no están consideradas como versiones finales)

Si simulamos que se «doble cada cada 4 días» *y nada más*, en una población que al comienzo sólo tiene 0.001% <icon i></icon>, ¿qué ocurre?

**¡Haga clic al botón "Iniciar" para comenzar la simulación! Podrás reiniciarla luego con diferentes ajustes:** (consideración técnica: [^caveats])

[^caveats]: **Recuerde: todas estas simulaciones están muy simplificadas para propósito didáctico.**
    
    Una simplificación: Cuando le dices a la simulación «Infecta 1 persona cada X días», en realidad se está incrementando el número de infectados por 1/X cada día. Lo mismo para los ajustes futuros en estas simulaciones – «Recuperados cada X días» en realidad se reduce el número de infectados en 1/X por día.
    
    En realidad, *no son* exactamente lo mismo, pero se aproximan lo suficiente y para propósitos didácticos es menos opaco que ajustar las tasas de transmisión y recuperación directamente.

<div class="sim">
		<iframe src="sim?stage=epi-1" width="800" height="540"></iframe>
</div>

Esta es la **curva de crecimiento exponencial.** Comienza pequeña y en determinado momento explota. De «Oh, es cómo la gripe» a «Oh claro, la gripe no crea *fosas comunes en ciudades ricas*».

![](pics/exponential.png)

Pero esta simulación no es correcta. El crecimiento exponencial, afortunadamente, no puede continuar indefinidamente. Una cosa que para el contagio del virus es cuando *ya hay* personas que tienen el virus:

![](pics/susceptibles.png)

Cuanto más <icon i></icon>s hay, más rápido los <icon s></icon>s se vuelven <icon i></icon>s, **pero cuantos menos <icon s></icon>s haya, más *lento* los <icon s></icon>s se convetirán en <icon i></icon>s.**

¿Cómo cambia ésto el crecimiento de la epidemia? Vamos a comprobarlo:

<div class="sim">
		<iframe src="sim?stage=epi-2" width="800" height="540"></iframe>
</div>

Es esta la **curva de crecimiento logística** con forma de S. Comienza plana, luego explota y luego se aplana otra vez.

Pero. Esta simulación *todavía* no es correcta. No estamos teniendo en cuenta que las personas <icon i></icon> Infecciosas dejan de serlo en determinado momento, ya sea porque 1) se recuperan, 2) se "recuperan" con daños pulmonares, o 3) se mueren.

Para simplificar la cuestión, vamos a asumir que todas las personas <icon i></icon> Infecciosas pasan a <icon r></icon> Recuperadas. (Pero recuerda que en realidad algunas fallecen). Las <icon r></icon>s no pueden infectarse de nuevo, y vamos a asumir – *¡por ahora!* – que serán inmunes el resto de sus vidas.

Con la COVID-19, se estima que eres <icon i></icon> Infeccioso durante 10 días, *en promedio*.[^infectiousness] Eso significa que algunas personas se recuperan antes de 10 días y otras después. **Aquí se ve como es eso, con una simulación que *comienza* con un 100% de <icon i></icon>:**

[^infectiousness]: «The median communicable period \[...\] was 9.5 days». [Hu, Z., Song, C., Xu, C. et al](https://link.springer.com/article/10.1007/s11427-020-1661-4) Sí, sabemos que la «mediana» no es lo mismo que la «media». Pero para propósitos educativos, se parecen bastante.

<div class="sim">
		<iframe src="sim?stage=epi-3" width="800" height="540"></iframe>
</div>

Esto es lo contrario de un crecimiento exponencial, la **curva de decaimiento exponencial.**

Y ahora, ¿qué ocurre si simulas un crecimiento logístico con forma de S *con* recuperación?

![](pics/graphs_q.png)

Vamos a comprobarlo.

La <b style='color:#ff4040'>curva roja</b> son los casos *actuales* <icon i></icon>,    
La <b style='color:#999999'>curva gris</b> son los casos *totales* (actuales + recuperados <icon r></icon>),
comienzan con solo 0.001% <icon i></icon>:

<div class="sim">
		<iframe src="sim?stage=epi-4" width="800" height="540"></iframe>
</div>

¡Y *de ahí* es de donde viene la famosa curva! No es una curva de Bell, ni siquiera una curva «log-normal». No tiene nombre. Pero la habrás visto un millón de veces e implorado que se aplane.

Éste es el **modelo SIR**,[^sir]    
(<icon s></icon>**S**usceptibles <icon i></icon>**I**nfecciosos <icon r></icon>**R**ecuperados)      
la *segunda* idea más importante en la Introducción a la Epidemiología:

[^sir]: Para más detalles técnicos del modelo SIR, consultar [Institute for Disease Modeling](https://www.idmod.org/docs/hiv/model-sir.html#) y [Wikipedia](https://es.wikipedia.org/wiki/Modelo_SIR)

![](pics/sir.png)

**NOTA: Las simulaciones que se usan para tomar decisiones públicas son mucho, *mucho* más sofisticadas que ésta!** Pero el modelo SIR puede explicar los mismos fenómenos generales, aún sin los matices.

Bueno, vamos a añadir otro matiz más: antes de que <icon s></icon> se convierta en <icon i></icon>, antes se convierten en personas <icon e></icon> Expuestas. Esto ocurre cuando tienen el virus pero aún no pueden transmitirlo – infec*tadas* pero todavía no son infec*ciosas*.

![](pics/seir.png)

(Esta variante es el llamado **modelo SEIR**[^seir], donde «E» son las personas <icon e></icon> «Expuestas». Ten en cuenta que este *no es* el significado habitual de «expuesto», cuando puedes o puedes no tener el virus. En esta definición técnica, «Expuesto» significa que lo tienes con seguridad. La terminología científica es mala).

[^seir]: Para más explicaciones ténicas del modelo SEIR, consultar [Institute for Disease Modeling](https://www.idmod.org/docs/hiv/model-seir.html) and [Wikipedia](https://es.wikipedia.org/wiki/Modelaje_matemático_de_epidemias#Modelo_SEIR)

Para la COVID-19, se estima que las personas son <icon e></icon> infectadas-pero-aún-no-infecciosas durante 3 días, *de promedio*.[^latent] ¿Qué ocurre si añadimos eso a la simulación?

[^latent]: «Assuming an incubation period distribution of mean 5.2 days from a separate study of early COVID-19 cases, we inferred that infectiousness started from 2.3 days (95% CI, 0.8–3.0 days) before symptom onset» (traducción: Si asumimos que los síntomas comienzan a los 5 días, la fase infecciosa comienza 2 días antes = la contagiosidad comienza a los 3 días) [He, X., Lau, E.H.Y., Wu, P. et al.](https://www.nature.com/articles/s41591-020-0869-5)

La <b style='color:#ff4040'>curva roja <b style='color:#FF9393'>+ rosa</b></b> son casos *actuales* (infecciosos <icon i></icon> + expuestos <icon e></icon>),    
La <b style='color:#888'>curva gris</b> son casos *totales* (actuales + recuperados <icon r></icon>):

<div class="sim">
		<iframe src="sim?stage=epi-5" width="800" height="540"></iframe>
</div>

¡Sin grandes cambios! El tiempo en el que se está <icon e></icon> Expuesto cambia con la relación de <icon e></icon>-a-<icon i></icon>, y *cúando* ocurre el pico de casos actuales... pero la *altura* del pico, y el total de casos, no cambian.

¿Por qué? Por la *primera* y más importante idea de la Introducción a la Epidemiología:

![](pics/r.png)

Abreviación de «número reproductivo». Es el número de personas *promedio* a las que una <icon i></icon> contagia *antes* de recuperarse (o fallecer).

![](pics/r2.png)

**R** cambia en el transcurso de una epidemia, según se obtiene más inmunidad y hay más intervenciones.

**R<sub>0</sub>** es el número R *al comienzo de un brote, antes de la inmunidad o las intervenciones*. R<sub>0</sub> refleja sobre todo el poder del propio virus, aunque cambia de un lugar a otro. Por ejemplo, R<sub>0</sub> es mayor en ciudades de gran densidad que en las áreas rurales y dispersas.

(La mayoría de los artículos periodísticos – ¡incluso algunos artículos científicos! – confunden R y R<sub>0</sub>. De nuevo, la terminología científica es mala).

El R<sub>0</sub> para «la» gripe estacional es de 1.28[^r0_flu]. Esto implica que, al *comienzo* de la epidemia, cada <icon i></icon> contagia a otras 1.28 *de media.* (Si le parece extraño que no sea un número entero, recuerde que una madre «promedio» tiene 2.4 hijos. Lo que no significa que tengan medio bebé gateando a su alrededor).

[^r0_flu]: “The median R value for seasonal influenza was 1.28 (IQR: 1.19–1.37)” [Biggerstaff, M., Cauchemez, S., Reed, C. et al.](https://bmcinfectdis.biomedcentral.com/articles/10.1186/1471-2334-14-480)

El R<sub>0</sub> para la COVID-19 se estima en 2.2,[^r0_covid] aunque un estudio *aún-no-finalizado* lo estima en 5.7(!) en Wuhan.[^r0_wuhan]

[^r0_covid]: «We estimated the basic reproduction number R0 of 2019-nCoV to be around 2.2 (90% high density interval: 1.4–3.8)» [Riou J, Althaus CL.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7001239/)

[^r0_wuhan]: «we calculated a median R0 value of 5.7 (95% CI 3.8–8.9)» [Sanche S, Lin YT, Xu C, Romero-Severson E, Hengartner N, Ke R.](https://wwwnc.cdc.gov/eid/article/26/7/20-0282_article)

En nuestras simulaciones – *al inicio y de media* – una <icon i></icon> infecta a alguien cada 4 días, durante 10 días. «4 días» pasan a ser «10 days» dos veces y media. Esto significa que – *al incio y de media* – cada <icon i></icon> contagia a otras 2.5 personas. Por tanto, R<sub>0</sub> = 2.5. (matizaciones:[^r0_caveats_sim])

[^r0_caveats_sim]: Esto asume que una persona es igual de contagiosa durante toda el periodo infeccioso. De nuevo, es una simplificación en aras de la didáctica.

**Juegue con esta calculadora de R<sub>0</sub>, para ver como R<sub>0</sub> depende del tiempo de recuperación y el tiempo de nuevo contagio:**

<div class="sim">
		<iframe src="sim?stage=epi-6a&format=calc" width="285" height="255"></iframe>
</div>

Pero recuerde, cuantas menos personas <icon s></icon>s haya, más *lento* se convertirán las <icon s></icon>s en <icon i></icon>s. El número de reproducción *actual* (R) depende no solo del número de reproducción *básico* (R<sub>0</sub>), sino *también* de cuantas personas ya no sea <icon s></icon> Susceptibles. (Por ejemplo, debido a la recuperación y obteniendo inmunidad natural).

<div class="sim">
		<iframe src="sim?stage=epi-6b&format=calc" width="285" height="390"></iframe>
</div>

Cuando haya un número suficiente de personas con inmunidad, R < 1, y el virus esté contenido, esto se llama **inmunidad de grupo**. Para la gripe la inmunidad de grupo se consigue *con una vacuna*. Intentar alcanzar la «inmunidad de grupo natural» dejando que las personas se contagien es una idea *horrible*. (¡Pero no por lo que puedes estar pensando! Luego lo explicamos).

Ahora, juguemos con el modelo SEIR otra vez, pero mostrando R<sub>0</sub>, R en el tiempo, y el umbral de la inmunidad de grupo:

<div class="sim">
		<iframe src="sim?stage=epi-7" width="800" height="540"></iframe>
</div>

**NOTA: ¡Los casos totales *no se detienen* al llegar a la inmunidad de grupo, sino que lo exceden!** Y cruza el umbral *exactamente* cuando se llega al pico de casos actuales. (Eso ocurre cualesquiera que sean los ajustes – ¡inténtalo tú mismo!)

Esto pasa porque cuando hay más no-<icon s></icon>s que el umbral de inmunidad de grupo, tenemos R < 1. Y cuando R < 1, el número de nuecos casos deja de crecer: un pico.

**Si solo hay una lección que llevarse de esta guía, aquí está** – es un diagrama extremadamente complejo así que por favor, tómate tu tiempo para comprenderlo en su totalidad:

![](pics/r3.png)

**Esto significa: ¡NO necesitamos detener todos los contagios, o casi todos los contagios, para detener a la COVID-19!**

Es una paradoja. La COVID-19 es extremadamente contagiosa, pero para contenerla, «solo» necesitamos detener más del 60% de las infecciones. ¿!El 60%!? Si fuera una nota de la escuela, sería un 6. Pero si R<sub>0</sub> = 2.5, disminuir eso un 61% nos da R = 0.975, que es R < 1, ¡el virus está contenido! (exact formula:[^exact_formula])

[^exact_formula]: Recuerda R = R<sub>0</sub> * la tasa de contagios aún permitidos. Recuerda también que la tasa de contagios permitidos = 1 - tasa de contagios *evitados*.
    
    Por tanto, para llegar a R < 1, tienes que conseguir que R<sub>0</sub> * ContagiosPermitidos < 1. 
    
    Por tanto, ContagiosPermitidos < 1/R<sub>0</sub>
    
    Por tanto, 1 - ContagiosEvitados < 1/R<sub>0</sub>
    
    Por tanto, ContagiosEvitados > 1 - 1/R<sub>0</sub>
    
    Por tanto, ¡debes evitar más de **1 - 1/R<sub>0</sub>** de los contagios para que R < 1 y contener el virus!

![](pics/r4.png)

(Si crees que R<sub>0</sub> o el resto de números de nuestras simulaciones son muy pequeños/grandes, ¡es estupendo que pongas en duda nuestras suposiciones! Tenemos un "área de juegos" al final de esta guía, donde podrás indicar tus *propios* números y simular lo que ocurre con ellos).

*Todas* las intervenciones para la COVID-19 que hayas oído – lavado de manos, distanciamiento social/físico, confinamientos, auto-aislamiento, cuarentenas y rastreo de contactos, mascarillas, incluso la «inmunidad de grupo» – *todas* hacen exactamente la misma cosa:

Hacer que R < 1.

Así que ahora vamos a usar nuestro «simulador de vuelo de epidemias» para averiguar ésto: ¿Cómo hacemos que R < 1 de forma que **también protega nuestra salud mental *y* económica?**

Abróchense para un aterrizaje de emergencia...

<div class="section chapter">
    <div>
		<img src="banners/curve.png" height=480 style="position: absolute;"/>
        <div>Los próximos meses</div>
    </div>
</div>

...podría haber sido peor. Aquí está el universo paralelo que hemos evitado:

###Escenario 0: No hacer nada en absoluto

Alrededor de 1 de cada 20 personas contagiadas de la COVID-19 necesitan ir a una UCI (Unidad de Cuidados Intensivos).[^icu_covid] En un país desarrollado como EEUU, hay una UCI por cada 3400 personas.[^icu_us] Por tanto, EEUU puede tratar 20 de cada 3400 personas contagiadas *simultáneamente* – o el 0.6% de la población.

[^icu_covid]: [«Percentage of COVID-19 cases in the United States from February 12 to March 16, 2020 that required intensive care unit (ICU) admission, by age group»](https://www.statista.com/statistics/1105420/covid-icu-admission-rates-us-by-age-group/). Entre el 4.9% y el 11.5% de *todos* los casos de COVID-19 necesitan UCI. Si seleccionamos el rango inferior de forma optimista, eso es el 5% o 1 de cada 20. Observa que este total es específico a la estructura de edades de EEUU, y será más alto en poblaciones con poblaciones más viejas, y menor en países en poblaciones más jóvenes.

[^icu_us]: «Number of ICU beds = 96,596». De la [Society of Critical Care Medicine](https://sccm.org/Blog/March-2020/United-States-Resource-Availability-for-COVID-19) EEUU tiene una población de 328,200,000 en 2019. 96,596 de 328,200,000 = aproximadamente 1 de 3400. 

Incluso si *más que triplicamos* esa capacidad al 2%, aquí vemos qué es lo que hubiese ocurrido *si no hubiéramos hecho nada en absoluto:*

<div class="sim">
		<iframe src="sim?stage=int-1&format=lines" width="800" height="540"></iframe>
</div>

No pinta bien.

Esto es lo que [el informe del 16 de marzo del Imperial College](http://www.imperial.ac.uk/mrc-global-infectious-disease-analysis/covid-19/report-9-impact-of-npis-on-covid-19/) concluyó: sin hacer nada, nos quedamos sin UCIs libres, y se contagiaría más del 80% de la población. 
(recuerda: el total de casos *excede* la inmunidad de grupo)

Incluso si sólo el 0.5% de las personas contagiadas mueren – una suposición optimista cuando no hay más UCIs – en un país poblado como EEUU, con 300 millones de personas, el 0.5% del 80% de 300 million = 1.2 millones de fallecidos... *SI no se hace nada.*

(Muchos medios de comunicación y medios sociales informaron que «se contagiará el 80%» *sin* el «SI NO HACEMOS NADA». El miedo se canalizó en clics, no en la comprensión. *Ay.*)

###Escenario 1: Aplanar la curva / Inmunidad de grupo

El plan de "Aplana la curva" ha sido promocionado por todas las organizaciones de sanidad pública, mientras que el plan original para la «inmunidad de grupo» del Reino Unido ha sido abucheado. Eran *el mismo plan.* Solo que el Reino Unido lo comunicó mal.[^yong]

[^yong]: «He says that the actual goal is the same as that of other countries: flatten the curve by staggering the onset of infections. As a consequence, the nation may achieve herd immunity; it’s a side effect, not an aim. [...] The government’s actual coronavirus action plan, available online, doesn’t mention herd immunity at all».
    
    De un [artículo de The Atlantic por Ed Yong](https://www.theatlantic.com/health/archive/2020/03/coronavirus-pandemic-herd-immunity-uk-boris-johnson/608065/)

Sin embargo, ambos planes adolecían de un error fatal, literalmente.

Primero, veamos las dos maneras principales para "aplanar la curva": lavado de manos y distanciamiento físico.

El incremento del lavado de manos reduce la gripe y los resfriados en los países desarrollados en ~25%[^handwashing], mientras que un confinamiento en toda la ciudad de Londres reduce los contactos en ~70%[^london]. Así que, asumamos que el lavado de manos puede reducir R *hasta* un 25%, y el distanciamiento reduce R *hasta* un 70%:

[^handwashing]: «All eight eligible studies reported that handwashing lowered risks of respiratory infection, with risk reductions ranging from 6% to 44% [pooled value 24% (95% CI 6–40%)]». En aras de la simplicidad, en estas simulaciones hemos redondeado el valor hasta el 25%. [Rabie, T. y Curtis, V.](https://onlinelibrary.wiley.com/doi/full/10.1111/j.1365-3156.2006.01568.x) Nota: tal y como este meta-análisis indica, la calidad de las medidas sobre el lavado de manos (al menos en los países desarrollados) son pésimas.

[^london]: «We found a 73% reduction in the average daily number of contacts observed per participant. This would be sufficient to reduce R0 from a value from 2.6 before the lockdown to 0.62 (0.37 - 0.89) during the lockdown». En aras de la simplicidad, para esta simulación lo hemos redondeado al 70%. [Jarvis y Zandvoort et al](https://cmmid.github.io/topics/covid19/comix-impact-of-physical-distance-measures-on-transmission-in-the-UK.html)

**Juegue con esta calculadora para ver cómo el % de no-<icon s></icon>, el lavado de manos y el distanciamiento reducen R:** (esta calculadora visualiza sus efectos *relativos*, y esa es la razón por la que al incrementar uno *parece* que se reduce el efecto de los otros.[^log_caveat])

[^log_caveat]: La distorsión desaparecería si se mostrase a R en una escala logarítima... pero entonces, tendríamos que explicar las *escalas logarítmicas.*

<div class="sim">
		<iframe src="sim?stage=int-2a&format=calc" width="285" height="260"></iframe>
</div>

Ahora, simulemos lo que pasa cuando una epidemia de la COVID-19 cuando, al inicio de marzo de 2020, hubiéramos incrementado el lavado de manos pero solo *un poco* de distanciamiento social – de tal forma que R es menor, pero aún por encima de 1:

<div class="sim">
		<iframe src="sim?stage=int-2&format=lines" width="800" height="540"></iframe>
</div>

Tres notas:

1. ¡Esto *reduce* los casos totales! **Incluso sin R < 1, la reducción de R salva vidas al reducir el 'exceso' sobre la inmunidad de grupo.** Muchas personas piensan que el "aplanar la curva" esparce los casos sin reducir el número total. Esto es imposible en *ninguno* de los modelos de Introducción a la Epidemiología. Pero por culpa de las noticias muchos pensaron que el «más del 80% se contagiará» era inevitable, sin importar lo que hicieran. *Ay.*

2. Debido a las intervenciones adicionales, el número de casos actual tendrá el pico *antes* de que se llegue a la inmunidad de grupo. De hecho, en esta simulación, el número total de casos solo excede *un poquito* sobre la inmunidad de grupo – ¡el plan del Reino Unido! Y ahí, con R < 1, puedes deshacerte del resto de intervenciones y la COVID-19 se mantendrá contenida! Bueno, excepto por un problema...

3. Aún te puedes quedar sin UCIs. Durante muchos meses. (Y recuerda, *ya* hemos triplicado las UCIs para estas simulaciones).

Ese fue otro descubrimiento del informe del Imperial College del 16 de marzo, que convenció al Reino Unido de abandonar su plan original. Cualquier intento de **mitigación** (reducir R, pero R > 1) fracasará. La única forma de tener éxito es la **supresión** (reducir R de modo que R < 1).

![](pics/mitigation_vs_suppression.png)

Eso es, no solo "aplanar" la curva, es *despachurrar* la curva. Por ejemplo, con un...

###Escenario 2: Confinamiento de varios meses

Ahora veamos lo que ocurre si *despachurramos* la curva con un confinamiento de 5 meses, reducimos <icon i></icon> a prácticamente nada, y finalmente – *finalmente* – regresamos a la vida normal:

<div class="sim">
		<iframe src="sim?stage=int-3&format=lines" width="800" height="540"></iframe>
</div>

Oh.

Esta es la "segunda ola" de la que todo el mundo habla. Tan pronto como eliminemos el confinamiento, tenemos otra vez R > 1. Una simple <icon i></icon> olvidada (o <icon i></icon> importada) puede generar un brote de casos que sea tan mala como si hubiéramos hecho el escenario 0: Nada En Absoluto.

**Un confinamiento no es una cura, es un reinicio.**

Así que, ¿vamos nos confinamos una y otra vez?

###Escenario 3: Confinamiento intermitente

Esta solución se sugirió en el informe del Imperial College del 16 de marzo, y posteriormente por un artículo de Harvard.[^lockdown_harvard]

[^lockdown_harvard]: «Absent other interventions, a key metric for the success of social distancing is whether critical care capacities are exceeded. To avoid this, prolonged or intermittent social distancing may be necessary into 2022». [Kissler y Tedijanto et al](https://science.sciencemag.org/content/early/2020/04/14/science.abb5793)

**Aquí tienes una simulación:** (Después de jugar con el "escenario grabado" ¡puedes intentar crear tu *propio* calendario de confinamiento, usando las barras de ajustes *mientras* se ejecuta la simulación! Recuerda que puedes detener y continuar la simulación, y cambiar su velocidad).

<div class="sim">
		<iframe src="sim?stage=int-4&format=lines" width="800" height="540"></iframe>
</div>

¡Esto *mantendría* los casos por debajo de la capacidad de las UCIs! Y hasta que llegue la vacuna es *mucho* mejor que el confinamiento total. Solo tenemos que... cerrar durante unos meses, abrir durante unos meses y repetir hasta que la vacuna esté disponible. (Y si no hay vacuna, repetir hasta que se alcance la inmunidad de grupo... en 2022).

Veamos, está bien dibujar una línea diciendo «capacidad UCIs», pero hay un montón de cosas importantes que *no podemos* simular aquí. Como:

**Salud mental:** La soledad es uno de los factores de riesgo más importantes de la depresión, la ansiedad y el suicidio. Y está asociada a una muerte temprana equivalente a la de fumar 15 cigarrillos diarios.[^loneliness]

[^loneliness]: Ver [Figura 6 de Holt-Lunstad & Smith 2010](https://journals.sagepub.com/doi/abs/10.1177/1745691614568352). Por supuesto, hay que advertir que lo que encontraron fue una *correlación*. Pero a menos que quieras incomunicar a una selección aleatoria de personas de por vida, la evidencia observacional es lo único que vamos a tener.

**Salud financiera:** «Qué pasa con la economía» suena a que te preocupa más el dinero que las vidas, pero «la economía» no son solo las acciones: es la posibilidad de las personas para proveer comida y protección a sus seres queridos, para invertir en el futuro de sus hijos, y disfrutar del arte, la gastronomía, los videojuegos – las cosas que hacen que valga la pena vivir. Eso sin contar que la pobreza *en sí misma* tiene un impacto terrible en la saludad física y mental.

¡No estamos diciendo que no haya que confinarse! Más tarde veremos los "cortocircuitos" de confinamientos. Aún así, no son la solución ideal.

Pero espera... ¿Taiwan y Corea del Sur no han contenido *ya* la COVID-19? ¿Durante cuatro meses completos, *sin* confinamientos duraderos?

¿Cómo?

###Escenario 4: Probar, Rastrear, Aislar

*«Por supuesto, *podríamos* haber hecho como Taiwán y Corea del Sur al inicio, pero ahora ya es muy tarde. Desaprovechamos el comienzo».*

¡Pero es eso exactamente! «El confinamiento no es una cura, es solo un reinicio»... **y un reinicio es justo lo que necesitamos.**

Para comprender cómo Taiwán y Corea del Sur han contenido la COVID-19, necesitamos comprender la cronología de una infección típica de la COVID-19[^timeline]:

[^timeline]: **3 días de media de contagiosidad:** «Assuming an incubation period distribution of mean 5.2 days from a separate study of early COVID-19 cases, we inferred that infectiousness started from 2.3 days (95% CI, 0.8–3.0 days) before symptom onset» (traducción: Asumiendo que los síntomas comienzan a los 5 días, la contagiosidad comienza 2 días antes = La contagiosidad comienza a los 3 días) [He, X., Lau, E.H.Y., Wu, P. et al.](https://www.nature.com/articles/s41591-020-0869-5)  
    
    **4 días en promedio para contagiar a alguien más:** “The mean [serial] interval was 3.96 days (95% CI 3.53–4.39 days)” [Du Z, Xu X, Wu Y, Wang L, Cowling BJ, Ancel Meyers L](https://wwwnc.cdc.gov/eid/article/26/6/20-0357_article)
    
    **5 días en promedio para sentir síntomas:** «The median incubation period was estimated to be 5.1 days (95% CI, 4.5 to 5.8 days)» [Lauer SA, Grantz KH, Bi Q, et al](https://annals.org/AIM/FULLARTICLE/2762808/INCUBATION-PERIOD-CORONAVIRUS-DISEASE-2019-COVID-19-FROM-PUBLICLY-REPORTED)

![](pics/timeline1.png)

Si los casos solo se auto-aíslan cuando se ponen enfermos (esto es, cuando sienten los síntomas), el virus se puede contagiar:

![](pics/timeline2.png)

Y, de hecho, el 44% de todos los contagios son así: *pre*-sintomáticos! [^pre_symp]

[^pre_symp]: «We estimated that 44% (95% confidence interval, 25–69%) of secondary cases were infected during the index cases’ presymptomatic stage» [He, X., Lau, E.H.Y., Wu, P. et al](https://www.nature.com/articles/s41591-020-0869-5)

Pero, si encontramos *y ponemos en cuarentena* a los casos sintomáticos y a sus contactos cercanos... ¡detenemos el contagio, al adelantarnos!

![](pics/timeline3.png)

Esto se denomina **rastreo de contactos**. Es una vieja idea, que se usó a un nivel sin precedentes para contener el ébola[^ebola], ¡y ahora es el núcleo de la estrategia de contención de la COVID-10 de Taiwán y Corea del Sur!

[^ebola]: «Contact tracing was a critical intervention in Liberia and represented one of the largest contact tracing efforts during an epidemic in history.» [Swanson KC, Altare C, Wesseh CS, et al.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6152989/)

(También nos permite usar la limitada capacidad de hacer pruebas de forma más eficiente, para encontrar a las <icon i></icon>s pre-sintomáticas sin la necesidad de hacer pruebas a todo el mundo).

Tradicionalmente, los contactos se identifican mediante entrevistas personales, pero esas *por si solas* son muy lentas para la ventana de ~48 horas de la COVID-19. Por eso los rastreadores de contactos necesitan ayuda, y soporte – *NO* ser reemplazados por – las aplicaciones de rastreo de contactos.

(Esta idea no la tuvieron los «tecnólogos»: el uso de una aplicación para ayudar a combatir la COVID-19 fue propuesta por primera vez por [un equipo de epidemiólogos de Oxford](https://science.sciencemag.org/content/early/2020/04/09/science.abb6936)).

Un momento, ¿aplicaciones que registran con quién has estado en contacto?... ¿Significa eso que tenemos que renunciar a la privacidad y dársela a un Gran Hermano?

¡Diantres, no! **[DP-3T](https://github.com/DP-3T/documents#decentralized-privacy-preserving-proximity-tracing)**, un equipo de epidemiólogos y criptógrafos (incluyendo uno de nosotros, Marcel Salathé) *ya* está desarrollando una aplicación para rastrear contactos  – su código es público – que **no revela información sobre tu identidad, posición, quiénes son tus contactos o incluso *cuántos* contactos has tenido.**

Aquí se ve cómo funciona:

![](pics/dp3t.png)

(y [aquí el cómico completo](https://ncase.me/contact-tracing/))

Junto a otros equipos similares como Protocolo TCN [^tcn] y MIT PACT[^pact], han inspirado a Apple y Google para incluir el rastreo de contactos privado directamente en Android e iOS.[^gapple] (¿No se fía de Google/Apple? ¡Bien! Es lo bueno de este sistema, ¡que no *necesita* confianza!). En breve, su administración de salud pública local le puede solicitar que se descargue una aplicación. Si tiene como prioridad la privacidad y la disponibilidad de código, ¡por favor, hágalo!

[^tcn]: [Temporary Contact Numbers, a decentralized, privacy-first contact tracing protocol](https://github.com/TCNCoalition/TCN#tcn-protocol)

[^pact]: [PACT: Private Automated Contact Tracing](https://pact.mit.edu/)

[^gapple]: [Apple and Google partner on COVID-19 contact tracing technology](https://www.apple.com/ca/newsroom/2020/04/apple-and-google-partner-on-covid-19-contact-tracing-technology/). Tenga en cuenta que no están desarrollando las aplicaciones *ellos mismos*, solo creando los sistemas que darán *soporte* a dichas aplicaciones.

Pero ¿qué pasa con las personas que no tienen teléfonos inteligentes? ¿O con los contagios a través de las puertas? ¿O con los casos "realmente" asintomáticos? Las aplicaciones de rastreo de contactos no pueden identificar todas las infecciones... y *¡no hay problema con eso!* No tenemos necesidad de identificar *todos* los contagios, solo ese más de 60% necestario para que R < 1.

(Diatraba sobre la confusión entre pre-sintomáticos y asintomáticos «reales». Los asintomáticos «reales» son muy pocos:[^rant])

[^rant]: Hay muchas noticias  – y, sinceramente, muchos artículos científicos – que no distinguen entre «casos que no han mostrado síntomas cuando les hicimos la prueba» (pre-sintomáticos) y «casos que *nunca* mostraron síntomas» (asintomáticos reales). La única manera de notar la diferencia es mediante un seguimiento de los casos.
   
    Que es justo lo que hizo [este estudio](https://wwwnc.cdc.gov/eid/article/26/8/20-1274_article). (Aviso: «La publicación temprana de artículos no está considerada como versión final».) En un centro de llamadas en Corea del Sur donde hubo un brote de la COVID-19, «solo cuatro personas (1.9%) se mantuvieron asintomáticos durante los 14 días de la cuarentena, y ninguno de los contactos en sus hogares sufrieron infecciones secundarias».
    
    Esto significa que los «asintomáticos reales» son pocos, e infectarse con la enfermedad a través de un asintomático real ¡podría ser incluso más extraño!

El aislamiento de los casos *sintomáticos* reduciría R en un 40%, y poniendo en cuarentena a sus contactos *pre/a-sintomáticos* reduciría R hasta en un 50%[^oxford]:

[^oxford]: Del mismo estudio de Oxford que primero recomendó el uso de aplicaciones para rastrear contactos en el caso de la COVID-19: [Luca Ferretti & Chris Wymant et al](https://science.sciencemag.org/content/early/2020/04/09/science.abb6936/tab-figures-data) Véase la figura 2. Si se asume que R<sub>0</sub> = 2.0, encontraron que:    
    
    * Los casos sintomáticos contribuyen R = 0.8 (40%).
    * Los casos pre-sintomáticos contribuyen R = 0.9 (45%).
    * Los casos asintomáticos contribuyen R = 0.1 (5%, aunque su modelo tiene mucha incertidumbre y podría ser aún menos).
    * Cosas ambientales como pomos de puertas contribuyen R = 0.2 (10%)

    Y añade a los contactos pre- y a-sintomáticos (45% + 5%) y ¡ya tienes el 50% de R!

<div class="sim">
		<iframe src="sim?stage=int-4a&format=calc" width="285" height="340"></iframe>
</div>

Así que, incluso sin la cuarentena del 100% de los contactos, podemos hacer que R < 1 *¡sin confinamiento!* Mucho mejor para nuestra salud mental y financiera. (El coste de las personas que se tienen que auto-aislar o poner en cuarentena *debería ser a cargo de los gobiernos* – el pago de las pruebas, la protección del trabajo, bajas cubiertas, etc. Es mucho más barato que los confinamientos intermitentes).

Cuando mantenemos R < 1 hasta que tengamos una vacuna, lo que convierte a las <icon s></icon>s susceptibles en <icon r></icon>s inmunes. La inmunidad de grupo, de la forma *correcta*:

<div class="sim">
		<iframe src="sim?stage=int-4b&format=calc" width="285" height="230"></iframe>
</div>

(Nota: esta calculadora supone que las vacunas son 100% efectivas. Recuerda que en realidad, tendrías que compensarlo vacunando a *más* personas que las que dan la «inmunidad de grupo». para obtener *realmente* la inmunidad de grupo).

Bueno, dejemos de hablar. Aquí está la simulación de:

1. Un confinamiento de varios meses, hasta que podamos...
2. Pasar a «Probar, rastrear y aislar», hasta que podamos...
3. Vacunar a suficientes personas, lo que implica que...
4. Ganamos.

<div class="sim">
		<iframe src="sim?stage=int-5&format=lines" width="800" height="540"></iframe>
</div>

¡Ahí está! Así es como hacemos el aterrizaje de emergencia en este avión.

Así es como ganamos a la COVID-19.

...

Pero, ¿qué ocurre si *aún así* las cosas van mal? Ya han ido mal. Eso es miedo, ¡y el miedo es bueno! El miedo nos da energía para crear *planes de contingencia*.

Los pesismistas inventan los paracaídas.

###Escenario 4+: Máscarillas para todos, verano, cortocircuitos

¿Qué pasa si R<sub>0</sub> es mucho mayor de lo que pensamos, y las intervenciones anteriores, incluso con distanciamiento leve, *aún* no son suficientes para que R < 1?

Recuerde, incluso si no podemos hacer que R < 1, la reducción de R disminuye el «exceso» de casos totales, y por lo tanto salva vidas. Pero aún así, R < 1 es lo ideal, así que aquí hay otras formas de reducir R:

**Mascarillas para todos:**

*«Espera»,* podrías preguntarte, *«¿Las mascarillas no evitan que no me ponga malo?*

Cierto. Las mascarillas no impiden que enferme[^incoming]... impiden que *otras* personas enfermen.

[^incoming]: «None of these surgical masks exhibited adequate filter performance and facial fit characteristics to be considered respiratory protection devices». [Tara Oberg y Lisa M. Brosseau](https://www.sciencedirect.com/science/article/pii/S0196655307007742)

[^outgoing]: «The overall 3.4 fold reduction [70% reduction] in aerosol copy numbers we observed combined with a nearly complete elimination of large droplet spray demonstrated by Johnson et al. suggests that surgical masks worn by infected persons could have a clinically significant impact on transmission». [Milton DK, Fabian MP, Cowling BJ, Grantham ML, McDevitt JJ](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3591312/)

[^homemade]: [Davies, A., Thompson, K., Giri, K., Kafatos, G., Walker, J., & Bennett, A](https://www.cambridge.org/core/journals/disaster-medicine-and-public-health-preparedness/article/testing-the-efficacy-of-homemade-masks-would-they-protect-in-an-influenza-pandemic/0921A05A69A9419C862FA2F35F819D55) Véase la tabla 1: una camiseta de algodón 100% tiene 2/3 de la eficiencia de transmisión de una mascarilla quirúrgica, para los dos aerosoles que probaron.

![](pics/masks.png)

Para ponerlo en números: las mascarillas quirúrgicas *en la persona enferma* reduce la cantidad de virus de la gripe y el resfriado en los aerosoles en un 70%.[^outgoing] ¡La reducción de contagios en un 70% tendría el mismo impacto que un confinamiento!

Sin embargo, no estamos seguros del impacto de las mascarillas en la COVID-19 *en concreto*. En ciencia, solo se debe publicar un descubrimiento si se está al menos un 95% seguro de él. (...debe.[^replication]) Las mascarillas, a día 1 de mayo de 2020, están por debajo de ese «95% seguro».

[^replication]: Cualquier científico de verdad que lea la última frase estará riéndose-llorando ahora mismo. Ver: [p-hacking](https://en.wikipedia.org/wiki/Data_dredging), [la crisis de replicación](https://es.wikipedia.org/wiki/Crisis_de_replicación))

Sin embargo, las pandemias son como el póker. **Apuesta solo cuando estés seguro al 95% y terminarás perdiéndolo todo.** Como ha apuntado un reciente artículo sobre las mascarillas en el British Medical Journal,[^precautionary] *tenemos* que hacer análisis de riesgo/beneficio en la incertidumbre. Como éste:

[^precautionary]: «It is time to apply the precautionary principle» [Trisha Greenhalgh et al \[PDF\]](https://www.bmj.com/content/bmj/369/bmj.m1435.full.pdf)

Riesgo: Si alguien lleva mascarillas caseras (que son ~2/3 tan efectivas como las mascarillas quirúrgicas[^homemade]), súper baratas. Y también si hay mascarillas quirúrgicas, más caras pero aún así asequibles.

Beneficio: Incluso si hay un 50-50 de probabilidad de que las mascarillas quirúrgicas reduzcan los contagios entre un 0% y 70%, el «valor esperado» medio aún es el 35%, ¡lo mismo que la mitad de un confinamiento! Así que vamos a asumir que las mascarillas quirúrgicas reducen R en un 35%, descontando nuestra incertidumbre. (De nuevo, puedes cuestionar nuestras suposiciones cambiando los ajustes).

<div class="sim">
		<iframe src="sim?stage=int-6a&format=calc" width="285" height="380"></iframe>
</div>

(otros argumentos a favor y en contra de las mascarillas:[^mask_args])

[^mask_args]: **«Necesitamos los suministros para los hospitales».** *No hay discusión.* Pero ése es un argumento para incrementar la producción, no para su racionamiento. Mientras tanto, podemos fabricar mascarillas caseras.

   **«Son difíciles de llevar correctamente».** También es difícil lavarnos las manos suguiendo las instrucciones de la OMS – en serio, ¿!«Paso 3) palma derecha contra el dorso de la mano izquierda»?! – pero aún así recomendamos el lavado de las manos, porque lo imperfecto es mejor que nada.
   
   **«Harán que las personas sean más descuidadas con el lavado de manos y el distanciamiento social».** Claro, los cinturones de seguridad hacen que las personas ignoren las señales de stop, y la limpieza con hilo dental hace que las personas comamos rocas. En serio, opinamos todo lo contrario: las mascarillas son un *recordatorio físico constante* de ser precavidos – ¡y en el este de Asia, las mascarillas también son un símbolo de solidaridad!
    
    

Las mascarillas *por si solas* no hacen que R < 1. Pero si el lavado de manos y «Probar, rastrear, aislar» sólo nos lleva a R = 1.10, el que 1/3 de las personas lleven mascarillas hacen que R < 1, y ¡el virus está contenido!

**Verano:**

Vale, esto no es una «intervención» que podamos controlar, ¡pero será de ayuda! Algunos medios informan de que el verano no tendrá efecto con la COVID-19. Tienen solo la mitad de la razón: el verano no hará que R < 1, pero *reducirá* R.

Para la COVID-19, cada 1° Celsius (2.2° Fahrenheit) adicional hace que R disminuya un 1.2%.[^heat] La diferencia entre el verano y el invierno en la ciudad de New York es de 15°C (60°F), así que el verano reducirá R en un 18%.

[^heat]: «One-degree Celsius increase in temperature [...] lower[s] R by 0.0225» y «The average R-value of these 100 cities is 1.83”. 0.0225 ÷ 1.83 = ~1.2». [Wang, Jingyuan y Tang, Ke and Feng, Kai and Lv, Weifeng](https://papers.ssrn.com/sol3/Papers.cfm?abstract_id=3551767)

<div class="sim">
		<iframe src="sim?stage=int-6b&format=calc" width="285" height="220"></iframe>
</div>

El verano por si solo no hará que R < 1, pero si tenemos recursos limitados, podemos desescalar algunas intervenciones en el verano – para escalarlas de nuevo durante el invierno.

**A "Circuit Breaker" Lockdown:**

And if all that *still* isn't enough to get R < 1... we can do another lockdown.

But we wouldn't have to be 2-months-closed / 1-month-open over & over! Because R is reduced, we'd only need one or two more "circuit breaker" lockdowns before a vaccine is available. (Singapore had to do this recently, "despite" having controlled COVID-19 for 4 months. That's not failure: this *is* what success takes.)

Here's a simulation a "lazy case" scenario:

1. Lockdown, then
2. A moderate amount of hygiene & "Test, Trace, Isolate", with a mild amount of "Masks For All", then...
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

So now, let's plan for some *worse* worst-case scenarios. Water landing, get your life jacket, and please follow the lights to the emergency exits:

<div class="section chapter">
    <div>
		<img src="banners/curve.png" height=480 style="position: absolute;"/>
        <div>The Next Few Years</div>
    </div>
</div>

You get COVID-19, and recover. Or you get the COVID-19 vaccine. Either way, you're now immune...

...*for how long?*

* COVID-19 is most closely related to SARS, which gave its survivors 2 years of immunity.[^SARS immunity]
* The coronaviruses that cause "the" common cold give you 8 months of immunity.[^cold immunity]
* There's reports of folks recovering from COVID-19, then testing positive again, but it's unclear if these are false positives.[^unclear]
* One *not-yet-peer-reviewed* study on monkeys showed immunity to the COVID-19 coronavirus for at least 28 days.[^monkeys]

But for COVID-19 *in humans*, as of May 1st 2020, "how long" is the big unknown.

[^SARS immunity]: “SARS-specific antibodies were maintained for an average of 2 years [...] Thus, SARS patients might be susceptible to reinfection ≥3 years after initial exposure.” [Wu LP, Wang NC, Chang YH, et al.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2851497/) "Sadly" we'll never know how long SARS immunity would have really lasted, since we eradicated it so quickly.

[^cold immunity]: “We found no significant difference between the probability of testing positive at least once and the probability of a recurrence for the beta-coronaviruses HKU1 and OC43 at 34 weeks after enrollment/first infection.” [Marta Galanti & Jeffrey Shaman (PDF)](http://www.columbia.edu/~jls106/galanti_shaman_ms_supp.pdf)

[^unclear]: “Once a person fights off a virus, viral particles tend to linger for some time. These cannot cause infections, but they can trigger a positive test.” [from STAT News by Andrew Joseph](https://www.statnews.com/2020/04/20/everything-we-know-about-coronavirus-immunity-and-antibodies-and-plenty-we-still-dont/)

[^monkeys]: From [Bao et al.](https://www.biorxiv.org/content/10.1101/2020.03.13.990226v1.abstract) *Disclaimer: This article is a preprint and has not been certified by peer review (yet).* Also, to emphasize: they only tested re-infection 28 days later. 

For these simulations, let's say it's 1 year.
**Here's a simulation starting with 100% <icon r></icon>**, exponentially decaying into susceptible, no-immunity <icon s></icon>s after 1 year, on *average*, with variation:

<div class="sim">
		<iframe src="sim?stage=yrs-1&format=lines&height=600" width="800" height="600"></iframe>
</div>

Return of the exponential decay!

This is the **SEIRS Model**. The final "S" stands for <icon s></icon> Susceptible, again.

![](pics/seirs.png)

Now, let's simulate a COVID-19 outbreak, over 10 years, with no interventions... *if immunity only lasts a year:*

<div class="sim">
		<iframe src="sim?stage=yrs-2&format=lines&height=600" width="800" height="600"></iframe>
</div>

In previous simulations, we only had *one* ICU-overwhelming spike. Now, we have several, *and* <icon i></icon> cases come to a rest *permanently at* ICU capacity. (Which, remember, we *tripled* for these simulations)

R = 1, it's **endemic.**

Thankfully, because summer reduces R, it'll make the situation better:

<div class="sim">
		<iframe src="sim?stage=yrs-3&format=lines&height=640" width="800" height="640"></iframe>
</div>

Oh.

Counterintuitively, summer makes the spikes worse *and* regular! This is because summer reduces new <icon i></icon>s, but that in turn reduces new immune <icon r></icon>s. Which means immunity plummets in the summer, *creating* large regular spikes in the winter.

Thankfully, the solution to this is pretty straightforward – just vaccinate people every fall/winter, like we do with flu shots:

**(After playing the recording, try simulating your own vaccination campaigns! Remember you can pause/continue the sim at any time)**

<div class="sim">
		<iframe src="sim?stage=yrs-4&format=lines" width="800" height="540"></iframe>
</div>

But here's the scarier question:

What if there's no vaccine for *years*? Or *ever?*

**To be clear: this is unlikely.** Most epidemiologists expect a vaccine in 1 to 2 years. Sure, there's never been a vaccine for any of the other coronaviruses before, but that's because SARS was eradicated quickly, and "the" common cold wasn't worth the investment. 

Still, infectious disease researchers have expressed worries: What if we can't make enough?[^vax_enough] What if we rush it, and it's not safe?[^vax_safe]

[^vax_enough]: “If a coronavirus vaccine arrives, can the world make enough?” [by Roxanne Khamsi, on Nature](https://www.nature.com/articles/d41586-020-01063-8)

[^vax_safe]: “Don’t rush to deploy COVID-19 vaccines and drugs without sufficient safety guarantees” [by Shibo Jiang, on Nature](https://www.nature.com/articles/d41586-020-00751-9)

Even in the nightmare "no-vaccine" scenario, we still have 3 ways out. From most to least terrible:

1) Do intermittent or loose R < 1 interventions, to reach "natural herd immunity". (Warning: this will result in many deaths & damaged lungs. *And* won't work if immunity doesn't last.)

2) Do the R < 1 interventions forever. Contact tracing & wearing masks just becomes a new norm in the post-COVID-19 world, like how STI tests & wearing condoms became a new norm in the post-HIV world.

3) Do the R < 1 interventions until we develop treatments that make COVID-19 way, way less likely to need critical care. (Which we should be doing *anyway!*) Reducing ICU use by 10x is the same as increasing our ICU capacity by 10x:

**Here's a simulation of *no* lasting immunity, *no* vaccine, and not even any interventions – just slowly increasing capacity to survive the long-term spikes:**

<div class="sim">
		<iframe src="sim?stage=yrs-5&format=lines" width="800" height="540"></iframe>
</div>

Even under the *worst* worst-case scenario... life perseveres.

. . .

Maybe you'd like to challenge our assumptions, and try different R<sub>0</sub>'s or numbers. Or try simulating your *own* combination of intervention plans!

**Here's an (optional) Sandbox Mode, with *everything* available. (scroll to see all controls) Simulate & play around to your heart's content:**

<div class="sim">
		<iframe src="sim?stage=SB&format=sb" width="800" height="540"></iframe>
</div>

This basic "epidemic flight simulator" has taught us so much. It's let us answer questions about the past few months, next few months, and next few years.

So finally, let's return to...

<div class="section chapter">
    <div>
		<img src="banners/curve.png" height=480 style="position: absolute;"/>
        <div>The Now</div>
    </div>
</div>

Plane's sunk. We've scrambled onto the life rafts. It's time to find dry land.[^dry_land]

[^dry_land]: Dry land metaphor [from Marc Lipsitch & Yonatan Grad, on STAT News](https://www.statnews.com/2020/04/01/navigating-covid-19-pandemic/)

Teams of epidemiologists and policymakers ([left](https://www.americanprogress.org/issues/healthcare/news/2020/04/03/482613/national-state-plan-end-coronavirus-crisis/), [right](https://www.aei.org/research-products/report/national-coronavirus-response-a-road-map-to-reopening/ ), and [multi-partisan](https://ethics.harvard.edu/covid-roadmap)) have come to a consensus on how to beat COVID-19, while protecting our lives *and* liberties.

Here's the rough idea, with some (less-consensus) backup plans:

![](pics/plan.png)

So what does this mean for YOU, right now?

**For everyone:** Respect the lockdown so we can get out of Phase I asap. Keep washing those hands. Make your own masks. Download a *privacy-protecting* contact tracing app when those are available next month. Stay healthy, physically & mentally! And write your local policymaker to get off their butt and...

**For policymakers:** Make laws to support folks who have to self-isolate/quarantine. Hire more manual contact tracers, *supported* by privacy-protecting contact tracing apps. Direct more funds into the stuff we should be building, like...

**For builders:** Build tests. Build ventilators. Build personal protective equipment for hospitals. Build tests. Build masks. Build apps. Build antivirals, prophylactics, and other treatments that aren't vaccines. Build vaccines. Build tests. Build tests. Build tests. Build hope. 

Don't downplay fear to build up hope. Our fear should *team up* with our hope, like the inventors of airplanes & parachutes. Preparing for horrible futures is how we *create* a hopeful future.

The only thing to fear is the idea that the only thing to fear is fear itself.