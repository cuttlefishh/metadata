## Python notebooks and scripts for handling EMP metadata

### Metadata exploration and refinement

`emp20k_metadata_explore.ipynb`
<https://github.com/cuttlefishh/metadata/blob/master/emp20k_metadata_explore.ipynb>

`emp20k_metadata_refine.ipynb`
<https://github.com/cuttlefishh/metadata/blob/master/emp20k_metadata_refine.ipynb>

Inputs

* Individual Qiime mapping files (list of studies and path to directory)
* NCBI taxonomy files (names.dmp)
* EMP Ontology data dictionary (.xlsx)
* Study titles and quality information (.xlsx)

Outputs

* Merged un-refined all columns of Qiime mapping files plus EMPO ontology (.tsv)
* Merged refined select columns of Qiime mapping files (.tsv)
* Individual refined select columns of Qiime mapping files (.tsv)
* List of studies with number of samples by sample type (.tsv)

### Metadata template generator

`metadata_template_generator.md` (ipynb in markdown format)
<https://github.com/biocore/emp/blob/master/ipynb/metadata_template_generator.md>

`metadata_template_generator.py` (python executable)
<https://github.com/biocore/emp/blob/master/ipynb/metadata_template_generator.py>

Generates metadata templates consistent with instructions on [EMP website](http://www.earthmicrobiome.org/emp500/emp-metadata-guide-new/), similar to instructions on [Qiita website](https://qiita.ucsd.edu/static/doc/html/tutorials/prepare-information-files.html#sample-information-file).

Python executable:

	$ metadata_template_generator.py --help
	
	Usage: metadata_template_generator.py [OPTIONS]
	
	  Generate metadata template and readme csv files
	
	Options:
	  --qiita_ebi_mims_path PATH   Excel file with Qiita/EBI and MIMS required
	                               fields. Example: Qiita_EBI_MIMS_v1.xlsx
	                               [required]
	  --migs_mims_path PATH        Excel file with MIxS standards. Example:
	                               MIGS_MIMS_v4.xls  [required]
	  --list_of_env_pkg TEXT       One (recommended) or more (separated by commas)
	                               environmental package. Choose from: air, built
	                               environment, host-associated, human-associated,
	                               human-skin, human-oral, human-gut, human-
	                               vaginal, microbial mat/biofilm, misc
	                               environment, plant-associated, sediment, soil,
	                               wastewater/sludge, water  [required]
	  --number_of_samples INTEGER  Number of samples (per environmental package)
	                               to create rows for in the template  [required]
	  --sample_prefix TEXT         Prefix string to prepend to sample numbers in
	                               row indexes. Example: Metcalf40 (EMP500 PI and
	                               study number)  [required]
	  --help                       Show this message and exit.

Example:

	$ metadata_template_generator.py \
		--qiita_ebi_mims_path ~/git/emp/data/MIxS/Qiita_EBI_MIMS_v1.xlsx \
		--migs_mims_path ~/git/emp/data/MIxS/MIGS_MIMS_v4.xls \
		--list_of_env_pkg host-associated \
		--number_of_samples 20 \
		--sample_prefix Thomas19

Issues:

* Still need to decide how to record units.
* Text input is all free text.

### Future: web-based metadata input with contextual input (smart type detection and graphical metadata feedback)


