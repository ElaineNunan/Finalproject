codes file
================

Fastq \<- readFastq(raw_data.fq.gz)

for Fastq

do

bowtie2 -p 30 -x AG.genome.fa -1 \$Fastq -S \$Fastq.sam

samtools view -bS \$Fastq.sam \> \$Fastq.bam

samtools sort \$Fastq.bam -o \$Fastq.sorted.bam

rm \$name.sam \$name.bam

genomeCoverageBed -ibam \$Fastq.sorted.bam -g AG.genome.fa -bg \>
\$Fastq.bg

bedtools sort -i \$Fastq.bg \> \$Fastq.sorted.bg

bedGraphToBigWig \$Fastq.sorted.bg AG.genome.chrom.sizes \$Fastq.bw

done

Fastq \<- readFastq(Ascaris_24hr_IP.fq.gz)

for Fastq

do

bowtie2 -p 30 -x AG.genome.fa -1 \$Fastq -S \$Fastq.sam

samtools view -bS \$Fastq.sam \> \$Fastq.bam

samtools sort \$Fastq.bam -o \$Fastq.sorted.bam

rm \$name.sam \$name.bam

genomeCoverageBed -ibam \$Fastq.sorted.bam -g AG.genome.fa -bg \>
\$Fastq.bg

bedtools sort -i \$Fastq.bg \> \$Fastq.sorted.bg

bedGraphToBigWig \$Fastq.sorted.bg AG.genome.chrom.sizes \$Fastq.bw

done

Ascaris_24hr_IP.bg

Ascaris_24hr_IP.bw

Ascaris_24hr_IP.sorted.bam

Ascaris_24hr_IP.sorted.bg
