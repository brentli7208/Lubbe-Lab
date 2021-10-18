# LubbeLab
/projects/b1049/brent/AMP-PD_2021 Explanation

Look in relation to /projects/b1049/brent/scripts/bash_scripts/AMPPD_pipeline.sh

Base Files:

chr1.vcf.gz and chr1.vcf.gz.tbi are the original nonfiltered VCF files of AMPPD in chromosome 1

chr1_filtering_commandline.txt is the filtering code first used by Bernabe

releases_2020_v2release_1218_amp-pd-participants.csv is a list of all the individuals within the cohort

releases_2020_v2release_1218_amp_pd_case_control.csv has diagnosis and case/control status at baseline and at a more recent time (more important)

releases_2020_v2release_1218_amp_pd_participant_mutations.csv shows whether an individual has a known GBA mutation, LRRK2 mutation, SNCA mutation, or PD mutation in WGS (file not used)

releases_2020_v2release_1218_clinical_Clinically_Reported_Genetic_Status.csv and releases_2020_v2release_1218_clinical_Clinically_Reported_Genetic_Status_dictionary.csv show genetic status of individuals based off PD-associated mutations or WGS-selected PD-associated variants.

chr1.vcf.gz is the original AMPPD chr1 VCF file

chr1_GBA_extract_commandline.txt has the code to extract GBA from the chr1 file to allow working with a smaller file and outputs into AMPPD_GBA.vcf

AMPPD_GBA_filtering_commandline.txt has the code for filtering. Originated from chr1_filtering_commandline.txt. Filtering log is slurm-6086548.out. Output is AMPPD_GBA.OnlyPASS_DP20_GQ20_CR90.MultiSplit.SNPsInDels.RawID.bcftools.June2021.vcf.gz

multianno.txt and multianno.vcf files were annotated but the vcf is what I used for plink and onward

AMPPD_variant.vcf were extracted from AMPPD_GBA_Anno.hg38_multianno.vcf to create single variant plink files

AMPPD_variant_noncarriers.txt are homozygous individuals for reference gene

AMPPD_variant_carriers.txt contain heterozygous and homozygous individuals for alternative gene

AMPPD_variant_nocalls.txt have individuals with no known genotype (0 0)

AMPPD_variant_homozy.txt have homozygous individuals for alternative genes

AMPPD_cases.txt and AMPPD_controls.txt have individuals that are either cases or controls extracted from releases_2020_v2release_1218_amp_pd_case_control.csv

AMPPD_homozy.txt are all homozygous individuals

AMPPD_variant_carriers_nohomozy.txt are files without homozygous individuals for each variant

AMPPD_homozy_cases.txt and AMPPD_homozy_controls.txt show which homozygous individuals are cases versus controls

AMPPD_variant_noncarriers_cases.txt, AMPPD_variant_noncarriers_controls.txt, AMPPD_variant_carriers_cases.txt, and AMPPD_variant_carriers_controls.txt are stratified individuals per variant

AMPPD_noncarriers_cases_duplicates.txt and AMPPD_noncarriers_controls_duplicates.txt show individuals that are noncarriers for one variant but a carrier for another variant

AMPPD_noncarriers_cases.txt and AMPPD_noncarriers_controls.txt have all individuals without variants in all locations

AMPPD_carriers_cases.txt and AMPPD_carriers_controls.txt have all individuals with only one variant

AMPPD_carriers_cases_duplicates.txt and AMPPD_carriers_cases_duplicates.txt have individuals with multiple variants in different locations (2 or more). Files with only the individuals' name is in AMPPD_2allele_cases.txt and AMPPD_2allele_controls.txt

AMPPD_no2_variant_carriers_cases.txt and AMPPD_no2_variant_carriers_controls.txt show which individuals had mutations in another variant.

AMPPD_brent_.Covars_Pheno_carriership_noncar_cases.txt, AMPPD_brent_.Covars_Pheno_carriership_noncar_controls.txt, AMPPD_brent_.Covars_Pheno_carriership_car_cases.txt, and AMPPD_brent_.Covars_Pheno_carriership_car_controls.txt have pheno files with the carriership (1=noncarrier, 2=carrier) added. All of these files were joined into AMPPD_brent_Covars_Pheno_carriership.txt

tabix_chr1-22.OnlyPASS_DP20_GQ20_CR90.MultiSplit.SNPsInDels.RawID.bcftools.April2021.PD_CC_QCedIndiv.MAF01.CandidateVars.CADD12.37.vcf.gz took filtered file and removed "chr" from 1st column (CHROM).

tabix_chr1-22.OnlyPASS_DP20_GQ20_CR90.MultiSplit.SNPsInDels.RawID.bcftools.April2021.PD_CC_QCedIndiv.MAF01.CandidateVars.CADD12.37.vcf.gz.tbi is the tabix indexed file to allow for rvtest to run.

AMPPD_2021_wCovs_analyses.SkatO.assoc, AMPPD_2021_wCovs_analyses.SingleFirth.assoc, and AMPPD_2021_wCovs_analyses.CMCFisherExact.assoc have the results of the three separate tests (kernel SKAT-O, single Firth, and burden exactCMC respectively) The analysis log for all three tests are within AMPPD_2021_wCovs_analyses.log.
