---
layout: page
title: Lab 4 code
subtitle: here is my code for lab 4! 
bigimg: /img/start.jpg
---


```
#1. open and read a given fasta file


#the file i used for the code is called "Lab4.FASTA"
#for other files, replace "Lab4.FASTA" in the code with the name of your file
myDNASeq = 'ATGGATACCGATCGAGCGATCGATG'
myDNASeq2 = 'GTCAAACCTGATCCAGTGATCGAAC'
#2. determine nucleotide frequency for each sequence
#2a. first determine sequence lengths
SeqLength = float(len(myDNASeq))
#2b. then count number of each nucleotide in the sequence
NumA = myDNASeq.count('A')
NumT = myDNASeq.count('T')
NumC = myDNASeq.count('C')
NumG = myDNASeq.count('G')
#2c. divide number of each base by sequence length (2b/2a) to determine frequency, and print
print 'A Frequency: ', NumA/SeqLength
print 'T Frequency: ', NumT/SeqLength
print 'C Frequency: ', NumC/SeqLength
print 'G Frequency: ', NumG/SeqLength
#2d. apply the above steps to the rest of the sequences

#DO WORK HERE MIRAAAAAAA

#3. compare transition rates and transversion rates
#3a. transition rates
#I made a loop that counts transitions by comparing the DNA sequences, counting the number
#of transitions as defined in the loop, and then adds that number to the total transition count

transitions=0
for x in range(0,len(myDNASeq)):
	if myDNASeq[x]=='A' and myDNASeq2[x]=='G':
		transitions=transitions+1
	elif myDNASeq[x]=='G' and myDNASeq2[x]=='A':
		transitions=transitions+1
	elif myDNASeq[x]=='C' and myDNASeq2[x]=='T':
		transitions=transitions+1
	elif myDNASeq[x]=='T' and myDNASeq2[x]=='C':
		transitions=transitions+1
print 'Transition Count:', transitions

#3b. transversion rates
#I used the same loop as 3a but changed what it was counting to transversions
transversions=0
for x in range(0,len(myDNASeq)):
	if myDNASeq[x]=='A' and myDNASeq2[x]=='T':
		transversions=transversions+1
	elif myDNASeq[x]=='T' and myDNASeq2[x]=='A':
		transversions=transversions+1
	elif myDNASeq[x]=='C' and myDNASeq2[x]=='G':
		transversions=transversions+1
	elif myDNASeq[x]=='G' and myDNASeq2[x]=='C':
		transversions=transversions+1
print 'Transversion Count:', transversions
```
