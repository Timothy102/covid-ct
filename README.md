# COVID-19 Lung Extensivess Deep Learning Model

The source code ascribed in this repo as well as the deep learning algorithm were conducted during a national machine learning competition - RIS in Slovenia. 

## About the model 


Pozdravljeni, na hitro o modelu. Ideja klasifikacije je, da se vse rezine pacienta segmentirajo z uporabo Inf-Net-a (DengPing et al.),
s čimer se dobi količino anomalij na vsaki rezini. To naredimo za vsako rezino in izračunamo, kolikšen odsotek pljuč zajemajo bodisi
GGO, bodisi konsolidacije (ti dve maski na koncu izvrže InfNet). V prvem delu tekmovanja sva s pomočjo statistike razdelila paciente na 1 % velike intervale
in izračunala verjetnost, da ima pacient, katerega odstotek anomalije pljuč paše v interval, obsežno COVID pljučnico. Na koncu še savgol filter za izravnavo in to je to. Statistična obdelava se nahaja v Stats.ipynb - začetni del sodi v drugi del tekmovanja, končni del pa je bil del prvega dela tekmovanja.
V drugem delu tekmovanja sva spet izračunala odstotek pljuč, ki je patološki in z uporabo funkcije calculate_thresholds() v stats.ipynb določila meje za prestop med A in B ter B in C, tako da se maksimizira območje znotraj intervala - da pripada čimveč ploščine tistemu razredu.
Model Inf-Net in postopek pridobitve mask ter izračun skupnih odstotkov se nahaja v Do.ipynb. Glavna funkcija, ki opravlja večino dela je process_one_patient(). Predprocesiranje je zelo podobno kot v vzorčnem primeru, le da nisva uporabila samo centralnih rezin, ampak vse.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------

Hello, quickly about the model. The idea of the classification is to segment all patient slices using Inf-Net (DengPing et al.),
thus obtaining the amount of anomaly on each slice. We do this for each slice and calculate what percentage of the lungs they cover either
GGO, either consolidation (two masks eventually ejected by InfNet). In the first part of the competition, patients are divided into 1% intervals with statistics
and calculated the probability that the patient has what percentage of lung anomaly fits in the interval, extensive COVID pneumonia. Finally a sagol leveling filter and that’s it. The statistical processing is located in Stats.ipynb - the initial part of the court in other parts of the competitions, and the final part was part of the first part of the competitions.
In the second part of the competition, the percentage of lungs was calculated again, which pathologically and using the Calculate_thresholds () functions in stats.ipynb determined the limits for the transition between A and B and B to C, so that the interval maximizes the intraocular area.
The Inf-Net model and the procedure for obtaining a mask to calculate total data can be found in Do.ipynb. The main function that does most of the work is process_one_patient (). Preprocessing is very similar to the sample case, except that it used not only the central slices, but everything.



## Contact
Please, feel free to reach out on [LinkedIn](https://www.linkedin.com/in/tim-cvetko-32842a1a6/) or [Gmail](tim@metawaveai.com).

## License

Licensed under the MIT [LICENSE](LICENSE)

