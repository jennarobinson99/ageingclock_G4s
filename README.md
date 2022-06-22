# ageingclock_G4s
## In this repo we learn about G4S 
The first part of this repo involves this code: 

`git show 721b71
git reset --soft HEAD^
git reset try_this`

`git reset --soft HEAD^`
`for SRR in $(awk 'NR>1 { print $8 }' sample_info_hacat.txt)`

```
for SRR in $(awk 'NR>1 { print $8 }' sample_info_hacat.txt)
do
fastq-dump $SRR
done

#rename all files 
for file in *.fasta 
do 
	name=`basename $file .fasta`
	x=`grep $name sample_info_hacat.txt|awk '{print $1}'`
	mv $file $x.fasta 
done
#make fake files for practice 
for SRR in $(awk 'NR>1 { print $8 }' sample_info_hacat.txt) 
do  
 touch $SRR.fasta
done
```
