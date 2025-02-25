# **SARS-CoV-2 Sequencing Resources**

This document repository is meant to serve as the start of a crowd-sourced collection of information, documentation, protocols and other resources for public health laboratories intending to sequence SARS-CoV-2 coronavirus samples in the coming weeks. This is admittedly a limited first draft, but will continued to collate useful information as additional protocols, tools, and resources are added, and as best practices are identified. While some of the resources here are directed specifically to US state and local public health laboratories in support of diagnostic testing, sequencing and response, we hope that this is a useful resource for the global laboratory community, as we respond to this pandemic threat.

This collection is maintained and curated by [Duncan MacCannell](https://www.twitter.com/dmaccannell) from the Office of Advanced Molecular Detection ([AMD](https://www.cdc.gov/amd)) at the Centers for Disease Control and Prevention ([CDC](https://www.cdc.gov)). Please feel free to suggest additions, edits, clarifications and corrections -- either by posting an issue, filing a pull request or by contacting me directly by email or twitter.  In the meantime, I'll continue to add and mirror useful resources here as they become available.

*Disclaimer*
> The findings and conclusions in this document and the attendant repository are those of the author and do not necessarily represent the official position of the Centers for Disease Control and Prevention. Use of trade names is for identiﬁcation only and does not imply endorsement by the Centers for Disease Control and Prevention or by the U.S. Department of Health and Human Services.


---


# **Sequencing Protocols**

## _**1. OXFORD NANOPORE**_
The following sequencing protocols, checklists and job-aids are primarily designed for the Oxford Nanopore [MinION](https://nanoporetech.com/products/minion), and have been kindly shared by research groups throughout the world (please see individual protocols for attribution and citing purposes). Even so, most of these protocols should scale to larger ONT instruments without significant modifications.

### a) CDC NCIRD/DVD ONT Sequencing Protocol
This protocol was developed, tuned and validated by the Viral Discovery laboratory at CDC/NCIRD, where it was used to generate the first 16 SARS-CoV-2 genome sequences from the United States. In practice, it has been used for situations with a relatively low or predictable volume of samples, and is often used in conjunction with Sanger-based tiling to resolve any potential sequencing or assembly issues.
- Release pending CDC clearance.

### b) [ARTIC Network nCoV-2019 Sequencing Protocol](https://artic.network/ncov-2019)
This protocol was developed and released by the fine folks at [ARTIC Network](https://artic.network), and was subsequently refined based on comments from [Itokawa et al](https://www.biorxiv.org/content/10.1101/2020.03.10.985150v1.full.pdf), which identified potential issues and proposed an alternate L18 primer.

- [Sequencing protocol](https://www.protocols.io/view/ncov-2019-sequencing-protocol-bbmuik6w) / [Single sample sequencing protocol](https://www.protocols.io/view/ncov-2019-sequencing-protocol-single-sample-bdbfi2jn)

- [Stepwise simplified protocol from ONT*](./protocols/ONT-COVID-19_Tiling)

- Primer schemes: [V1](https://github.com/artic-network/artic-ncov2019/tree/master/primer_schemes/nCoV-2019/V1) / [V2](https://github.com/artic-network/artic-ncov2019/tree/master/primer_schemes/nCoV-2019/V2) [(ref)](https://www.biorxiv.org/content/10.1101/2020.03.10.985150v1.full.pdf)

- Integrated bioinformatics (RAMPART) - documentation below under bioinformatics methods.

### c) Doherty Institute VIDRL Sequencing Protocols
The Victorian Infectious Diseases Reference Laboratory ([VIDRL](https://www.vidrl.org.au/)) at the [Peter Doherty Institute for Infection and Immunity](https://www.doherty.edu.au/) released two protocols for the ONT MinION, which they successfully used to sequence early Australian SARS-CoV-2 samples.
- [Native RNA Sequencing Protocol](./protocols/ONT-Native_RNA) [(ref)](https://www.biorxiv.org/content/10.1101/2020.03.05.976167v1.full.pdf)

- [SISPA Sequencing Protocol](./protocols/ONT-SISPA)

## _**2. ILLUMINA**_
### a) Illumina Nextera Flex Enrichment Sequencing Protocol
Illumina's Research and Development group has recently developed and validated a custom, research use only (RUO) enrichment sequencing strategy based on their Nextera Flex chemistry.
- Release imminent.

### b) SARS-CoV-2 Enrichment Sequencing by Spiked Primer MSSPE (NIAID/UCSF/CZBioHub)
The NIAID laboratory team in Cambodia, in collaboration with UCSF, CZBioHub and IPC, has released a metagenomic sequencing with spiked primer enrichment (MSSPE) protocol for SARS-CoV-2. The protocol is available on [protocols.io](https://protocols.io).
- [MSSPE Protocol](https://www.protocols.io/view/sars-cov-2-enrichment-sequencing-by-spiked-primer-bc36iyre)

### c) Illumina Shotgun Metagenomics Sequencing Protocol
Illumina's technical note on sequencing coronavirus samples using a comprehensive metagenomic sequencing approach was one of the earlier protocols released for SARS-CoV-2, and remains an effective option for shotgun sequencing.
- [Application Note](https://www.illumina.com/content/dam/illumina-marketing/documents/products/appnotes/ngs-coronavirus-app-note-1270-2020-001.pdf)

## _**3. TANDEM**_
### a) SARS-CoV-2 Parallel Sequencing by Illumina and ONT (UWMadison ZEST)
Staff and students from Thomas Friedrich and Dave O'Connor's laboratories at UWMadison have put together a tandem sequencing protocol and bioinformatic workflow that incorporates Illumina and ONT sequence. While this may be overkill for routine or high-throughput public health purposes, the necessary protocols, scripts and documentation are available here.
- [Protocol](https://openresearch.labkey.com/wiki/ZEST/Ncov/page.view?name=SARS0CoV-2%20Deep%20Sequencing)
- [Github resources](https://github.com/katarinabraun/SARS-CoV-2_sequencing)

## _**4. SANGER**_
### a) CDC NCIRD/DVD Sanger Tiling
An elegant approach from a more civilized age. The Viral Discovery laboratory team in CDC/NCIRD/DVD has used conventional Sanger sequencing to refine and complement betacoronavirus sequencing on next generation platforms.
- Release pending CDC clearance.
---


# **Bioinformatics Tools, Scripts and Workflows**

### 1. CDC NCIRD/DVD Bioinformatics SOPs
This section describes the basic bioinformatic workflow that the Viral Discovery laboratory in NCIRD, and other teams at CDC use for quality assessment, assembly and comparison of coronavirus sequences. IRMA, the Iterative Refinement Meta-Assembler developed by CDC's Influenza Division for routine influenza surveillance, has recently been updated to support both ebolavirus and coronavirus assembly tasks. While IRMA isn't used for all SARS-CoV-2 assemblies at CDC, it is a powerful tool for complex or problematic samples and datasets.
- Release of scripts and other tools is pending CDC clearance.
- [IRMA: Iterative Refinement Meta-Assembler](https://wonder.cdc.gov/amd/flu/irma) is available here.

### 2. CLCbio Genomics Workbench
QIAGEN CLCbio will be releasing a set of CLCbio SARS-CoV-2 workflows that have been optimized for Illumina, ONT and IonTorrent sequencing platforms.  More information, download instructions and tutorials will be available within the next several days.
- SARSCoV2 Assembly/Analysis Tutorial and FAQs (Illumina/ONT/Ion data) - TBD

### 3. ARTIC Network Bioinformatics
The [ARTIC Network](https://artic.network) has released detailed instructions on how to setup and configure the conda environment needed to run their analysis pipelines. These are complete bioinformatic workflows, including runtime visualization, basecalling, mapping/assembly and reporting in a single, portable environment. The [artic-nCoV2019](https://github.com/artic-network/artic-ncov2019) repo includes source code and build instructions for a custom RAMPART configuration.  Additional instructions and documentation are available below.

- [Bioinformatics Environment Setup/Configuration](https://artic.network/ncov-2019/ncov2019-it-setup.html)

- [SARS-CoV-2 Bioinformatics SOP](https://artic.network/ncov-2019/ncov2019-bioinformatics-sop.html)

- [RAMPART Runtime Documentation](https://artic.network/ncov-2019/ncov2019-using-rampart.html)

- [Nextflow ARTIC nCoV Workflows - Connor Lab Cardiff/PHW](https://github.com/connor-lab/ncov2019-artic-nf)

### 4. One Codex
[One Codex](https://www.onecodex.com) has added support to its analysis platform for analyzing SARS-CoV-2 samples. This analysis ([example](https://app.onecodex.com/report/public/2b15c38901224e5f)) will be automatically run on any samples with SARS-CoV-2 reads. One Codex is making analysis of SARS-CoV-2 samples available **free of charge** for all users sharing their results and data publicly. Additional information and documentation are available below:

- [Blog post introducing COVID-19 analysis support](https://www.onecodex.com/blog/2020/03/16/covid-19-sequencing-analysis/)

- [An example report](https://app.onecodex.com/report/public/2b15c38901224e5f)

- [Additional documentation and bioinformatics details](https://docs.onecodex.com/en/articles/3793936-covid-19-sequencing-analysis)

### 5. Broad viral-ngs tools
The Broad Institute's viral genomics analysis tools can assist with assembly, metagenomics, QC, and NCBI submission prep, for Illumina-generated data on viral genomes. It is available in the following forms:

- The Terra cloud platform ([workspace](https://app.terra.bio/#workspaces/pathogen-genomic-surveillance/COVID-19) including example SARS-CoV-2 data from SRA, [blog post](https://support.terra.bio/hc/en-us/articles/360040613432), [getting started](https://support.terra.bio/hc/en-us/articles/360041068771)) 
- The DNAnexus cloud platform ([workflows](https://platform.dnanexus.com/projects/F8PQ6380xf5bK0Qk0YPjB17P/data/build/quay.io/broadinstitute/viral-pipelines/2.0.11.0-rc23))
- The Dockstore tool repository service - integrates with several cloud platforms, or download to run on-prem ([workflows](https://dockstore.org/organizations/BroadInstitute/collections/pgs))
- Github ([workflows](https://github.com/broadinstitute/viral-pipelines/tree/master/pipes/WDL))

The tools include:
- denovo and reference based assembly
- short read alignment and coverage plots
- krakenuniq metagenomic classification
- NCBI: SRA download, Genbank annotation download, Genbank submission prep
- multiple alignment of genomes w/MAFFT
- Illumina basecalling & demux, metrics, fastQC, ERCC spike-in counter

---

# **Quality Management**
This section will describe best practices for laboratory and bioinformatic quality assurance, including preflight checks for sequence and metadata submission to public repositories.
- **to do**: I'd love for people to help describe their actual QC processes.

---


# **Submitting to Public Sequence Repositories**

## Sequence naming conventions for public repositories
We are proposing simplified naming conventions for sequences submitted to GISAID and NCBI from US public health and clinical laboratories.

**COUNTRY** | /  **STATE-LAB-SAMPLE**  / | **YEAR**
--- | --- | ---
`USA` | ``/ CA-CDPH-S1 /`` | `2020`
`USA` | ``/ UT-01 /`` | `2020`
`USA` | ``/ AZ-1045 /`` | `2020`
`USA` | ``/ WA-UW-316 /`` | `2020`

> The proposed convention is as follows: 1) country (USA). 2) The middle sample identification cell should include two-letter state (eg: CA), an abbreviated identifier for the submitting lab (eg: CDPH), as desired, and a unique sequence identifier (eg:01, S01, 454, ...), with all three terms separated by hyphens.




For states with only one submitting laboratory (which should be most), the identifier for the submitting laboratory may be omitted, resulting in a simple, state-level identifier such as `USA/UT-573/2020`.

*These recommendations are roughly compatible with existing submissions to GISAID and NCBI, but are completely open for debate.*

## Recommended formatting and criteria for sample metadata

### [NCBI SARS-CoV-2 Genbank/SRA](https://www.ncbi.nlm.nih.gov/genbank/sars-cov-2-seqs/)
The National Center for Biotechnology has established a custom landing page for SARS-CoV-2 sequences and data, and is working to develop streamlined submission processes for Genbank and SRA.  For the time being, we suggest basing metadata and submission formatting on GISAID EpiCoV, which tends to be more comprehensive and structured. We will develop specific guidance for NCBI submissions.  In the meantime, here are some resources to help with NCBI data submission and metadata management.

#### 1. NCBI Submission Portal
Individual sequences can be submitted to NCBI using the following web form. Create an NCBI user account, and select "SARS-CoV-2 (through BankIt)".
- [Genbank Submission Portal](https://www.ncbi.nlm.nih.gov/WebSub/)

#### 2. NCBI Batch Submissions
NCBI has indicated that they plan to develop a specific rapid submission process for SARS-CoV-2 sequences. In the meantime, I believe you should be able to follow the FDA/CFSAN submission protocol below, which includes links to appropriate interfaces and templates (with obvious changes for pathogen and project information).

#### 3. FDA/CFSAN NCBI Submission and Data Curation Protocols
The Center for Food Safety and Applied Nutrition ([CFSAN](https://www.fda.gov/about-fda/fda-organization/center-food-safety-and-applied-nutrition-cfsan)) at FDA has released a number of protocols as part of the [GenomeTrakr Network](https://www.fda.gov/food/whole-genome-sequencing-wgs-program/genometrakr-network) that may be useful for NCBI sequence submission and metadata curation.

- [NCBI submission protocol for microbial pathogen surveillance](https://www.protocols.io/view/ncbi-submission-protocol-for-microbial-pathogen-su-9aph2dn)
- [Populating the NCBI pathogen metadata template](https://www.protocols.io/view/populating-the-ncbi-pathogen-metadata-template-bck3iuyn)
- NCBI Data Curation - Pending release

### [GISAID EpiCoV](https://www.gisaid.org/)

The GISAID EpiCoV Public Access repository is based on existing submission processes and data structures for large-scale influenza surveillance (GISAID EpiFlu). As such, submitters to EpiCoV will discover that several of the required metadata submission fields may be problematic.  Nonetheless, a number of laboratories have been submitting sequences with the following:

METADATA FIELDS (GISAID) | GUIDANCE
--- | ---
`Virus name`| USA/FL-103/2020 (see above)
`Accession ID` |
`Type` | betacoronavirus
`Collection date`| YYYY-MM-DD
`Location` | USA / State / County?
`Additional location information` |
`Host` | Human
`Additional host information` |
`Gender` | (no guidance)
`Patient age`| (no guidance, could be binned)
`Patient status` | (no guidance)
`Specimen source` | (free text)
`Outbreak detail` | omit
`Last vaccinated` | omit
`Treatment` | omit

At a minimum, we suggest that samples be submitted with `collection date` `location` `host` information attached.  `location`, `host`, `gender` `patient age` are all required fields, and several of them likely constitute personally-identifiable information. While they cannot be left blank for submission, you can submit the record successfully (in both single or batch mode) by entering "**unknown**".

Note that for GISAID submissions, users must register for an account, and must successfully submit a single submission before being granted access to the bulk submission template and interface.

---


# **Linking Sequence Accessions**
For data linkage, we are proposing the following template, as a simple, lightweight line list of tab-separated values. If this consensus recommendation for data linkage is acceptable, a preformatted .TSV will be made available. We recognize that not all samples sent for sequencing have a PUID associated.

SEQUENCE_NAME | GISAID_ID | GENBANK_ID | COLLECTION_DATE | PUID/COVID-ID
--- | --- | --- | --- | ---
USA/CA-CDPH-999/2020 | EPI_ISL_999999 | MT99999999 | 2020-04-01 | 99999

In this simple proposed schema, GISAID ID or GENBANK ID and COLLECTION DATE are required fields, and our hope is to maximize PUID completion.  All accession numbers, including PUID should be entered without any superfluous text or annotation.

---


# **Other Useful References and Resources**

### [Nextstrain hCoV-19](https://www.nextstrain.org/ncov)
### [Virological Novel 2019 Coronavirus forum](http://virological.org/c/novel-2019-coronavirus)
### [CNCB 2019 Novel Coronavirus Resource (2019nCoVR)](https://bigd.big.ac.cn/ncov?lang=en)

---
# **Notices and Disclaimers**
## Public Domain

This repository constitutes a work of the United States Government and is not
subject to domestic copyright protection under 17 USC § 105. This repository is in
the public domain within the United States, and copyright and related rights in
the work worldwide are waived through the [CC0 1.0 Universal public domain dedication](https://creativecommons.org/publicdomain/zero/1.0/).
All contributions to this repository will be released under the CC0 dedication. By
submitting a pull request you are agreeing to comply with this waiver of
copyright interest.

## License

Unless otherwise specified, the repository utilizes code licensed under the terms of the Apache Software
License and therefore is licensed under ASL v2 or later.

This source code in this repository is free: you can redistribute it and/or modify it under
the terms of the Apache Software License version 2, or (at your option) any
later version.

This source code in this repository is distributed in the hope that it will be useful, but WITHOUT ANY
WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A
PARTICULAR PURPOSE. See the Apache Software License for more details.

You should have received a copy of the Apache Software License along with this
program. If not, see http://www.apache.org/licenses/LICENSE-2.0.html

Any source code forked from other open source projects will inherit its license.

## Privacy

This repository contains only non-sensitive, publicly available data and
information. All material and community participation is covered by the
Surveillance Platform [Disclaimer](https://github.com/CDCgov/template/blob/master/DISCLAIMER.md)
and [Code of Conduct](https://github.com/CDCgov/template/blob/master/code-of-conduct.md).
For more information about CDC's privacy policy, please visit [http://www.cdc.gov/privacy.html](http://www.cdc.gov/privacy.html).

## Contributing

Anyone is encouraged to contribute to the repository by [forking](https://help.github.com/articles/fork-a-repo)
and submitting a pull request. (If you are new to GitHub, you might start with a
[basic tutorial](https://help.github.com/articles/set-up-git).) By contributing
to this project, you grant a world-wide, royalty-free, perpetual, irrevocable,
non-exclusive, transferable license to all users under the terms of the
[Apache Software License v2](http://www.apache.org/licenses/LICENSE-2.0.html) or
later.

All comments, messages, pull requests, and other submissions received through
CDC including this GitHub page are subject to the [Presidential Records Act](http://www.archives.gov/about/laws/presidential-records.html)
and may be archived. Learn more at [http://www.cdc.gov/other/privacy.html](http://www.cdc.gov/other/privacy.html).

## Records

This repository is not a source of government records, but is a copy to increase
collaboration and collaborative potential. All government records will be
published through the [CDC web site](http://www.cdc.gov).

---

Updated: 20200317 [@dmaccannell](https://www.twitter.com/dmaccannell)
