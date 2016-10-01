The project is a music genre classification system.

1.Data set: GTZAN Genre Collection (1.28G)
http://marsyasweb.appspot.com/download/data_sets/

please download and put files to the 'genres_ori' folder in the root directory.

2. convert data from .au to .wav

please use any third-party software to convert the audios from .au to .wav 

and put into 'genres' folder

OR use matlab with following code to do so
******************************
%read in music
data_path='.\genres_ori\';
save_path='.\genres\';
genres={'blues','classical','jazz','pop','rock'};%5 music genres
for i=1:5 %for 5 genres
    flist=dir(fullfile(data_path,genres{i},'*.au')); %read files in data_path
    save_list=[save_path genres{i} '\'];
    n=length(flist); %number of files
    for j=1:n
        [data,fs]=audioread(fullfile(data_path,genres{i},flist(j).name)); %read music       
        audiowrite([save_list num2str(j) '.wav'],data,fs);
    end
end
*******************************

3. Used python package:

numpy, scipy, os, matplotlib, sklearn,pdb
