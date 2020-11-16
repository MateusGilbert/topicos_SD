# topicos_SD
Presentes neste repositório trabalhos desenvolvidos para a disciplina de Tópicos Especiais em Sistemas Digitais ministrada pelo professor Flávio Mello no Período Letivo Exepcional (PLE) na Universidade Federal do Rio de Janeiro (UFRJ). Os arquivos aqui presente são:

(1) um programa de extração de carácteristicas relevantes de arquivos PDF (proj.ipynb);

(2) protótipo (inacabado) de um programa para classificação de processos jurídicos utilizando rede LSTM Bidirecional (trab_final.ipynb).

--------------------------------------------------------------------------------------------------------------------------------------------------------------------
Como utilizar:
--------------------------------------------------------------------------------------------------------------------------------------------------------------------

(1) O programa solicitara o upload dos arquivos que se deseja análisar.

![alt image size](https://github.com/MateusGilbert/topicos_SD/blob/main/pictures/Screenshot_2020-11-16%20Google%20Colaboratory.png){width="50%"}

Os arquivos carregarregados devem ser no formato pdf.

![alt image size](https://github.com/MateusGilbert/topicos_SD/blob/main/pictures/Screenshot%20from%202020-11-16%2016-55-37.png){width="50%"}

Dois programas OCR (pdfplumber e tesseract OCR) convertem o arquivo pdf em arquivo texto, para que as extrações sejam executadas. O arquivo gerado pelo pdfplumber é utilizado para as análises de palavras (variedade lexical e frequência de incidência no texto), enquanto o arquivo gerado pelo tesseract é utilizado para a análise das frases do texto. Ao final, um pequeno resumo das informações dos arquivos análisados são listadas.

![alt text](https://github.com/MateusGilbert/topicos_SD/blob/main/pictures/Screenshot%20from%202020-11-16%2016-46-29.png)

--------------------------------------------------------------------------------------------------------------------------------------------------------------------

(2) O programa desenvolvido para classificar arquivos de processos judicias fornecidos na disciplina. Assume que os arquivos tratados estão comprimidos em um arquivo zip, presente em um Google Drive que deve ser acoplado (mount) quando solicitado pelo programa. Alguns parâmetros devem ser ajustados (além da rede lstm bidirecional):

  (i) quatidade de páginas de cada arquivo em pdf que são convertidas em arquivo texto (default = 2 páginas);
  
  (ii) quantidade de palavras (que não são stopwords) que servem de entrada para a rede Bi-LSTM (default = 1000 palavras).
  
Na sua atual configuração, o programa procura classificar os arquivos utilizados no treinamento de acordo com os campos listados antes de fornece-los para o treinamento da rede neural.
