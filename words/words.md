<div class="section">
    <div>
    	<iframe id="splash" width="960" height="480" src="banners/splash.html"></iframe>
        <div style="top: 70px;font-size: 75px;font-weight: bold;">
        	¿Qué pasará ahora?
       	</div>
		<div style="font-weight: 500;top: 140px;left: 10px;font-size: 29px;">
			Los futuros de la COVID-19 explicados con simulaciones
		</div>
		<div style="font-weight: 100;top: 189px;left: 10px;font-size: 19px;line-height: 21px;">
			<b>
				🕐 30 min lectura/juego
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

Lo de «sólo tenemos que temer al propio miedo» es un consejo estúpido.

Por supuesto, no hay que hacer acopio de papel higiénico, pero si los responsables públicos tienen miedo al miedo tenderán a minimizar los peligros reales para evitar la «histeria colectiva». El problema no es el miedo, es cómo *canalizamos* nuestro miedo. El miedo nos da fuerzas para enfrentarnos a los peligros actuales y prepararnos para los futuros.

Sinceramente, nosotros (Marcel, epidemiólogo + Nicky, arte/código) estamos preocupados. ¡Y pensamos que tú también lo estarás! Por eso hemos canalizado nuestro miedo haciendo estas **simulaciones interactivas**, para que *tú* canalices tu miedo en comprensión:

* **Los últimos meses** (introducción a la epidemiología, modelo SEIR, R y R<sub>0</sub>).
* **Los próximos meses** (confinamientos, rastreo de contactos, mascarillas).
* **Los próximos años** (¿pérdida de inmunidad? ¿ausencia de vacunas?).

El objetivo de esta guía (publicada el 1 de mayo de 2020, haz clic en esta nota al pie de página→[^timestamp]) es darte esperanza *y* miedo. Para ganar a la COVID-19 **de una forma que también proteja nuestra salud mental y financiera**, necesitamos optimismo para crear planes, y pesimismo para crear planes de contingencia. Como Gladys Bronwyn Stern dijo una vez: *«El optimismo inventa el avión y el pesimismo, el paracaídas».*

[^timestamp]: Estas notas al pie de página mostrarán fuentes, enlaces y comentarios extra. ¡Como este comentario!
    
    **Esta guía se publicó el 1 de mayo de 2020.** Muchos de los detalles caducarán eventualmente, pero estamos seguros de que la guía cubre el 95% de los futuros posibles, y que la introducción a la epidemiología será un recurso útil que perdurará.

Abróchate el cinturón: vamos a sufrir algunas turbulencias.

<div class="section chapter">
    <div>
		<img src="banners/curve.png" height=480 style="position: absolute;"/>
        <div>Los próximos meses</div>
    </div>
</div>

Los pilotos usan simuladores de vuelo para aprender cómo evitar que los aviones se estrellen.

**Los epidemiólogos usan simuladores para aprender cómo evitar que la humanidad se estrelle.**

Así que, venga, ¡hagamos un «simulador de vuelo de epidemias» muy, *muy* simple! En esta simulación, las personas <icon i></icon> Infecciosas pueden convertir a las personas <icon s></icon> Susceptibles en aún más personas <icon i></icon> Infecciosas:

![](pics/es_ES/spread.png)

Se estima que, *al comienzo* de un brote de la COVID-19, el virus salta de una <icon i></icon> a una <icon s></icon> cada 4 días, *en promedio*.[^serial_interval] (Recuerde, hay mucha variabilidad).

[^serial_interval]: «The mean [serial] interval was 3.96 days (95% CI 3.53–4.39 days)». [Du Z, Xu X, Wu Y, Wang L, Cowling BJ, Ancel Meyers L](https://wwwnc.cdc.gov/eid/article/26/6/20-0357_article) (Aviso: La publicación temprana de estos artículos no están consideradas como versiones finales)

Si simulamos que se «doble cada cada 4 días» *y nada más*, en una población que al comienzo sólo tiene 0.001% <icon i></icon>, ¿qué pasa?

**¡Haga clic al botón «Iniciar» para comenzar la simulación! Podrás reiniciarla luego con diferentes ajustes:** (consideración técnica: [^caveats])

[^caveats]: **Recuerda: todas estas simulaciones están muy simplificadas por motivos didácticos.**
    
    Una simplificación: cuando le dices a la simulación «infecta a 1 persona cada X días», en realidad se está incrementando el número de infectados en 1/X cada día. Lo mismo para los ajustes futuros en estas simulaciones –«recuperados cada X días» en realidad reduce el número de infectados en 1/X por día.
    
    En realidad, *no son* exactamente lo mismo, pero se aproximan lo suficiente y para propósitos didácticos es menos opaco que ajustar las tasas de transmisión y recuperación directamente.

<div class="sim">
		<iframe src="sim?stage=epi-1" width="800" height="540"></iframe>
</div>

Esta es la **curva de crecimiento exponencial.** Comienza plana y en determinado momento explota. De «ah, es cómo la gripe» a «ah claro, la gripe no crea *fosas comunes en ciudades desarrolladas*».

![](pics/es_ES/exponential.png)

Pero esta simulación no es correcta. El crecimiento exponencial, afortunadamente, no puede continuar indefinidamente. Una cosa que detiene el contagio es cuando *ya hay* personas que tienen el virus:

![](pics/es_ES/susceptibles.png)

Cuantas más <icon i></icon>s haya, más rápido las <icon s></icon>s se vuelven <icon i></icon>s, **pero cuantas menos <icon s></icon>s haya, más *lento* la <icon s></icon>s se convertirán en <icon i></icon>s.**

¿Cómo cambia ésto el crecimiento de la epidemia? Vamos a comprobarlo:

<div class="sim">
		<iframe src="sim?stage=epi-2" width="800" height="540"></iframe>
</div>

Esta es la **curva de crecimiento logística** con forma de S. Comienza plana, luego explota y luego se aplana otra vez.

Pero. Esta simulación *todavía* no es correcta. No estamos teniendo en cuenta que las personas <icon i></icon> Infecciosas dejan de serlo en determinado momento, ya sea porque 1) se recuperan, 2) se «recuperan» con daños pulmonares, o 3) se mueren.

Para simplificar la cuestión, vamos a asumir que todas las personas <icon i></icon> Infecciosas pasan a <icon r></icon> Recuperadas. (Pero recuerda que en realidad algunas fallecen). Las <icon r></icon>s no pueden infectarse de nuevo, y vamos a asumir –*¡por ahora!*– que serán inmunes el resto de sus vidas.

Con la COVID-19, se estima que eres <icon i></icon> Infeccioso durante 10 días, *en promedio*.[^infectiousness] Eso significa que algunas personas se recuperan antes de 10 días y otras después. **Aquí se ve como es éso, con una simulación que *comienza* con un 100% de <icon i></icon>:**

[^infectiousness]: «The median communicable period \[...\] was 9.5 days». [Hu, Z., Song, C., Xu, C. et al](https://link.springer.com/article/10.1007/s11427-020-1661-4) Sí, sabemos que la «mediana» no es lo mismo que la «media». Pero para propósitos educativos, se parecen bastante.

<div class="sim">
		<iframe src="sim?stage=epi-3" width="800" height="540"></iframe>
</div>

Esto es lo contrario de un crecimiento exponencial, la **curva de decaimiento exponencial.**

Y ahora, ¿qué pasa si simulas un crecimiento logístico con forma de S *con* recuperación?

![](pics/es_ES/graphs_q.png)

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

![](pics/es_ES/sir.png)

**NOTA: Las simulaciones usadas en la toma de decisiones públicas son mucho, *mucho* más sofisticadas que ésta!** Pero el modelo SIR puede explicar los mismos fenómenos generales, aún sin todos sus matices.

Bueno, vamos a añadir otro matiz más: antes de que <icon s></icon> se convierta en <icon i></icon>, antes se convierten en personas <icon e></icon> Expuestas. Esto pasa cuando tienen el virus pero aún no pueden transmitirlo –infec*tadas* pero todavía no son infec*ciosas*.

![](pics/es_ES/seir.png)

(Esta variante es el denominado **modelo SEIR**[^seir], donde «E» son las personas <icon e></icon> «Expuestas». Ten en cuenta que este *no es* el significado habitual de «expuesto», cuando podrías tener o no el virus. En esta definición técnica, «Expuesto» significa que lo tienes con seguridad. La terminología científica es mala).

[^seir]: Para más explicaciones técnicas del modelo SEIR, consultar [Institute for Disease Modeling](https://www.idmod.org/docs/hiv/model-seir.html) and [Wikipedia](https://es.wikipedia.org/wiki/Modelaje_matemático_de_epidemias#Modelo_SEIR)

Para la COVID-19, se estima que las personas son <icon e></icon> infectadas-pero-aún-no-infecciosas durante 3 días, *de promedio*.[^latent] ¿Qué pasa si añadimos eso a la simulación?

[^latent]: «Assuming an incubation period distribution of mean 5.2 days from a separate study of early COVID-19 cases, we inferred that infectiousness started from 2.3 days (95% CI, 0.8–3.0 days) before symptom onset». (Traducción: Si asumimos que los síntomas comienzan a los 5 días, la fase infecciosa comienza 2 días antes = la contagiosidad comienza a los 3 días) [He, X., Lau, E.H.Y., Wu, P. et al.](https://www.nature.com/articles/s41591-020-0869-5)

La <b style='color:#ff4040'>curva roja <b style='color:#FF9393'>+ rosa</b></b> son casos *actuales* (infecciosos <icon i></icon> + expuestos <icon e></icon>),    
La <b style='color:#888'>curva gris</b> son casos *totales* (actuales + recuperados <icon r></icon>):

<div class="sim">
		<iframe src="sim?stage=epi-5" width="800" height="540"></iframe>
</div>

¡Sin grandes cambios! El tiempo en el que se está <icon e></icon> Expuesto cambia con la relación de <icon e></icon>-a-<icon i></icon> y el *momento* en el que ocurre el pico de casos actuales... pero la *altura* del pico y el total de casos no cambian.

¿Por qué? Por la *primera* y más importante idea de la Introducción a la Epidemiología:

![](pics/es_ES/r.png)

Abreviación de «número reproductivo». Es el número de personas *promedio* a las que una <icon i></icon> contagia *antes* de recuperarse (o fallecer).

![](pics/es_ES/r2.png)

**R** cambia durante el transcurso de una epidemia, según se obtiene más inmunidad y se realizan más intervenciones.

**R<sub>0</sub>** es el número R *al comienzo de un brote, antes de la inmunidad o las intervenciones*. R<sub>0</sub> refleja sobre todo el poder del propio virus, aunque cambia de un lugar a otro. Por ejemplo, R<sub>0</sub> es mayor en ciudades de gran densidad que en las áreas rurales y dispersas.

(La mayoría de los artículos periodísticos –¡incluso algunos artículos científicos!– confunden R y R<sub>0</sub>. De nuevo, la terminología científica es mala).

El R<sub>0</sub> para «la» gripe estacional es de 1.28[^r0_flu]. Esto implica que, al *comienzo* de la epidemia, cada <icon i></icon> contagia a otras 1.28 *de media.* (Si le parece extraño que no sea un número entero recuerde que una madre «promedio» tiene 2.4 hijos. Lo que no significa que tengan a medio bebé gateando a su alrededor).

[^r0_flu]: «The median R value for seasonal influenza was 1.28 (IQR: 1.19–1.37)» [Biggerstaff, M., Cauchemez, S., Reed, C. et al.](https://bmcinfectdis.biomedcentral.com/articles/10.1186/1471-2334-14-480)

El R<sub>0</sub> para la COVID-19 se estima en 2.2,[^r0_covid] aunque un estudio *aún-no-finalizado* lo estima en 5.7(!) en Wuhan.[^r0_wuhan]

[^r0_covid]: «We estimated the basic reproduction number R0 of 2019-nCoV to be around 2.2 (90% high density interval: 1.4–3.8)» [Riou J, Althaus CL.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7001239/)

[^r0_wuhan]: «we calculated a median R0 value of 5.7 (95% CI 3.8–8.9)» [Sanche S, Lin YT, Xu C, Romero-Severson E, Hengartner N, Ke R.](https://wwwnc.cdc.gov/eid/article/26/7/20-0282_article)

En nuestras simulaciones –*al inicio y de media*– una <icon i></icon> infecta a alguien cada 4 días, durante 10 días. «4 días» pasan a ser «10 días» dos veces y media. Esto significa que –*al incio y de media*– cada <icon i></icon> contagia a otras 2.5 personas. Por tanto, R<sub>0</sub> = 2.5. (matizaciones:[^r0_caveats_sim])

[^r0_caveats_sim]: Esto asume que una persona es igual de contagiosa durante todo el periodo infeccioso. De nuevo, es una simplificación en aras de la didáctica.

**Juegue con esta calculadora de R<sub>0</sub>, para ver como R<sub>0</sub> depende del tiempo de recuperación y del tiempo de nuevo contagio:**

<div class="sim">
		<iframe src="sim?stage=epi-6a&format=calc" width="285" height="255"></iframe>
</div>

Pero recuerde, cuantas menos personas <icon s></icon>s haya, más *lentamente* se convertirán las <icon s></icon>s en <icon i></icon>s. El número de reproducción *actual* (R) depende no sólo del número de reproducción *básico* (R<sub>0</sub>), sino *también* de cuantas personas ya no sean <icon s></icon> Susceptibles. (Por ejemplo, debido a la recuperación y obteniendo inmunidad natural).

<div class="sim">
		<iframe src="sim?stage=epi-6b&format=calc" width="285" height="390"></iframe>
</div>

Cuando haya un número suficiente de personas con inmunidad, R < 1, y el virus esté contenido, eso se llama **inmunidad de grupo**. Para la gripe la inmunidad de grupo se consigue *con una vacuna*. Intentar alcanzar la «inmunidad de grupo natural» dejando que las personas se contagien es una idea *horrible*. (¡Pero no por la razón que quizás estás pensando! Luego lo explicamos).

Ahora, juguemos con el modelo SEIR otra vez, pero mostrando R<sub>0</sub>, R en el tiempo y el umbral de la inmunidad de grupo:

<div class="sim">
		<iframe src="sim?stage=epi-7" width="800" height="540"></iframe>
</div>

**NOTA: ¡Los casos totales *no se detienen* al llegar a la inmunidad de grupo, sino que lo exceden!** Y cruza el umbral *exactamente* cuando se llega al pico de casos actuales. (Eso ocurre cualesquiera que sean los ajustes –¡inténtalo tú mismo!)

Esto pasa porque cuando hay más no-<icon s></icon>s que el umbral de inmunidad de grupo, tenemos R < 1. Y cuando R < 1, el número de nuevos casos deja de crecer: un pico.

**Si sólo hubiera una lección que llevarse de esta guía, es ésta** –es un diagrama extremadamente complejo así que, por favor, tómate tu tiempo para comprenderlo en su totalidad:

![](pics/es_ES/r3.png)

**Esto significa: ¡NO necesitamos detener todos los contagios, o casi todos los contagios, para detener a la COVID-19!**

Es una paradoja. La COVID-19 es extremadamente contagiosa, pero para contenerla, «sólo» necesitamos evitar al menos el 60% de las infecciones. ¿¡El 60%!? Si fuera una nota de la escuela, sería un 6. Pero si R<sub>0</sub> = 2.5, disminuir eso un 61% nos da R = 0.975, que es R < 1, ¡el virus está contenido! (Fórmula exacta:[^exact_formula]).

[^exact_formula]: Recuerda R = R<sub>0</sub> * la tasa de contagios aún permitidos. Recuerda también que la tasa de contagios permitidos = 1 - tasa de contagios *evitados*.
    
    Por tanto, para llegar a R < 1, tienes que conseguir que R<sub>0</sub> * ContagiosPermitidos < 1. 
    
    Por tanto, ContagiosPermitidos < 1/R<sub>0</sub>
    
    Por tanto, 1 - ContagiosEvitados < 1/R<sub>0</sub>
    
    Por tanto, ContagiosEvitados > 1 - 1/R<sub>0</sub>
    
    Por tanto, ¡debes evitar más de **1 - 1/R<sub>0</sub>** de los contagios para que R < 1 y así contener el virus!

![](pics/es_ES/r4.png)

(Si crees que R<sub>0</sub> o el resto de números de nuestras simulaciones son muy pequeños/grandes, ¡es estupendo que cuestiones nuestras suposiciones! Tenemos una «zona de juegos» al final de esta guía, donde podrás indicar tus *propios* números y simular lo que ocurre con ellos).

*Todas* las intervenciones para la COVID-19 que has oído –lavado de manos, distanciamiento social/físico, confinamientos, auto-aislamiento, cuarentenas y rastreo de contactos, mascarillas, incluso la «inmunidad de grupo»– *todas* hacen exactamente lo mismo:

Hacer que R < 1.

Así que ahora vamos a usar nuestro «simulador de vuelo de epidemias» para averiguar lo siguiente: ¿Cómo hacemos que R < 1 de forma que **también proteja nuestra salud mental *y* financiera?**

Abróchense para un aterrizaje de emergencia...

<div class="section chapter">
    <div>
		<img src="banners/curve.png" height=480 style="position: absolute;"/>
        <div>Los próximos meses</div>
    </div>
</div>

...podría haber sido peor. Aquí está el universo paralelo que hemos evitado:

###Escenario 0: No hacer nada en absoluto

Alrededor de 1 de cada 20 personas contagiadas de la COVID-19 necesitan ir a una UCI (Unidad de Cuidados Intensivos).[^icu_covid] En un país desarrollado como EEUU, hay una UCI por cada 3400 personas.[^icu_us] Por tanto, EEUU puede tratar 20 de cada 3400 personas contagiadas *simultáneamente* –o el 0.6% de la población.

[^icu_covid]: [«Percentage of COVID-19 cases in the United States from February 12 to March 16, 2020 that required intensive care unit (ICU) admission, by age group»](https://www.statista.com/statistics/1105420/covid-icu-admission-rates-us-by-age-group/). Entre el 4.9% y el 11.5% de *todos* los casos de COVID-19 necesitan UCI. Si de forma optimista seleccionamos el rango inferior, eso es el 5% o 1 de cada 20. Observa que este total es específico para la estructura de edades de EEUU y será más alto en países con poblaciones más viejas y menor en países con poblaciones más jóvenes.

[^icu_us]: «Number of ICU beds = 96,596». De la [Society of Critical Care Medicine](https://sccm.org/Blog/March-2020/United-States-Resource-Availability-for-COVID-19) EEUU tiene una población de 328,200,000 en 2019. 96,596 de 328,200,000 = aproximadamente 1 de 3400. 

Incluso si *multiplicáramos* esa capacidad al 2%, aquí vemos lo que hubiese pasado *si no hubiéramos hecho nada en absoluto:*

<div class="sim">
		<iframe src="sim?stage=int-1&format=lines" width="800" height="540"></iframe>
</div>

No tiene buena pinta.

Esto es lo que [el informe del 16 de marzo del Imperial College](http://www.imperial.ac.uk/mrc-global-infectious-disease-analysis/covid-19/report-9-impact-of-npis-on-covid-19/) concluyó: sin hacer nada, nos quedamos sin UCIs libres, y se contagiaría más del 80% de la población. 
(recuerda: el total de casos *excede* la inmunidad de grupo)

Incluso si sólo el 0.5% de las personas contagiadas mueren –una suposición optimista cuando no hay más UCIs– en un país poblado como EEUU, con 300 millones de personas, el 0.5% del 80% de 300 millones = 1.2 millones de fallecidos... *SI no se hace nada.*

(Muchos medios de comunicación y medios sociales informaron de que «se contagiará el 80%» *sin* el «SI NO HACEMOS NADA». El miedo se canalizó en clics, no en comprensión. *Ay.*)

###Escenario 1: Aplanar la curva / Inmunidad de grupo

El plan de «Aplana la curva» ha sido promocionado por todas las organizaciones de sanidad pública, mientras que el plan original para la «inmunidad de grupo» del Reino Unido ha sido abucheado. Eran *el mismo plan.* Pero el Reino Unido lo comunicó mal.[^yong]

[^yong]: «He says that the actual goal is the same as that of other countries: flatten the curve by staggering the onset of infections. As a consequence, the nation may achieve herd immunity; it’s a side effect, not an aim. [...] The government’s actual coronavirus action plan, available online, doesn’t mention herd immunity at all».
    
    De un [artículo de The Atlantic por Ed Yong](https://www.theatlantic.com/health/archive/2020/03/coronavirus-pandemic-herd-immunity-uk-boris-johnson/608065/)

Sin embargo, ambos planes adolecían de un error fatal, literalmente.

Primero, veamos las dos maneras principales de «aplanar la curva»: lavado de manos y distanciamiento físico.

El incremento del lavado de manos reduce la gripe y los resfriados en los países desarrollados en ~25%[^handwashing], mientras que el confinamiento de toda la ciudad de Londres reduce los contactos en ~70%[^london]. Así que, asumamos que el lavado de manos puede reducir R *hasta* un 25%, y el distanciamiento reduce R *hasta* un 70%:

[^handwashing]: «All eight eligible studies reported that handwashing lowered risks of respiratory infection, with risk reductions ranging from 6% to 44% [pooled value 24% (95% CI 6–40%)]». En aras de la simplicidad, en estas simulaciones hemos redondeado el valor hasta el 25%. [Rabie, T. y Curtis, V.](https://onlinelibrary.wiley.com/doi/full/10.1111/j.1365-3156.2006.01568.x) Nota: tal y como este meta-análisis indica, la calidad de las medidas sobre el lavado de manos (al menos en los países desarrollados) son pésimas.

[^london]: «We found a 73% reduction in the average daily number of contacts observed per participant. This would be sufficient to reduce R0 from a value from 2.6 before the lockdown to 0.62 (0.37 - 0.89) during the lockdown». En aras de la simplicidad, para esta simulación lo hemos redondeado al 70%. [Jarvis y Zandvoort et al](https://cmmid.github.io/topics/covid19/comix-impact-of-physical-distance-measures-on-transmission-in-the-UK.html)

**Juegue con esta calculadora para ver como el % de no-<icon s></icon>, el lavado de manos y el distanciamiento reducen R:** (esta calculadora visualiza sus efectos *relativos* y esa es la razón por la que al incrementar uno *parece* que se reduce el efecto de los otros.[^log_caveat])

[^log_caveat]: La distorsión desaparecería si se mostrase a R en una escala logarítmica... pero entonces tendríamos que explicar las *escalas logarítmicas.*

<div class="sim">
		<iframe src="sim?stage=int-2a&format=calc" width="285" height="260"></iframe>
</div>

Ahora, simulemos lo que le pasa una epidemia de la COVID-19 si al inicio de marzo de 2020 hubiésemos incrementado el lavado de manos y sólo *un poco* de distanciamiento social –de tal forma que R es menor pero aún está por encima de 1:

<div class="sim">
		<iframe src="sim?stage=int-2&format=lines" width="800" height="540"></iframe>
</div>

Tres notas:

1. ¡Esto *reduce* los casos totales! **Incluso sin R < 1, la reducción de R salva vidas al reducir el 'exceso' sobre la inmunidad de grupo.** Muchas personas piensan que el «aplana la curva» esparce los casos sin reducir el número total. Esto es imposible en *ninguno* de los modelos de Introducción a la Epidemiología. Pero por culpa de las noticias muchos pensaron que eso del «más del 80% se contagiará» era inevitable, sin importar lo que hicieran. *Ay.*

2. Debido a las intervenciones adicionales, el número de casos actual tendrá el pico *antes* de que se llegue a la inmunidad de grupo. De hecho, en esta simulación, el número total de casos solo excede *un poquito* la inmunidad de grupo –¡el plan del Reino Unido!–. Y ahí, con R < 1, puedes deshacerte del resto de intervenciones y la COVID-19 se mantendrá contenida! Bueno, excepto por un problema...

3. Aún te puedes quedar sin UCIs. Durante muchos meses. (Y recuerda, *ya* hemos triplicado las UCIs para estas simulaciones).

Ese fue otro descubrimiento del informe del Imperial College del 16 de marzo, que convenció al Reino Unido de abandonar su plan original. Cualquier intento de **mitigación** (reducir R, pero R > 1) fracasará. La única forma de tener éxito es la **eliminación** (reducir R de modo que R < 1).

![](pics/es_ES/mitigation_vs_suppression.png)

Eso no es «aplana» la curva, es *despachurra* la curva. Por ejemplo, con un...

###Escenario 2: Confinamiento de varios meses

Ahora veamos lo que ocurre si *despachurramos* la curva con un confinamiento de 5 meses, reducimos <icon i></icon> a prácticamente nada y finalmente –*finalmente*– regresamos a la vida normal:

<div class="sim">
		<iframe src="sim?stage=int-3&format=lines" width="800" height="540"></iframe>
</div>

Oh.

Esta es la «segunda ola» de la que todo el mundo habla. Tan pronto como eliminamos el confinamiento, tenemos otra vez R > 1. Una simple <icon i></icon> olvidada (o <icon i></icon> importada) puede generar un brote de casos que sea tan malo como si hubiéramos hecho el escenario 0: Nada En Absoluto.

**Un confinamiento no es una cura, es un reinicio.**

Así que, ¿vamos a confinarnos una y otra vez?

###Escenario 3: Confinamiento intermitente

Esta solución se sugirió en el informe del Imperial College del 16 de marzo y posteriormente por un artículo de Harvard.[^lockdown_harvard]

[^lockdown_harvard]: «Absent other interventions, a key metric for the success of social distancing is whether critical care capacities are exceeded. To avoid this, prolonged or intermittent social distancing may be necessary into 2022». [Kissler y Tedijanto et al](https://science.sciencemag.org/content/early/2020/04/14/science.abb5793)

**Aquí tienes una simulación:** (Después de jugar con el «escenario grabado» ¡puedes intentar crear tu *propio* calendario de confinamiento, usando las barras de ajustes *mientras* se ejecuta la simulación! Recuerda que puedes detener y continuar la simulación y cambiar su velocidad).

<div class="sim">
		<iframe src="sim?stage=int-4&format=lines" width="800" height="540"></iframe>
</div>

¡Esto *mantendría* los casos por debajo de la capacidad de las UCIs! Y hasta que llegue la vacuna es *mucho* mejor que el confinamiento total. Solo tenemos que... cerrar durante unos meses, abrir durante unos meses y repetir hasta que la vacuna esté disponible. (Y si no hay vacuna, repetir hasta que se alcance la inmunidad de grupo... en 2022).

Veamos, está bien dibujar una línea diciendo «capacidad UCIs» pero hay un montón de cosas importantes que *no podemos* simular aquí. Como:

**Salud mental:** La soledad es uno de los factores de riesgo más importantes de la depresión, la ansiedad y el suicidio. Y está asociada a una muerte temprana equivalente a la de fumar 15 cigarrillos diarios.[^loneliness]

[^loneliness]: Ver [Figura 6 de Holt-Lunstad & Smith 2010](https://journals.sagepub.com/doi/abs/10.1177/1745691614568352). Por supuesto, hay que advertir que lo que encontraron fue una *correlación*. Pero a menos que quieras incomunicar a una selección aleatoria de personas de por vida, la evidencia observacional es lo único que vamos a tener.

**Salud financiera:** «Qué pasa con la economía» suena a que te preocupa más el dinero que las vidas, pero «la economía» no son sólo las acciones: es la posibilidad de que las personas provean comida y protección a sus seres queridos, de que inviertan en el futuro de sus hijos, y de que disfruten del arte, la gastronomía, los videojuegos –las cosas que hacen que valga la pena vivir. Eso sin contar con que la pobreza *en sí misma* tiene un impacto terrible en la saludad física y mental.

¡No estamos diciendo que no haya que confinarse! Más tarde veremos los confinamientos «cortacircuitos». Aún así, no son la solución ideal.

Pero espera... ¿Taiwan y Corea del Sur no han contenido *ya* la COVID-19? ¿Durante cuatro meses completos y *sin* confinamientos duraderos?

¿Cómo?

###Escenario 4: Probar, Rastrear, Aislar

*«Por supuesto, *podríamos* haber hecho como Taiwán y Corea del Sur al inicio, pero ahora ya es muy tarde. Desaprovechamos el comienzo».*

¡Pero es eso exactamente! «El confinamiento no es una cura, es solo un reinicio»... **y un reinicio es justo lo que necesitamos.**

Para comprender cómo Taiwán y Corea del Sur han contenido la COVID-19, necesitamos comprender la cronología de una infección típica de la COVID-19[^timeline]:

[^timeline]: **3 días en promedio de contagiosidad:** «Assuming an incubation period distribution of mean 5.2 days from a separate study of early COVID-19 cases, we inferred that infectiousness started from 2.3 days (95% CI, 0.8–3.0 days) before symptom onset» (traducción: Asumiendo que los síntomas comienzan a los 5 días, la contagiosidad comienza 2 días antes = La contagiosidad comienza a los 3 días) [He, X., Lau, E.H.Y., Wu, P. et al.](https://www.nature.com/articles/s41591-020-0869-5)  
    
    **4 días en promedio para contagiar a alguien más:** “The mean [serial] interval was 3.96 days (95% CI 3.53–4.39 days)” [Du Z, Xu X, Wu Y, Wang L, Cowling BJ, Ancel Meyers L](https://wwwnc.cdc.gov/eid/article/26/6/20-0357_article)
    
    **5 días en promedio para sentir síntomas:** «The median incubation period was estimated to be 5.1 days (95% CI, 4.5 to 5.8 days)» [Lauer SA, Grantz KH, Bi Q, et al](https://annals.org/AIM/FULLARTICLE/2762808/INCUBATION-PERIOD-CORONAVIRUS-DISEASE-2019-COVID-19-FROM-PUBLICLY-REPORTED)

![](pics/es_ES/timeline1.png)

Si los casos solamente se auto-aíslan cuando se ponen enfermos (esto es, cuando sienten los síntomas), el virus se puede contagiar:

![](pics/es_ES/timeline2.png)

Y, de hecho, el 44% de todos los contagios son así: ¡*pre*-sintomáticos! [^pre_symp]

[^pre_symp]: «We estimated that 44% (95% confidence interval, 25–69%) of secondary cases were infected during the index cases’ presymptomatic stage» [He, X., Lau, E.H.Y., Wu, P. et al](https://www.nature.com/articles/s41591-020-0869-5)

Pero, si encontramos *y ponemos en cuarentena* a los casos sintomáticos y a sus contactos cercanos... ¡detenemos el contagio, al adelantarnos!

![](pics/es_ES/timeline3.png)

Esto se denomina **rastreo de contactos**. Es una vieja idea, que se usó a una escala sin precedentes para contener el ébola[^ebola], ¡y ahora es el núcleo central de la estrategia de contención de la COVID-10 de Taiwán y Corea del Sur!

[^ebola]: «Contact tracing was a critical intervention in Liberia and represented one of the largest contact tracing efforts during an epidemic in history.» [Swanson KC, Altare C, Wesseh CS, et al.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6152989/)

(También nos permite usar la limitada capacidad para hacer pruebas de manera más eficiente, para encontrar a las <icon i></icon>s pre-sintomáticas sin la necesidad de hacer pruebas a todo el mundo).

Tradicionalmente, los contactos se identifican mediante entrevistas personales, pero esas *por si solas* son muy lentas para la ventana de ~48 horas de la COVID-19. Por eso los rastreadores de contactos necesitan ayuda, y soporte de –*NO* ser reemplazados por– aplicaciones de rastreo de contactos.

(Esta idea no la tuvieron los amantes de la tecnología: el uso de una aplicación para ayudar a combatir la COVID-19 fue propuesta por primera vez por [un equipo de epidemiólogos de Oxford](https://science.sciencemag.org/content/early/2020/04/09/science.abb6936)).

Un momento, ¿aplicaciones que registran con quién has estado en contacto?... ¿Significa eso que tenemos que renunciar a nuestra privacidad y dársela a un Gran Hermano?

¡Diantres, no! **[DP-3T](https://github.com/DP-3T/documents#decentralized-privacy-preserving-proximity-tracing)**, un equipo de epidemiólogos y criptógrafos (incluyendo uno de nosotros, Marcel Salathé) *ya* está desarrollando una aplicación para rastrear contactos  –su código es público– que **no revela información sobre tu identidad, localización, quiénes son tus contactos o incluso *cuántos* contactos has tenido.**

Aquí se ve cómo funciona:

![](pics/es_ES/dp3t.png)

(y [aquí el cómic completo](https://ncase.me/contact-tracing/))

Junto a otros equipos similares como Protocolo TCN [^tcn] y MIT PACT[^pact], han inspirado a Apple y Google para incluir el rastreo de contactos privado directamente en Android e iOS.[^gapple] (¿No te fías de Google/Apple? ¡Bien! Es lo bueno de este sistema, ¡que no *necesita* confianza!). En breve, tu administración de salud pública local te podría solicitar que te descargues una aplicación. Si tienes como prioridad la privacidad y la disponibilidad de código, ¡por favor, hazlo!

[^tcn]: [Temporary Contact Numbers, a decentralized, privacy-first contact tracing protocol](https://github.com/TCNCoalition/TCN#tcn-protocol)

[^pact]: [PACT: Private Automated Contact Tracing](https://pact.mit.edu/)

[^gapple]: [Apple and Google partner on COVID-19 contact tracing technology](https://www.apple.com/ca/newsroom/2020/04/apple-and-google-partner-on-covid-19-contact-tracing-technology/). Ten en cuenta que no están desarrollando las aplicaciones *ellos mismos*, solo creando los sistemas que darán *soporte* a dichas aplicaciones.

Pero ¿qué pasa con las personas que no tienen teléfonos inteligentes? ¿O con los contagios a través de las puertas? ¿O con los casos «realmente» asintomáticos? Las aplicaciones de rastreo de contactos no pueden identificar todas las infecciones... y *¡no hay ningún problema con eso!* No estamos obligados a identificar *todos* los contagios, solamente ese 60% o más necesario para que R < 1.

(Diatriba sobre la confusión entre pre-sintomáticos y asintomáticos «reales». Los asintomáticos «reales» son muy pocos:[^rant])

[^rant]: Hay muchas noticias  –y, sinceramente, muchos artículos científicos– que no distinguen entre «casos que no han mostrado síntomas cuando les hicimos la prueba» (pre-sintomáticos) y «casos que *nunca* mostraron síntomas» (asintomáticos reales). La única manera de hallar la diferencia es mediante un seguimiento pormenorizado de los casos.
   
    Que es justo lo que hizo [este estudio](https://wwwnc.cdc.gov/eid/article/26/8/20-1274_article). (Aviso: «La publicación temprana de artículos no está considerada como versión final».) En un centro de llamadas en Corea del Sur donde hubo un brote de la COVID-19, «solo cuatro personas (1.9%) se mantuvieron asintomáticos durante los 14 días de la cuarentena y ninguno de los contactos en sus hogares sufrieron infecciones secundarias».
    
    Esto significa que los «asintomáticos reales» son pocos e infectarse con la enfermedad a través de un asintomático real ¡podría ser incluso más extraño!

El aislamiento de los casos *sintomáticos* reduciría R en un 40% y poniendo en cuarentena a sus contactos *pre/a-sintomáticos* reduciría R hasta en un 50%[^oxford]:

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

###Escenario 4+: Mascarillas para todos, verano, cortacircuitos

¿Qué pasa si R<sub>0</sub> es mucho mayor de lo que pensamos y las intervenciones anteriores, incluso con distanciamiento leve, *aún* no son suficientes para que R < 1?

Recuerde, incluso si no podemos hacer que R < 1, la reducción de R disminuye el «exceso» de casos totales y por lo tanto salva vidas. Pero aún así, R < 1 es lo ideal, así que aquí hay otras formas de reducir R:

**Mascarillas para todos:**

*«Espera»,* podrías preguntarte, *«¿Las mascarillas no evitan que no me ponga malo?*

Cierto. Las mascarillas no impiden que enferme[^incoming]... impiden que *otras* personas enfermen.

[^incoming]: «None of these surgical masks exhibited adequate filter performance and facial fit characteristics to be considered respiratory protection devices». [Tara Oberg y Lisa M. Brosseau](https://www.sciencedirect.com/science/article/pii/S0196655307007742)

[^outgoing]: «The overall 3.4 fold reduction [70% reduction] in aerosol copy numbers we observed combined with a nearly complete elimination of large droplet spray demonstrated by Johnson et al. suggests that surgical masks worn by infected persons could have a clinically significant impact on transmission». [Milton DK, Fabian MP, Cowling BJ, Grantham ML, McDevitt JJ](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3591312/)

[^homemade]: [Davies, A., Thompson, K., Giri, K., Kafatos, G., Walker, J., & Bennett, A](https://www.cambridge.org/core/journals/disaster-medicine-and-public-health-preparedness/article/testing-the-efficacy-of-homemade-masks-would-they-protect-in-an-influenza-pandemic/0921A05A69A9419C862FA2F35F819D55) Véase la tabla 1: una camiseta de algodón 100% tiene 2/3 de la eficiencia de transmisión de una mascarilla quirúrgica, para los dos aerosoles que probaron.

![](pics/es_ES/masks.png)

Para ponerlo en números: las mascarillas quirúrgicas *en la persona enferma* reduce la cantidad de virus de la gripe y el resfriado en los aerosoles en un 70%.[^outgoing] ¡La reducción de contagios en un 70% tendría el mismo impacto que un confinamiento!

Sin embargo, no estamos seguros del impacto de las mascarillas en la COVID-19 *en concreto*. En ciencia, solo se debe publicar un descubrimiento si se está al menos un 95% seguro de él. (...debe.[^replication]) Las mascarillas, a día 1 de mayo de 2020, están por debajo de ese «95% seguro».

[^replication]: Cualquier científico de verdad que lea la última frase estará riéndose-llorando ahora mismo. Ver: [p-hacking](https://en.wikipedia.org/wiki/Data_dredging), [la crisis de replicación](https://es.wikipedia.org/wiki/Crisis_de_replicación))

Sin embargo, las pandemias son como el póquer. **Apuesta solo cuando estés seguro al 95% y terminarás perdiéndolo todo.** Como ha apuntado un reciente artículo sobre las mascarillas en el British Medical Journal,[^precautionary] *tenemos* que hacer análisis de coste/beneficio con la incertidumbre. Como éste:

[^precautionary]: «It is time to apply the precautionary principle» [Trisha Greenhalgh et al \[PDF\]](https://www.bmj.com/content/bmj/369/bmj.m1435.full.pdf)

Coste: Si alguien lleva mascarillas caseras (que son ~2/3 tan efectivas como las mascarillas quirúrgicas[^homemade]), súper barato. Y si hay mascarillas quirúrgicas, son más caras pero aún así asequibles.

Beneficio: Incluso si hay un 50-50 de probabilidad de que las mascarillas quirúrgicas reduzcan los contagios entre un 0% y 70%, el «valor esperado» medio aún es el 35%, ¡lo mismo que la mitad de un confinamiento! Así que vamos a asumir que las mascarillas quirúrgicas reducen R en un 35%, descontando nuestra incertidumbre. (De nuevo, puedes cuestionar nuestras suposiciones cambiando los ajustes).

<div class="sim">
		<iframe src="sim?stage=int-6a&format=calc" width="285" height="380"></iframe>
</div>

(otros argumentos a favor y en contra de las mascarillas:[^mask_args])

[^mask_args]: **«Necesitamos los suministros para los hospitales».** *Sin discusión.* Pero ese argumento es para incrementar la producción no para el racionamiento. Mientras tanto, podemos fabricar mascarillas caseras.

   **«Son difíciles de llevar correctamente».** También es difícil lavarnos las manos siguiendo las instrucciones de la OMS –en serio, ¿¡«Paso 3) palma derecha contra el dorso de la mano izquierda»!?– pero aún así recomendamos el lavado de las manos, porque lo imperfecto es mejor que nada.
   
   **«Harán que las personas sean más descuidadas con el lavado de manos y el distanciamiento social».** Claro, los cinturones de seguridad hacen que las personas ignoren las señales de stop y la limpieza con hilo dental hace que las personas comamos rocas. En serio, opinamos todo lo contrario: las mascarillas son un *recordatorio físico constante* de ser precavidos –¡y en el este de Asia, las mascarillas también son un símbolo de solidaridad!
    
    

Las mascarillas *por si solas* no hacen que R < 1. Pero si el lavado de manos y «probar, rastrear, aislar» sólo nos lleva a R = 1.10, el que 1/3 de las personas lleven mascarillas hacen que R < 1, y ¡el virus está contenido!

**Verano:**

Vale, esto no es una «intervención» que podamos controlar, ¡pero será de ayuda! Algunos medios informan de que el verano no tendrá efecto con la COVID-19. Tienen solo la mitad de la razón: el verano no hará que R < 1, pero *reducirá* R.

Para la COVID-19, cada 1° Celsius (2.2° Fahrenheit) adicional hace que R disminuya un 1.2%.[^heat] La diferencia entre el verano y el invierno en la ciudad de Nueva York es de 15°C (60°F), así que el verano reducirá R en un 18%.

[^heat]: «One-degree Celsius increase in temperature [...] lower[s] R by 0.0225» y «The average R-value of these 100 cities is 1.83”. 0.0225 ÷ 1.83 = ~1.2». [Wang, Jingyuan y Tang, Ke and Feng, Kai and Lv, Weifeng](https://papers.ssrn.com/sol3/Papers.cfm?abstract_id=3551767)

<div class="sim">
		<iframe src="sim?stage=int-6b&format=calc" width="285" height="220"></iframe>
</div>

El verano por si solo no hará que R < 1, pero si tenemos recursos limitados, podemos desescalar algunas intervenciones en el verano –para escalarlas de nuevo durante el invierno.

**Un confinamiento «cortacircuito»:**

Y si con todo eso *todavía* no es suficiente para que R < 1... podemos hacer otro confinamiento.

¡Pero no tendríamos que estar 2 meses cerrados / 1 abierto una y otra vez! Dado que R se reduce, solo tendríamos que tener uno o dos confinamientos «cortacircuitos» antes de que la vacuna esté disponible. (Recientemente, Singapur tuvo que hacerlo, «a pesar» de que tuvo controlada la COVID-19 durante 4 meses. No es un fracaso: esto *es* lo que el éxito requiere).

Aquí hay una simulación de un escenario de «casos vagos»:

1. Confinamiento, y tras él..
2. Una cantidad moderada de higiene y «probar, rastrear, aislar», con una pizca de «mascarillas para todos», y luego...
3. Uno o más confinamientos de «cortacircuitos» antes de encontrar la vacuna.

<div class="sim">
		<iframe src="sim?stage=int-7&format=lines&height=620" width="800" height="620"></iframe>
</div>

Sin mencionar todas las *otras* intervenciones, para reducir aún más R:

* Restricciones de viajes/cuarentenas.
* Comprobación de temperaturas en los centros comerciales y escuelas.
* Lavado a conciencia de los espacios públicos.
* [Reemplazo de apretón de manos con el choque de pies](https://twitter.com/V_actually/status/1233785527788285953).
* Y el resto de cosas que nos brinda la ingenuidad humana.

. . .

Esperemos que estos planes le den esperanzas. 

**Incluso en un escenario pesimista, *es* posible ganar a la COVID-19 y proteger nuestra salud mental y financiera.** ¡Usa el confinamiento como un «botón de reinicio», mantén R < 1 con el aislamiento de casos + rastreo de contactos con privacidad + *al menos* mascarillas para todos... y la vida puede volver a cierta normalidad!

Claro, te habrá resultado un proceso complicado. ¡Pero volverás a pedir una cita en una tienda de tebeos! Y podrás ir con tus amigos a ver el último sacaperras de Hollywood. Podrás ir a observar a otros en una biblioteca y regocijarte de que la gente vaya por el simple hecho de *estar vivos*.

Incluso en el peor escenario... la vida continúa.

Así que ahora, planifiquemos algunos de los *peores* escenarios. Aterrizaje en el agua, colóquese el salvavidas y, por favor, siga las luces de emergencia que indican la salida:

<div class="section chapter">
    <div>
		<img src="banners/curve.png" height=480 style="position: absolute;"/>
        <div>Los próximos años</div>
    </div>
</div>

Te contagias de la COVID-19 y te recuperas. O llegas a la vacuna de la COVID-19. En cualquier caso, ahora eres inmune...

...*¿durante cuanto tiempo?*

* El pariente más cercano de la COVID-19 es el SARS, cuyos supervivientes tuvieron 2 años de inmunidad.[^SARS immunity]
* Los conarovirus que causan el resfriado común te dan 8 meses de inmunidad.[^cold immunity]
* Hay informes de personas recuperadas de la COVID-19 que luego han vuelto a dar positivo pero no está claro si han dado falsos positivos.[^unclear]
* Y un estudio *aún no revisado por pares* con monos muestran inmunidad al coronavirus de la COVID-19 durante al menos 28 días.[^monkeys]

Pero para la COVID-19 *en humanos*, a día 1 de mayo de 2020, la gran incógnita es «hasta cuándo».

[^SARS immunity]: «SARS-specific antibodies were maintained for an average of 2 years [...] Thus, SARS patients might be susceptible to reinfection ≥3 years after initial exposure». [Wu LP, Wang NC, Chang YH, et al.](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2851497/) «Por desgracia», nunca sabremos cuánto dura la inmunidad al SARS, puesto que se erradicó rápidamente.

[^cold immunity]: «We found no significant difference between the probability of testing positive at least once and the probability of a recurrence for the beta-coronaviruses HKU1 and OC43 at 34 weeks after enrollment/first infection». [Marta Galanti & Jeffrey Shaman (PDF)](http://www.columbia.edu/~jls106/galanti_shaman_ms_supp.pdf)

[^unclear]: «Once a person fights off a virus, viral particles tend to linger for some time. These cannot cause infections, but they can trigger a positive test». [de STAT News por Andrew Joseph](https://www.statnews.com/2020/04/20/everything-we-know-about-coronavirus-immunity-and-antibodies-and-plenty-we-still-dont/)

[^monkeys]: De [Bao et al.](https://www.biorxiv.org/content/10.1101/2020.03.13.990226v1.abstract) *Aviso: Este es un borrador de artículo y no ha sido certificado por la revisión por pares (aún).* También es importante hacer hincapié: solamente probaron la reinfección 28 días después. 

Para estas simulaciones, digamos que es 1 año.
**Esta simulación comienza con 100% <icon r></icon>**, disminuyendo exponencialmente en susceptibles, <icon s></icon>s sin inmunidad después de un año, de *promedio*, con variación:

<div class="sim">
		<iframe src="sim?stage=yrs-1&format=lines&height=600" width="800" height="600"></iframe>
</div>

¡El regreso de la disminución exponencial!

Este es el **modelo SEIRS**. La «S» es por las personas <icon s></icon> Susceptibles, de nuevo.

![](pics/es_ES/seirs.png)

Ahora, vamos a simular un brote de la COVID-19, durante 10 años, sin intervenciones... *si la inmunidad sólo durase un año:*

<div class="sim">
		<iframe src="sim?stage=yrs-2&format=lines&height=600" width="800" height="600"></iframe>
</div>

En simulaciones anteriores, solo teníamos *un* pico que sobrepasaba las UCIs. Ahora, tenemos muchos *y* los casos <icon i></icon> se equilibran *permanentemente en* la capacidad de UCIs. (Que, recuerda, hemos *triplicado* para estas simulaciones).

R = 1, es **endémico.**

Por fortuna, dado que el verano reduce R, la situación mejorará:

<div class="sim">
		<iframe src="sim?stage=yrs-3&format=lines&height=640" width="800" height="640"></iframe>
</div>

Oh.

De forma contraintuitiva, ¡el verano hace que los picos empeoren *y* sean más frecuentes! Esto es debido a que el verano reduce las nuevas <icon i></icon>s, pero por otra parte reduce las nuevas <icon r></icon>s inmunes. Lo que significa que la inmunidad se desploma en el verano *creando* grandes picos frecuentes en el invierno.

Por fortuna, la solución a este problema es bastante sencilla: solo hay que vacunar a la población en cada otoño/invierno, como hacemos con las vacunas de la gripe:

**(Después de ver la grabación, ¡intenta simular tus propias campañas de vacunación! Recuerda que puedes detener/continuar la simulación en cualquier momento).**

<div class="sim">
		<iframe src="sim?stage=yrs-4&format=lines" width="800" height="540"></iframe>
</div>

Pero aquí hay una pregunta más aterradora:

¿Y qué pasa si durante *años* no hay ninguna vacuna? ¿O *nunca*?

**Seamos claros: esto es muy poco probable.** La mayoría de epidemiólogos piensan que habrá una vacuna para 2021 o 2022. Por supuesto, nunca ha habido una vacuna para ninguno de los otros coronavirus, pero eso fue porque el SARS se erradicó rápidamente, y para «el» resfriado común dicho esfuerzo no ha valido la pena. 

Aún así, los investigadores de enfermedades contagiosas han expresado sus temores: ¿Y si no podemos hacer suficientes?[^vax_enough] ¿Qué pasa si nos damos prisa y al final no es segura?[^vax_safe]

[^vax_enough]: «If a coronavirus vaccine arrives, can the world make enough?» [por Roxanne Khamsi, en Nature](https://www.nature.com/articles/d41586-020-01063-8)

[^vax_safe]: «Don’t rush to deploy COVID-19 vaccines and drugs without sufficient safety guarantees» [por Shibo Jiang, en Nature](https://www.nature.com/articles/d41586-020-00751-9)

Incluso en el escenario «sin vacuna», aún tenemos 3 maneras de escapar. De la más a la menos espantosa:

1) Hacer intervenciones R < 1 intermitentes o suaves para llegar a la «inmunidad de grupo». (Aviso: esto implica muchas muertes y muchos pulmones dañados. *Y* no funciona si la inmunidad no es duradera).

2) Hacer que las intervenciones R < 1 sean persistentes. El rastreo de contactos y las mascarillas se convierten en la nueva normalidad en el mundo post-COVID-19, igual que las pruebas ITC y llevar condón se convirtieron en la norma en el mundo post-VIH.

3) Hacer intervenciones R < 1 hasta que se desarrollen tratamientos para la COVID-19 con los que sea mucho, mucho, mucho menos probable la necesidad de cuidados intensivos. (Lo que deberíamos hacer *¡en cualquier caso!*) La reducción del uso de UCIs por 10x es lo mismo que incrementar nuestra capacidad de UCIs por 10x:

**Aquí hay una simulación en la que *no* hay una inmunidad duradera, *no hay* vacuna, e incluso no hay ninguna intervención, solo un incremento lento de la capacidad para sobrevivir a los picos de largo plazo:**

<div class="sim">
		<iframe src="sim?stage=yrs-5&format=lines" width="800" height="540"></iframe>
</div>

Incluso en el *peor* de los peores escenarios... la vida prevalece.

. . .

Quizás quieras cuestionar nuestras suposiciones e intentar unos R<sub>0</sub>s diferentes u otros números. ¡O intentar simular tu *propia* combinación de planes de intervención!

**Aquí hay un «zona de juego» (opcional), con *todo* disponible. (deslizar para ver todos los controles) ¡Simula y juega tanto como quieras!:**

<div class="sim">
		<iframe src="sim?stage=SB&format=sb" width="800" height="540"></iframe>
</div>

Este «simular de vuelo de epidemias» básico nos ha enseñado mucho. Nos ha permitido encontrar respuestas a dudas que teníamos sobre los pasados meses, los próximos meses y los próximos años.

Así que, finalmente, regresemos a...

<div class="section chapter">
    <div>
		<img src="banners/curve.png" height=480 style="position: absolute;"/>
        <div>El ahora</div>
    </div>
</div>

El avión se ha hundido. Hemos corrido a los botes salvavidas. Ahora es momento de encontrar tierra firme.[^dry_land]

[^dry_land]: La metáfora de la tierra firme es [de Marc Lipsitch y Yonatan Grad, en STAT News](https://www.statnews.com/2020/04/01/navigating-covid-19-pandemic/)

Equipos de epidemiólogos y políticos de la ([izquierda](https://www.americanprogress.org/issues/healthcare/news/2020/04/03/482613/national-state-plan-end-coronavirus-crisis/), la [derecha](https://www.aei.org/research-products/report/national-coronavirus-response-a-road-map-to-reopening/ ) y [multi-partidistas](https://ethics.harvard.edu/covid-roadmap)) han llegado al consenso de que para ganar a la COVID-19 debemos proteger nuestras vidas *y* libertades.

Esta es la idea general, con algunos planes de contingencia (sin consenso):

![](pics/es_ES/plan.png)

¿Qué es lo que esto implica para TÍ, ahora mismo?

**Para todos:** Respeta el confinamiento para que podamos pasar de la Fase 1 rápidamente. Mantén limpias esas manos. Fabrica tus propias mascarillas. Descarga una aplicación de rastreo de contactos *que proteja la privacidad* cuando estén disponibles el próximo mes. Mantente sano ¡física y mentalmente! Y escribe a tu representante público para que mueva el culo y...

**Para políticos:** Promulga leyes que apoyen a quienes tienen que auto-aislarse/hacer cuarentena. Contrata muchos más rastreadores de contactos, *apoyados* por aplicaciones aplicaciones de rastreo de contactos que protejan la privacidad. Ofrece más fondos a cosas que deberíamos estar fabricando, como...

**Para fabricantes:** Haz pruebas. Fabrica ventiladores. Fabrica equipo de protección individual para los hospitales. Haz aplicaciones. Haz antivirales, profilácticos y otros tratamientos que no son vacunas. Fabrica vacunas. Haz pruebas. Haz pruebas. Haz pruebas. Da esperanzas. 

No subestimemos el miedo para dar esperanzas. Nuestro miedo debería *hacer equipo* con nuestra esperanza, como los inventores de los aviones y los paracaídas. *Creamos* un futuro esperanzado preparándonos para futuros horribles.

La única cosa a temer es la idea de que la única cosa a temer es al miedo mismo.
