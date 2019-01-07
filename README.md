# NLP
NLP

from nltk.tag import CRFTagger
 
jumSample = 500000
namaFile = "C:\\Users\Asus_Pc\Downloads\idn-tagged-corpus-master\Indonesian_Manually_Tagged_Corpus.tsv "
with open(namaFile, 'r', encoding='utf-8') as f:
    lines = f.read().split('\n')
 
pasangan = []
allPasangan = []
 
for line in lines[: min(jumSample, len(lines))]:
    if line == '':
        allPasangan.append(pasangan)
        pasangan = []
    else:
        kata, tag = line.split('\t')
        p = (kata,tag)
        pasangan.append(p)
 
ct = CRFTagger()
ct.train(allPasangan,'all_indo_man_tag_corpus_model.crf.tagger')
hasil = ct.tag_sents([['Saya','kuliah','di','Jogja'],['Nama','saya','Dewi']])
print(hasil)

import nltk
from nltk.tokenize import word_tokenize
tes = ('Saya kuliah di UII')
cek = nltk.word_tokenize(tes)
coba = ct.tag(cek)
print(coba)

import nltk
from nltk.tokenize import word_tokenize
tes = ('Saya kuliah di UII')
cek = nltk.word_tokenize(tes)
coba = ct.tag(cek)
print(coba)
