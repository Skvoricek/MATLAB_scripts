# MATLAB_scripts
Matlab scripts developed to make the evaluations easier
****

READ ME for MATLAB files:

	-Vše, co je napsáno CAPS LOCK s čísly formátu data (YYYYMMDD) na konci za podtržítkem jest spustitelný 	vyhodnocovaný m.FILE

	-Při vyhodnocování zkopírujte mimo potřebného vyhodnocovacího souboru též VŠECHNY funkce (m.FILE nadepsaný malým písmenkem bez data) pro zajištění hladkého běhu programů.

	-Veškeré vyhodnocení je připraveno na datový typ *.CSV s daty pro zpracování v druhém sloupci (možno libovolně upravit přepsáním čísla ve zdrojáku.)
	
	- Veškeré obrázky, txt soubory a další věci "lezoucí ze skrzptů" se ukládají do kořenového adresáře, kde je umístěn vyhodnocovací m.file.
	- Používá se desetiná tečka. (nikoliv čárka ",")



CHANGELOG:
2015-12-18:	FILTERED_PEAKFINDER 	- upraveno zobrazení počtu peaku.

		FREQUENCY_CHECK    	 - upraveno ukládání obrázků, přidání hystogramu, středních hodnot a grafického vynesení. dopočítání STDEV vzájemných rozdílů mezi vzorky v datech. Ukládání txt 			file s 	[sampling frequency, mean timeStamp , standard deviation of timeStamp and statistical 			number of samples od shora v *double formátu], dynamické odečítání posledních 11 znaků z názvu 		pro ukládání.

--------------------------
2016-01-12	FREQUENCY_CHECK & FILTERED_PEAKFINDER & SPECTRAL_FILTRATION     - upraveno vykreslování proměnných do textboxů (annotation) - již není škrtlé boxem.

--------------------------
2016-01-15	FILTERED_PEAKFINDER 	- upraveno zadání kontstanty určující výpočet počtu z absolutních hodnot nebo reálného signálu (abs(data) / data)).
					-ukládání parametrů pro výpočet -do jedné řádky matice: save_variables = [meanSigP_tot(střední hodnota nalezených peaků),stdev_SigP_tot(stdev nalezených peaků),num_double (počet nalezených peaků),threshold_ref (výkonová hranice thresholdu),SNR_tot_DB(SND 10log10(signál/šum)),Threshold(násobek maxima v šumovém intervalu),noise_time (doba šumového intervalu -napočítání šumu),separation (minimální časový odstup peaků od sebe),absOn(hodnota abs (1 - signál v abs, jinak ne),fs (vzorkovací kmitočet),wwidth (okno pro FFT¨) ,fml (spodní kmitočet pro pásmovku na filtraci),fmh (horní kmitočet pro pásmovku na filtraci)];
    
					- smazání vzorkovací frekvence v duplicitním zadání (druhá část výpočtu - počítání peaků
					-přidání střední hodnoty a stdev nalezených peaků
					- oprava ukládání NaN hodnot (kontrola na existenci záporných peaků - pokud ne pak se vypustí z výpočttu
					- eleiminace přebuzení thresholdu v rekonstruovaném signálu výpočtu peaků

-------------------------
2016-02-01	FREQUENCY_CHECK		- upraven výpočet (ztráta přesnosti na posledních desetinných místech - předchozí výsledky jsou posunuty (nutno přepočítat). 1044Usec na 1024usec, 957Hz na 976Hz - adekvátně pro 2kHz

            MULTIPLE_CSV_PLOT - V cyklu vykreslí zadaný počet souborů vybraných interaktivně ze složky. Legendu je nutné dopsat přímo do kódu - zobrazuje se pouze stejný počet legend jako je křivek (další nejsou v rámečku). Ukládání grafu je pouze manuální  

-------------------------
2016-02-02	FREQUENCY_CHECK		- Odstraněny pauzy mezi výpočty

2016-02-15

FILTERED_PEAKFINDER 
 - updated first time calculation (taken backwards from last char)
 
SPECTRAL_FILTRATION
 - updated first time calculation (taken backwards from last char)
 - updated interpreter for annotation and figure description (tex vs none)
 

SIMPLE_PLOT 
 - added possibility to combine files (you have to state nuber of files in the begining of the cycle)
 - added to possibility to save figures at the end
 - changed figure name prefix (hx_plot_***)
************************************
2016-02-24 

FILTERED_PEAKFINDER
 - updatet for multiple CSV file choice
 - fixed the first_time in graphs
SPECTRAL_FILTRATION
 - updatet for multiple CSV file choice
 - fixed the first_time in graphs
SIMPLE_PLOT
 - fixed the first_time in graphs
 -
 
 Kuba Maršálek - jakub.marsalek@safibra.cz
