.. role:: raw-html-m2r(raw)
   :format: html


Input files
-----------

KleborateModular takes genome assemblies in FASTA format (can be gzipped). It will work on either draft or completed assemblies, though completed is better because it reduces the risk of fragmented genes/loci.

If you have unassembled reads, you will need to assemble them before running Kleborate. You can try our `Unicycler <https://github.com/rrwick/Unicycler>`_ assembler which works great on Illumina or hybrid Illumina + Nanopore/PacBio reads. Or check out this `guide to bacterial genome assembly <https://github.com/rrwick/Trycycler/wiki/Guide-to-bacterial-genome-assembly>`_.

Full usage options
------------------

.. code-block::


   ./kleborate-runner.py [-a ASSEMBLIES [ASSEMBLIES ...]] [-o OUTFILE] [--list_modules] [-p PRESET] [-m MODULES] [--abst_min_identity ABST_MIN_IDENTITY]
                              [--abst_min_coverage ABST_MIN_COVERAGE] [--abst_required_exact_matches ABST_REQUIRED_EXACT_MATCHES] [--cbst_min_identity CBST_MIN_IDENTITY]
                              [--cbst_min_coverage CBST_MIN_COVERAGE] [--cbst_required_exact_matches CBST_REQUIRED_EXACT_MATCHES]
                              [--escherichia_mlst_achtman_min_identity ESCHERICHIA_MLST_ACHTMAN_MIN_IDENTITY] [--escherichia_mlst_achtman_min_coverage ESCHERICHIA_MLST_ACHTMAN_MIN_COVERAGE]
                              [--escherichia_mlst_achtman_required_exact_matches ESCHERICHIA_MLST_ACHTMAN_REQUIRED_EXACT_MATCHES]
                              [--escherichia_mlst_pasteur_min_identity ESCHERICHIA_MLST_PASTEUR_MIN_IDENTITY] [--escherichia_mlst_pasteur_min_coverage ESCHERICHIA_MLST_PASTEUR_MIN_COVERAGE]
                              [--escherichia_mlst_pasteur_required_exact_matches ESCHERICHIA_MLST_PASTEUR_REQUIRED_EXACT_MATCHES] [--klebsiella_species_strong KLEBSIELLA_SPECIES_STRONG]
                              [--klebsiella_species_weak KLEBSIELLA_SPECIES_WEAK] [--kosc_mlst_min_identity KOSC_MLST_MIN_IDENTITY] [--kosc_mlst_min_coverage KOSC_MLST_MIN_COVERAGE]
                              [--kosc_mlst_required_exact_matches KOSC_MLST_REQUIRED_EXACT_MATCHES] [--kpsc_amr_min_identity KPSC_AMR_MIN_IDENTITY] [--kpsc_amr_min_coverage KPSC_AMR_MIN_COVERAGE]
                              [--kpsc_amr_min_spurious_identity KPSC_AMR_MIN_SPURIOUS_IDENTITY] [--kpsc_amr_min_spurious_coverage KPSC_AMR_MIN_SPURIOUS_COVERAGE]
                              [--kpsc_mlst_min_identity KPSC_MLST_MIN_IDENTITY] [--kpsc_mlst_min_coverage KPSC_MLST_MIN_COVERAGE]
                              [--kpsc_mlst_required_exact_matches KPSC_MLST_REQUIRED_EXACT_MATCHES] [--rmst_min_identity RMST_MIN_IDENTITY] [--rmst_min_coverage RMST_MIN_COVERAGE]
                              [--rmst_required_exact_matches RMST_REQUIRED_EXACT_MATCHES] [--smst_min_identity SMST_MIN_IDENTITY] [--smst_min_coverage SMST_MIN_COVERAGE]
                              [--smst_required_exact_matches SMST_REQUIRED_EXACT_MATCHES] [--ybst_min_identity YBST_MIN_IDENTITY] [--ybst_min_coverage YBST_MIN_COVERAGE]
                              [--ybst_required_exact_matches YBST_REQUIRED_EXACT_MATCHES] [-h] [--help_all] [--version]

   Kleborate: a tool for characterising virulence and resistance in pathogen assemblies

   Input/output:
     -a ASSEMBLIES [ASSEMBLIES ...], --assemblies ASSEMBLIES [ASSEMBLIES ...]
                                           FASTA file(s) for assemblies
     -o OUTFILE, --outfile OUTFILE         File for detailed output (default: Kleborate_results.txt)

   Modules:
     --list_modules                        Print a list of all available modules and then quit (default: False)
     -p PRESET, --preset PRESET            Module presets, choose from: kpsc, kosc, escherichia
     -m MODULES, --modules MODULES         Comma-delimited list of Kleborate modules to use

   abst module:
     --abst_min_identity ABST_MIN_IDENTITY
                                           Minimum alignment percent identity for aerobactin MLST (default: 90.0)
     --abst_min_coverage ABST_MIN_COVERAGE
                                           Minimum alignment percent coverage for aerobactin MLST (default: 80.0)
     --abst_required_exact_matches ABST_REQUIRED_EXACT_MATCHES
                                           At least this many exact matches are required to call an ST (default: 3)

   cbst module:
     --cbst_min_identity CBST_MIN_IDENTITY
                                           Minimum alignment percent identity for colibactin MLST (default: 90.0)
     --cbst_min_coverage CBST_MIN_COVERAGE
                                           Minimum alignment percent coverage for colibactin MLST (default: 80.0)
     --cbst_required_exact_matches CBST_REQUIRED_EXACT_MATCHES
                                           At least this many exact matches are required to call an ST (default: 8)

   escherichia_mlst_achtman module:
     --escherichia_mlst_achtman_min_identity ESCHERICHIA_MLST_ACHTMAN_MIN_IDENTITY
                                           Minimum alignment percent identity for Escherchia-Achtman MLST (default: 90.0)
     --escherichia_mlst_achtman_min_coverage ESCHERICHIA_MLST_ACHTMAN_MIN_COVERAGE
                                           Minimum alignment percent coverage for Escherchia-Achtman MLST (default: 80.0)
     --escherichia_mlst_achtman_required_exact_matches ESCHERICHIA_MLST_ACHTMAN_REQUIRED_EXACT_MATCHES
                                           At least this many exact matches are required to call an ST (default: 3)

   escherichia_mlst_pasteur module:
     --escherichia_mlst_pasteur_min_identity ESCHERICHIA_MLST_PASTEUR_MIN_IDENTITY
                                           Minimum alignment percent identity for Escherchia-Pasteur MLST (default: 90.0)
     --escherichia_mlst_pasteur_min_coverage ESCHERICHIA_MLST_PASTEUR_MIN_COVERAGE
                                           Minimum alignment percent coverage for Escherchia-Pasteur MLST (default: 80.0)
     --escherichia_mlst_pasteur_required_exact_matches ESCHERICHIA_MLST_PASTEUR_REQUIRED_EXACT_MATCHES
                                           At least this many exact matches are required to call an ST (default: 4)

   klebsiella_species module:
     --klebsiella_species_strong KLEBSIELLA_SPECIES_STRONG
                                           Mash distance threshold for a strong species match (default: 0.02)
     --klebsiella_species_weak KLEBSIELLA_SPECIES_WEAK
                                           Mash distance threshold for a weak species match (default: 0.04)

   kosc_mlst module:
     --kosc_mlst_min_identity KOSC_MLST_MIN_IDENTITY
                                           Minimum alignment percent identity for KoSC MLST (default: 90.0)
     --kosc_mlst_min_coverage KOSC_MLST_MIN_COVERAGE
                                           Minimum alignment percent coverage for KoSC MLST (default: 80.0)
     --kosc_mlst_required_exact_matches KOSC_MLST_REQUIRED_EXACT_MATCHES
                                           At least this many exact matches are required to call an ST (default: 3)

   kpsc_amr module:
     --kpsc_amr_min_identity KPSC_AMR_MIN_IDENTITY
                                           Minimum alignment percent identity for KpSC Amr results (default: 90.0)
     --kpsc_amr_min_coverage KPSC_AMR_MIN_COVERAGE
                                           Minimum alignment percent coverage for KpSC Amr results (default: 80.0)
     --kpsc_amr_min_spurious_identity KPSC_AMR_MIN_SPURIOUS_IDENTITY
                                           Minimum alignment percent identity for KpSC Amr spurious results (default: 80.0)
     --kpsc_amr_min_spurious_coverage KPSC_AMR_MIN_SPURIOUS_COVERAGE
                                           Minimum alignment percent coverage for KpSC Amr spurious results (default: 40.0)

   kpsc_mlst module:
     --kpsc_mlst_min_identity KPSC_MLST_MIN_IDENTITY
                                           Minimum alignment percent identity for KpSC MLST (default: 90.0)
     --kpsc_mlst_min_coverage KPSC_MLST_MIN_COVERAGE
                                           Minimum alignment percent coverage for KpSC MLST (default: 80.0)
     --kpsc_mlst_required_exact_matches KPSC_MLST_REQUIRED_EXACT_MATCHES
                                           At least this many exact matches are required to call an ST (default: 3)

   rmst module:
     --rmst_min_identity RMST_MIN_IDENTITY
                                           Minimum alignment percent identity for Rmp MLST (default: 90.0)
     --rmst_min_coverage RMST_MIN_COVERAGE
                                           Minimum alignment percent coverage for Rmp MLST (default: 80.0)
     --rmst_required_exact_matches RMST_REQUIRED_EXACT_MATCHES
                                           At least this many exact matches are required to call an ST (default: 2)

   smst module:
     --smst_min_identity SMST_MIN_IDENTITY
                                           Minimum alignment percent identity for salmochelin MLST (default: 90.0)
     --smst_min_coverage SMST_MIN_COVERAGE
                                           Minimum alignment percent coverage for salmochelin MLST (default: 80.0)
     --smst_required_exact_matches SMST_REQUIRED_EXACT_MATCHES
                                           At least this many exact matches are required to call an ST (default: 2)

   ybst module:
     --ybst_min_identity YBST_MIN_IDENTITY
                                           Minimum alignment percent identity for yersiniabactin MLST (default: 90.0)
     --ybst_min_coverage YBST_MIN_COVERAGE
                                           Minimum alignment percent coverage for yersiniabactin MLST (default: 80.0)
     --ybst_required_exact_matches YBST_REQUIRED_EXACT_MATCHES
                                           At least this many exact matches are required to call an ST (default: 2)

   Help:
     -h, --help                            Show this help message and exit
     --help_all                            Show a help message with all module options
     --version                             Show program's version number and exit

Basic usage
-----------

**list available modules for Kleborate:**\ :raw-html-m2r:`<br>`

.. code-block:: bash

   ./kleborate-runner.py --list_modules

**run KleborateModular to analyse Klebsiella Species complex (Kpsc):**\ :raw-html-m2r:`<br>`

.. code-block:: bash

   ./kleborate-runner.py  -a *.fasta -o results.txt -p kpsc

**run KleborateModular to analyse Escherichia coli species:**\ :raw-html-m2r:`<br>`

.. code-block:: bash

   ./kleborate-runner.py  -a *.fasta -o results.txt -p escherichia

**Screen  a set of gzipped assemblies:**\ :raw-html-m2r:`<br>`

.. code-block:: bash

   kleborate  -a *.fasta.gz -o results.txt -p kpsc
