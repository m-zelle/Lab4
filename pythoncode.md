---
layout: page
title: Lab 4 code
subtitle: here is my code for lab 4! 
bigimg: /img/start.jpg
---


```
#1. open and read a given fasta file
#I started by making a dictionary (called Data) to read from the FASTA file and "define" the sequences
Data={}
SeqName=""
Sequence=""
with open("Lab4.FASTA") as fp: #the file i used for the code is called "Lab4.FASTA"
	for line in fp: #reading the file one line at a time
		entry = line 
		entry = entry.strip()
		if entry.startswith('>'): #defining the sequence name
			entry = entry.replace('>','') #naming the sequence
			SeqName=entry #save the sequence name in the dictionary "Data"
		elif not entry.startswith('>'): #defining the sequence data
			Sequence = entry #save sequence to the dictionary
			Data[SeqName] = Sequence #link sequence name to sequence data
#for other files, replace "Lab4.FASTA" in the code with the name of your file

#2. determine nucleotide frequency for each sequence
for items in Data: #applies the following code to the Data dictionary
	seqLen = len(items) #length of each sequence (which should be the same length)
	for key,value in Data.items(): 
		print ('A Frequency: ', value.count('A')/seqLen, file=open('Lab4Results.txt', 'a'))
		print ('T Frequency: ', value.count('T')/seqLen, file=open('Lab4Results.txt', 'a'))
		print ('G Frequency: ', value.count('G')/seqLen, file=open('Lab4Results.txt', 'a'))
		print ('C Frequency: ', value.count('C')/seqLen, file=open('Lab4Results.txt', 'a'))
		print ('', file=open('Lab4Results.txt', 'a'))
#the above code counts the number of nucleotides (e.g. 'A') in the "value" or sequence
#and then divides by the total sequence/value length
#the part at the end of each line and the last line (29) should open the printed values in a new file
	totalLen = len(value)
	print ('Total A Frequency: ', value.count('A')/totalLen, file=open('Lab4Results.txt', 'a'))
	print ('Total T Frequency: ', value.count('T')/totalLen, file=open('Lab4Results.txt', 'a'))
	print ('Total G Frequency: ', value.count('G')/totalLen, file=open('Lab4Results.txt', 'a'))
	print ('Total C Frequency: ', value.count('C')/totalLen, file=open('Lab4Results.txt', 'a'))
	print ('', file=open('Lab4Results.txt', 'a'))
#this section is to find total frequencies in the entire file, not divided up by sequence

#3. compare transition rates and transversion rates--VALUES
	for key,value in Data.items(): #again, applies the following loop to the dictionary/FASTA file
		transitions=0 #we're counting the transitions in the loop, so before we look at the file there should be 0
		for x in range(0,len(Data)): #we're looking between the start through end of the value
			for i in Data[value] and for j in Data[value+1]: #comparing location "i" in one value and then the subsequent value
				if i=='A' and j=='G':
					transitions=transitions+1
				elif i=='G' and j=='A':
					transitions=transitions+1
				elif i =='C' and j=='T':
					transitions=transitions+1
				elif i=='T' and j=='C':
					transitions=transitions+1
		print ('Transition Count: ', transitions, file=open('Lab4Results.txt', 'a'))
		print ('', file=open('Lab4Results.txt', 'a'))
#the rest of the loop compares the positions in the two sequences and looks to see if there is a change in bases
#again, the last two lines print to the external file
	for key,value in Data.items():
		transversions=0
		for x in range(0,len(Data)):
			for i in Data[value] and for j in Data [value+1]:
				if i=='A' and j=='T':
					transversions=transversions+1
				elif i=='A' and j=='C':
					transversions=transversions+1
				elif i=='T' and j=='A':
					transversions=transversions+1
				elif i=='T' and j=='G':
					transversions=transversions+1
				elif i=='C' and j=='G':
					transversions=transversions+1
				elif i=='C' and j=='A':
					transversions=transversions+1
				elif i=='G' and j=='C':
					transversions=transversions+1
				elif i=='G' and j=='T':
					transversions=transversions+1
		print ('Transversion Count: ', transversions, file=open('Lab4Results.txt', 'a'))
		print ('', file=open('Lab4Results.txt', 'a'))
#this loop functions the same the transition loop but looking for different mismatches of bases
#proportion of transitions to transversions
		print ('Ratio of Transitions to Transverions:', transitions/transversions, file=open('Lab4Results.txt', 'a'))
		print ('', file=open('Lab4Results.txt', 'a'))


```
