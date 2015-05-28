# GenAnnc
Working Repo for the Genome Announcement Projects

We're writing genome announcements for the following groups:
- betI (Lhab and Rhodo)
- betII (Pnec)
- betIIV (LD28)

## Submission Journal Info
Targeting Standards in Genomic Science for publication,
[SIGS](http://www.standardsingenomics.com/)

Article type: [Short Genome Report](http://www.standardsingenomics.com/authors/instructions/shortgenomereport)

[Document template](http://media.biomedcentral.com/content/editorial/templates/ShortGenomeReportTemplate.docx)

Supplemnetal info [(Old, non-working link)](http://standardsingenomics.org/index.php/sigen/pages/view/migstable) - can't find a current working link, but it should be a "MIGS record"

## Relevant Google Docs
[Summary stats (added csv version to this repo)](https://docs.google.com/spreadsheets/d/1SREBGNmXNHlnqmJbpZNnJWh-MGHG2OgPUyRfdBG0z68/edit?usp=sharing)

[GFM tracking google document](https://docs.google.com/spreadsheets/d/1NqxTV87yZwEZpvgwfTc3ky8YNoGdDxkpfQJMh2-gY0c/edit#gid=1387774424)

[SAG tracking google document](https://docs.google.com/spreadsheets/d/1-xh5pnCx5vbJmlcFvMHZ8l3kLCLWDAqbA_CxdjA14e4/edit#gid=0)

## Places to look for additional genomes:
Lhab genomes from old set of bins. These need to be manually curated:
- MEint.metabat.1062
- MEint.metabat.7043
- MEint.metabat.7618
- MEint.metabat.16806
- MEint.metabat.12185
- MEint.metabat.10739
- MEint.metabat.7618
- MEint.metabat.3080

## Other curation required:
Several of the beta-SAGs may need some more decontamination because they were originally screened by Sarah in 2013.  Trina emailed Tanja and Miranda to ask if it is possible to get them screened using their new pipeline.  Tanja said we can download their decontamination pipeline and run it locally, then resubmit to IMG.

Josh has obtained ProDeGe from IMG and run the SAGs through it.  We are unsure if the given taxonomy from the user input effects the results.  
Tested this by changing the taxonomic level we specified and resubmitting.  
Also going to send email to be sure we understand how ProDeGe is working.  
Found from testing that the taxonomy doesn't make a difference between genus and family.  Will just take the screened version and resubmit to IMG as an analysis project.  Then in the manuscript, put a link to both the unscreened and screened version.

### Random note to followup on:  
While re-reading the original SAG paper from Ramunas' group, I noticed they found some pufM and BchlY genes in Polynucleobacter SAGs.  This is odd because the reference genome for Pnec does not have them. LIkely a clade/lake specificity thing?  Would be need to look at both our Pnec SAG and GFMs to see if they have them (they are indicators of photoheterotrophy).  Actually, never mind.  The strain MWH-MoK4 genome has pufM (it wasn't published in 2011 when Ramunas published). Josh and Sarah vote not to look into this issue. We are publishing genome announcements, not genome analyses.
