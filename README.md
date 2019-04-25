# vdb
very-dreamy-blastvdb: an easy to use wrapper for blastn_vdb and tblastn_vdb

## Objective
`blastn_vdb` and `tblastn_vdb` are new BLAST implementations from NCBI that use
one or more Sequence Read Archive (SRA)  accessions as nucleotide databases for
nucleotide or protein queries (respectively).

I created very-dreamy-blast as an easy to use wrapper around blast_vdb, with 
options provided by the user on each run, without having to change any 
parameters hidden in some bash script.

## Usage
`./run_vdb.sh -s SRX00001,[SRX00002],[...] -q QUERY_INPUT.FASTA -t nucl|prot [-e #] [-d] [-n]`

## Parameters & Options
*Required*:
`-s`: A comma-separated list of 1 or more SRA Accession(s) to build BLAST databases from

`-q`: A query file in FASTA format

`-t`: The type of query, 'nucl' or 'prot' (do not include the quotes)

*Optional*:
`-e`: e-value threshold for the BLAST search, in scientific notation. Default: `1e-9`

`-d`: By default, the blastn_vdb task is megablast (for most similar hits).
      If you would like to instead search for more divergent matches,
      you may use the `-d` flag to switch the task to `discontiguous-megablast`

`-n`: Similar to the `-d` flag, except it switches the BLAST task to `blastn`,
      which is optimized for somewhat similar hits.


