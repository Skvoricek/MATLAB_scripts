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
************************************
2016-03-03
SPECTRAL_FILTRATION
- added a spectrogram plot as figure6
- created export for fig6 as well 

NUMBER_ALLOCATOR
- Added 6th choice for export (button 6)
- changed proportions of command figure
 
**************************
2016-03-08
FILTERED_PEAKFINDER
 - added fig_cescription (h1_peaks_*)
 - commented choice of sampling frequency for 4kHz and 16kHz
 
 SPECTRAL_FILTRATION
 - commented choice of sampling frequency for 4kHz and 16kHz

************************
2016-03-10
FILTERED_PEAKFINDER
 - added starting time for noise level calculation (for automatic threshold  decision process)
 - repaired separation (time distance of peaks) saving (previous versions were saved as "char" (transfered from ascii to double)
 
**********************
2016-03-16
PARTIAL SIGNAL PROCESSING	
added new matlab script - combining previous multiple file support and partial filtration (reconstructed signal)
Allowes to perform spectral filtration and statistical characteristics calculation above brushed part of original part of signal. 
**********************
2016-04-08
FILTERED_PEAKFINDER &  SPECTRAL_FILTRATION
 - added commented choice for 32kHz processing
 - commented "filter" variable - causing problem during spectral filtration of signal
FILTERED_PEAKFINDER 
 - repaired saved_variable (computed characteristics and calculation variablses) saving into ascii txt file
 
*********************
2016-10-13
FILTERED_PEAKFINDER &  SPECTRAL_FILTRATION & PARTIAL SIGNAL PROCESSING
 - added possibility to load waw file (via filetype function)
*********************
2016-11-02
SOUND_VIEWER
-added export into the txt file.
********************
2016-11-04
SIGNAL_VIEWER
- created new sccript - CSV and WAV into signal with FFT and spectrogram. Able to save file int otxt (commented)

********************
2016-11-14
FREQUENCY_MIC-SIG_PROC
 - created new script for microphone evaluation. Manual choice of the signal part (CSV or WAV), filtration (parameter choice), statistical variables and fig/png save.
 - save_statistics= [max;min;mean;std;var;fs;wwidth;fmll;fmhh;samples]; - first 4 from abs(IFFT(data)).
 
 FILTERED_PEAKFINDER 
  - code repired according to last commit...
  - changed initial save limit for noise calculation (down to 0.5xfs) 
 ********************
2016-11-15
FREQUENCY_MIC-SIG_PROC
 - small code mistakes and formating repaired
 - added automatical fs input from WAV file, 
 - export  - save_statistics= [max;min;mean;std;var;fs;wwidth;fmll;fmhh;max_freq;samples]; - first 4 from abs(IFFT(data)). 
  ********************
2016-11-16
FREQUENCY_MIC-SIG_PROC
  - added automatic sample recaltulation for filtered signal (max value for estimated amount of samples - moved along the X axis
  - Error message in case of internal overflow of recalculating cycle
  - changed the save statistics accordingly (now from recalculated samples)
  - chart and filename changed ( filename = char(filename(1:12));%filename rename (line 150))
 ********************
 SPECTRAL_BAND_PICK
 2016-11-18
  - script to bring out numerical values of a spectrum (brushed or not)
  - addded brushed/nonbrushed decision-making logic
  - Ccentral frequencies input in a cycle - number of cycles is a subject of a choice 
  Export save_variable = [length(X) FFT data length,str2num(fmhh - window width );Spectral_vector (where Spectral_vector(i,1) = central_freq and Spectral_vector(i,2) = max_freq)
  ********************
 SPECTRAL_BAND_PICK
 2016-11-19
  - Added Central frequency bypass for 21 microphonce testing frequencies.
 -All WAW scripts works with m4a as well 
 ********************
 2016-12-29
  - addedd 8kHz sampling to most of the scripts.
   - updated network backup and names of all files
 *******************
 2017-01-05
   SIMPLE_PLOT_TIME
   - created from SIMPLE_PLOT by adding sampling frequency and sample axes recalculation...
 *******************
 2017-01-20
   SIMPLE_PLOT_TIME
  - file numbering has been repaired, right name of the figure2 window
  MULTIPLE_SIGNAL_VIEWER
   - repaired subplot figure structure (wrong numbering), cha
  FILTERED_SIGMALIMIT_FINDER
   - Created evaluation script (origin filtered_peakfinder) for sigma lvl establishment
   - noise threshold calculated as sigma function (std) + mean value of the signal
   - saved peaks as following> save_sigma_peaks=[max_peak_value;low_sigma_point;high_sigma_point]
   - from max_peak_value and threshold (sigma) the SNR is recalculated

 Kuba Maršálek - jakub.marsalek@safibra.cz 
