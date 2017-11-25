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
*********************
2017-01-24
SIMPLE_PLOT_TIME_DIR
 - Created script which takes all csv files in the folder and saves fig and png graphs for each file with time x axess according to given sampling frequency.
*********************
2017-02-01
MULTIPLE_SIGNAL_VIEWER
 - repaired subplot number 15. (wrong data input)
MULTIPLE_SIGNAL_VIEWER_SHIFT
 - updated MULTIPLE_SIGNAL_VIEWER
 - possible to insert time_shift between signals for better synchronization
*********************
2017-02-02
PARTIAL_TIME_PLOT_DIR
 - created to plot spectrum of part of the signal according to choosen time range (multiple channels measured in the same time to compare the spectral densities in all of them)
  - the folder has to be empty of other files (can be filled with folders)
*********************
2017-02-03
FILTERED_SIGMALIMIT_FINDER_DIR
 - created from sigmalimit_finder via additional loop and numbering signal recalculation. Special saving of variables:
 save_variables = [meanSigP,meanSigP_neg,stdevSigP,stdevSigP_neg,num_double,threshold_ref,SNR_tot_DB,Threshold,noise_start_time,noise_end_time,sep_num,absOn,fs,wwidth ,fml,fmh,first_sec_neglect,last_sec_neglect];
 save_sigma_peaks=[[SNR_max 0];max_peak_value;low_sigma_point;high_sigma_point] 
 - takes all vlues in seconds and/or Hz, recalculation into speed is not implemented
 - threshold is taken as a std (data part for processing)
 - implemented relative filepath to pick up additional matlab functions
 - automatically saved figures (numberAllocator bypased)
 - bypas for parameter input inside the lowest file loop is prepared
 *********************
 2017-02-15
 FILTERED_SIGMALIMIT_FINDER_DIR
  - fix of variable clearing
  - implemented case of no peaks (no signal / start / end of event detected)
  - added plot (time, threshold) length check - possible plotting problem solved
  - changed save_sigma_peaks=[[SNR_max 0];max_peak_value(1,1);max_peak_value(1,2);low_sigma_point(1,1);low_sigma_point(1,2);high_sigma_point(1,1);high_sigma_point(1,2)] ;%back to saving process -- max value, and both borders for calculated sigma threshold
 - added save_all_sigma_peaks (for all files in big cycle)
 *******************
 2017-03-23*
 SPECTRAL_FILTRATION_DIR
 Created automatic tool to run through DIR saving all the output.
 *******************
 2017-03-28
 SPECTRAL_FILTRATION_DIR
 - finished and optimized (longest time takes num2str). Needs CS_header in the same folder)
 - tool to load WAV or M4A file and according to fs, date and time create the time stamps and standard CSV structure - saving it into the same folder.
 
  *******************
 2017-03-29
 SOUND_TO_CSV_SAVE
 - created tool to choose WAV and / or M4A files to load them (including dir information - date and time with sampling frequency
 - it recalculates and creates time stram (date included)
 - must include CSV_header.csv (source file for the header - can be changed)
 - takes a long time (tens of minutes) (shown in waitbar) according to number of rows.
 - output is a CSV_file of the same name as a source WAV or M4A file.
 
   *******************
 2017-03-29
 SOUND_TO_CSV_SAVE_DIR	
 - changed for possible multifile use
 - the CSV_header.csv must be next to the source .m file 
 - input m4a / WAV file must be in the separate folder (with nothing else)
 - uses waitbars to comment the progress
 
    *******************
 2017-03-29
 SOUND_TO_CSV_SAVE_DIR	& SOUND_TO_CSV_SAVE	
  - date format exchange (dd-mm-yyy), added _space_ after the time stamp 
  - verified functionality for WAV files taken from direct measurement
 
 
    *******************
 2017-04-20
 SIMPLE_PLOT_TIME_DIR
  - added annotation box with min, max, mean and stdev


*******************
2017-04-25

FILTERED_PEAKFINDER_DIR_ANE
- created to evaluate for cirular measurement of FBG anemometer. Filtration turned off 

*******************
2017-04-25
FILTERED_PEAKFINDER_DIR
- created evaluation tool for normalized (reproductor) mechanical testing - peak calculation for the whole dirrectory - including the spectral filtration

****************
2017-04-25
SIMPLE_PLOT_TIME_STATISTIC_DIR
- created simple time related plot tool exporting statistical values [mean, stdev, min, max] into txt file

*****************
2017-05-05
STATISTICAL_TEST
- Created test to check statistical distributions of input data, evaluate P-P and Q-Q plots, obtain and draw return level functions.

*****************
2017-05-09
DIFF_SIG_TIME_DIR
 - Created to change data for following evaluation
 - Saves variables [mean, max, min, std, window size and fs],
 - Implemented differencial code (data(i)-data(i+1))
 - Exports eperimental distribution fce (max / mean or so) of input data set over window_size of sampling points in a cycle into txt file
 
 
*****************
2017-05-10
STATISTICAL_TEST & DIFF_SIG_TIME_DIR
-celaning and getting rid of the residual mistakes, fixed figure saving and export

*****************
2017-06-13
MULTIPLE_SIGNAL_VIEWER_ANIMATED
 - created animation tool for multiple signal viewer (number by choice) (input txt file by choice, sampling frequency parameter). 
 - can plot multiple siglas (each into separate window with dynamic Y axis adjustment)
 - can plot all signals into one file and run the time axis with permanent width (taken by seconds)
 - added computation time comparison into second based animation
 *******************
 2017-06-20
STATISTICAL_TEST  
- changed filename u(to bethe whole wtring (-4))
- changed the name of output figures (added _statistics_p_q_RL)

FILTERED_PEAKFINDER
- changed the borders for computation (10 sec from both - start and end has been neglected. First 41 FFT points has been taken into the computation (according the fs and filter - DC value +- something)

2017-07-26
BIN_CHOBOTNICE_VSB_DIR
-bin file reading fixed.
*********************
2017-08-04
BIN_CHOBOTNICE_VSB_DIR
- normalization constants for demodulation eq (Vmin + Vmax ) taken as a max (min) for each channel (ch1;ch2;ch3). This goes into all files in second cycle - the computation.
- saved picture for each channel additionally
- save_statistics= [vMax,vMin, numfiles]; (length number of files in channel + 1); into txt file named according to ch1
- saving demodulation result into txt file (for each file set of computation; Y(ch1,ch2,ch3)
*************************
2017-08-08
SIGNAL_VIEWER_PLAY
-loading the csv or waw, plot the signal, ft and spectrum, and playing sound (possible to stop, pause and resume) with sec count in the command window (native - must be reset if played again))
*************************
2017-08-09
SIGNAL_VIEWER_PLAY
 - save wav file has the filename.
 - fs = round(fs) given in the initial window 
 - autosave of the data commented (to save space and time)
 - automatic play commented at line 204, can by played manualy - commands comented in the script
************************
2017-10-16
SIMPLE_PLOT_TIME_DIR
 - added possibility to read binary files (in a code - use comment to make the choice)
*************************

2017-10-24
SIMPLE_PLOT_TIME_DIR
- added statistical values to be exported in txt
****************************
2017-11-01
BIN_CHOBOTNICE_VSB_DIR
- added resampling of the demodulation data (1MHz to 20kHz)
- txt and fig export of resampled_demodulation

*******************
2017-11-04
SIGNAL_VIEWER_PLAY 
 -  added binary files (in case no file is chosen and "LOAD" button is being clicked dirrecty)
 
 
*******************
2017-11-23
SIMPLE_PLOT_TIME_DIR
- added export in wav format.
************************
2017-11-25
SIGNAL_PLOT_MICROPHONE_NET
-takes 4 signals from destinations, applies DIFF, computes spectrogram and plots thoose on joined x-axes (paralel and spectrogram in subplot), raw diff in one figure

SIMPLE_PLOT_TIME_DIR
- added expirt in wav format.
- added export of histogram and its proporties (edges and values)

Kuba Maršálek - jakub.marsalek@safibra.cz 
