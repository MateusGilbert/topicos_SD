# topicos_SD
Presentes neste repositório trabalhos desenvolvidos para a disciplina de Tópicos Especiais em Sistemas Digitais ministrada pelo professor Flávio Mello no Período Letivo Exepcional (PLE) na Universidade Federal do Rio de Janeiro (UFRJ). Os arquivos aqui presente são:

(1) um programa de extração de carácteristicas relevantes de arquivos PDF (proj.ipynb);

(2) protótipo (inacabado) de um programa para classificação de processos jurídicos utilizando rede LSTM Bidirecional (trab_final.ipynb).

--------------------------------------------------------------------------------------------------------------------------------------------------------------------
Como utilizar:
--------------------------------------------------------------------------------------------------------------------------------------------------------------------

(1) O programa solicitará o upload dos arquivos que se deseja analisar.

![test image size](https://github.com/MateusGilbert/topicos_SD/blob/main/pictures/Screenshot_2020-11-16%20Google%20Colaboratory.png)

Os arquivos carregados devem ser no formato pdf.

![test image size](https://github.com/MateusGilbert/topicos_SD/blob/main/pictures/Screenshot%20from%202020-11-16%2016-55-37.png)

Dois programas OCR (pdfplumber e tesseract OCR) convertem o arquivo pdf em arquivo texto, para que as extrações sejam executadas. O arquivo gerado pelo pdfplumber é utilizado para as análises de palavras (variedade lexical e frequência de incidência no texto), enquanto o arquivo gerado pelo tesseract é utilizado para a análise das frases do texto. Ao final, um pequeno resumo das informações dos arquivos análisados são listadas.

![test image size](https://github.com/MateusGilbert/topicos_SD/blob/main/pictures/Screenshot%20from%202020-11-16%2016-46-29.png)


--------------------------------------------------------------------------------------------------------------------------------------------------------------------

(2) O programa desenvolvido para classificar arquivos de processos judiciais fornecidos na disciplina. Assume que os arquivos tratados estão comprimidos em um arquivo zip, presente em um Google Drive que deve ser acoplado (mount no primeiro retângulo da figura abaixo) quando solicitado pelo programa. Na figura, o diretório onde estão os arquivos judiciais é armazenado na variável zirDir.

![test image size](https://github.com/MateusGilbert/topicos_SD/blob/main/pictures/Screenshot_2020-11-17%20Google%20Colaboratory.png)

Alguns parâmetros devem ser ajustados (além da rede lstm bidirecional):

  (i) quatidade de páginas de cada arquivo em pdf que são convertidas em arquivo texto (default = 2 páginas);

![test image size](https://github.com/MateusGilbert/topicos_SD/blob/main/pictures/Screenshot_2020-11-17%20Google%20Colaboratory(1).png)

  (ii) quantidade de palavras (que não são stopwords) que servem de entrada para a rede Bi-LSTM (default = 1000 palavras, o nome da variável é max_size).

Dada a demora para converter os arquivos pdf em txt, utilizando o tesseract ocr, o programa salva os arquivos textos resultantes em uma pasta do diretório fornecido (veja a figura abaixo).

![test image size](https://github.com/MateusGilbert/topicos_SD/blob/main/pictures/Screenshot_2020-11-17%20Google%20Colaboratory(2).png)

Na sua atual configuração, o programa procura classificar os arquivos utilizados no treinamento de acordo com os campos listados antes de fornece-los para o treinamento da rede neural. Basicamente, este conta a frequência de aparições de cada termo no texto, classificando o arquivo no campo onde os termos em questão aparecem mais.

![test image size](https://github.com/MateusGilbert/topicos_SD/blob/main/pictures/Screenshot_2020-11-17%20Google%20Colaboratory(3).png)
