* Modified source taken from https://github.com/pachterlab/kallisto

* To build follow the instructions given at https://pachterlab.github.io/kallisto/source.html

* License: http://pachterlab.github.io/kallisto/license.html

The functionality of this temporary kallisto version is identical to the original kallisto version 0.42.3 except for the new command "kallisto pseudoalign". The folder kallisto_pseudo_single contains the modifications for single-end reads\* and kallisto_pseudo_paired for paired-end. 
\**single-end bypasses the requirement to specify fragment length and sd, which are otherwise necessary for quantification.* 

##### Usage.

###### Single-end reads: 
 kallisto pseudoalign -i (path/to/kallisto_index_file) -o (path/to/output_file) (path/to/reads)

###### Paired-end reads: 
 kallisto pseudoalign -i (path/to/kallisto_index_file) -o (path/to/output_file) (path/to/paired_read1) (path/to/paired_read2)

##### Output.

Note that we require (path/to/output_file) and not (path/to/output_folder). The output file contains the transcript-compatibility counts corresponding to the reads that were provided in the input. In each line of the output kallisto pseudoalign reports the equivalence class id followed by the corresponding counts. In the case a read generates a new equivalence class that is not in the index, the equivalence class id is set to be the list of transcript ids in the new class. This is necessary so that one can keep track of new eq.classes generated from different cells, and generate the transcript-compatibility counts matrix.

