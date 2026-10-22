# QIIME-Compatible Databases 🧬

<p align="center">
  <a href="#choosing-primers-for-soil-and-plant-samples"><img alt="Focus: soil–plant–microbe" src="https://img.shields.io/badge/Focus-Soil%20%E2%80%A2%20Plant%20%E2%80%A2%20Microbe-8FBC8F?style=flat-square"></a>
  <a href="#database-downloads"><img alt="Resources: QIIME 2 artifacts" src="https://img.shields.io/badge/Resources-QIIME%202-96D6CF?style=flat-square"></a>
  <a href="https://earthmicrobiome.ucsd.edu/"><img alt="Earth Microbiome Project: website" src="https://img.shields.io/badge/Earth%20Microbiome%20Project-Explore-7FB685?style=flat-square"></a>
  <a href="https://earthmicrobiome.ucsd.edu/protocols-and-standards/16s/"><img alt="EMP: 16S protocol reference" src="https://img.shields.io/badge/EMP-16S%20protocol-89CFF0?style=flat-square"></a>
  <a href="https://earthmicrobiome.ucsd.edu/protocols-and-standards/its/"><img alt="EMP: ITS1 protocol reference" src="https://img.shields.io/badge/EMP-ITS1%20protocol-C3B1E1?style=flat-square"></a>
</p>


Reference resources for marker-gene analysis, with a curated primer catalogue for soil–plant–microbe research.

## 🧭 Contents

- [Scope and sequence conventions](#scope-and-sequence-conventions)
- [16S rRNA gene primers](#16s-rrna-gene-primers)
- [Fungal ITS1 primers](#fungal-its1-primers)
- [Fungal ITS2 primers](#fungal-its2-primers)
- [Full-ITS and additional primer variants](#full-its-and-additional-primer-variants)
- [Choosing primers for soil and plant samples](#choosing-primers-for-soil-and-plant-samples)
- [Other markers in this repository](#other-markers-in-this-repository)
- [Using primers with QIIME 2 resources](#using-primers-with-qiime-2-resources)
- [Hackflex and DNA extraction for shotgun metagenomics](#hackflex-and-dna-extraction-for-shotgun-metagenomics)
- [Database downloads](#database-downloads)
- [References](#references)

## Scope and sequence conventions

This is a **curated catalogue of established primer pairs**, not an exhaustive inventory of every published oligonucleotide or a claim that one pair captures all microorganisms. It focuses on community amplicon sequencing of bacterial/archaeal 16S rRNA genes and fungal ITS1/ITS2, including representative soil and plant-associated applications. Some supporting evaluations used 454 sequencing; successful use on that platform does not establish compatibility with every current library-preparation protocol.

- **Orientation:** every primer is written **5′→3′**, including reverse primers. Do not reverse-complement these sequences when ordering oligonucleotides.
- **Sequence content:** sequences are target-binding regions only; adapters, barcodes, linkers, spacers, and platform-specific modifications are excluded.
- **Names:** use the **name plus exact sequence and citation**. A name such as `515F`, `806R`, `27F`, or `ITS1FI2` does not uniquely identify a sequence.
- **Evidence:** “sequenced” means a published application recovered community sequences. It does **not** mean unbiased amplification, complete taxonomic coverage, or validation in every host. *In silico* coverage (predicted primer matching) is distinct from experimental recovery.
- **Lengths:** approximate 16S PCR-product lengths include the biological primer-binding sites and exclude adapters. Actual lengths vary; primer position labels are not exact product-length calculations. ITS lengths vary particularly strongly among taxa.
- **Specificity:** broad-range bacterial primers need not cover archaea well. Fungal-selective primers can still miss fungal lineages or amplify non-fungal DNA.

### Degenerate bases

Degenerate bases specify mixtures of nucleotides; inosine is a separate chemical base.

| Code | Bases | Code | Bases |
| --- | --- | --- | --- |
| R | A/G | Y | C/T |
| M | A/C | K | G/T |
| S | G/C | W | A/T |
| B | C/G/T | D | A/G/T |
| H | A/C/T | V | A/C/G |
| N | A/C/G/T | I | Inosine; not an IUPAC nucleotide-mixture code |

## 16S rRNA gene primers

### Broad bacterial/archaeal and bacterial survey options

| Primer pair | Forward sequence, 5′→3′ | Reverse sequence, 5′→3′ | Target; approximate product | Evidence and interpretation |
| --- | --- | --- | --- | --- |
| **515F (Parada) / 806R (Apprill)**; often called 515F-Y/806RB | `GTGYCAGCMGCCGCGGTAA` | `GGACTACNVGGGTWTCTAAT` | V4; ~290 bp | Updated EMP pair; bacterial and archaeal coverage. Evaluated in managed soils against metagenome-derived 16S sequences. [[1](#ref-1), [2](#ref-2), [3](#ref-3)] |
| **515F / 806R, original Caporaso versions** | `GTGCCAGCMGCCGCGGTAA` | `GGACTACHVGGGTWTCTAAT` | V4; ~290 bp | Established historical versions. Do not conflate with the updated pair: degeneracy changes affect coverage. [[1](#ref-1), [2](#ref-2)] |
| **515F (Parada) / 926R (Quince)** | `GTGYCAGCMGCCGCGGTAA` | `CCGYCAATTYMTTTRAGTTT` | V4–V5; ~410 bp | Bacterial/archaeal option, also capable of amplifying eukaryotic 18S. Evaluated in marine communities and managed soils. [[2](#ref-2), [3](#ref-3), [4](#ref-4)] |
| **341F / 785R**, Klindworth versions; reverse also reported as 805R | `CCTACGGGNGGCWGCAG` | `GACTACHVGGGTATCTAATCC` | V3–V4; ~440–465 bp | Strong bacterial soil/rhizosphere option in comparative studies. This exact pair is not a substitute for a broadly archaeal-inclusive assay. Plant organelles can dominate tissue libraries. [[5](#ref-5), [6](#ref-6), [7](#ref-7)] |
| **338F / 806R**, versions shown | `ACTCCTACGGGAGGCAGCAG` | `GGACTACHVGGGTWTCTAAT` | V3–V4; ~460–470 bp | Successfully used in agricultural-soil sequencing. Interpret primarily as a bacterial survey; verify archaeal coverage if required. [[8](#ref-8)] |

The updated 515F/806R primers address known coverage limitations of the original versions, but are not bias-free [[1](#ref-1), [2](#ref-2), [3](#ref-3), [4](#ref-4)]. A longer 16S target is not automatically more representative: the two EMP pairs produced different recoveries in managed soils [[3](#ref-3)].

### Plant-associated and alternative bacterial options

| Primer pair | Forward sequence, 5′→3′ | Reverse sequence, 5′→3′ | Target; approximate product | Evidence and interpretation |
| --- | --- | --- | --- | --- |
| **799F / 1193R** | `AACMGGATTAGATACCCKG` | `ACGTCATCCCCACCTTCC` | V5–V7; ~400 bp | Sequenced from rhizosphere and plant tissues. Chloroplast-discriminating 799F reduces host amplification, with taxonomic trade-offs and possible mitochondrial products. [[6](#ref-6), [7](#ref-7)] |
| **799F / 1391R** | `AACMGGATTAGATACCCKG` | `GACGGGCGGTGWGTRCA` | Approximately positions 799–1391; ~600 bp | Successfully evaluated across poplar compartments. Longer product requires a suitable read strategy and inspection of non-target products. [[6](#ref-6)] |
| **967F / 1391R** | `CAACGCGAAGAACCTTACC` | `GACGGGCGGTGWGTRCA` | Approximately positions 967–1391; ~425 bp | Sequenced in soil/plant comparisons; strongly affected by host amplification in poplar tissues. [[6](#ref-6), [7](#ref-7)] |
| **68F / 518R** | `TNANACATGCAAGTCGRRCG` | `WTTACCGCGGCTGCTGG` | V1–V3; ~450 bp | Published comparator with substantial coverage/taxonomic limitations. Retained for interpreting existing studies, rather than as a preferred new broad survey. [[6](#ref-6), [7](#ref-7)] |
| **27F / 1492R**, degenerate versions shown | `AGRGTTYGATYMTGGCTCAG` | `RGYTACCTTGTTACGACTT` | Near-full-length 16S; ~1,450–1,500 bp | Successfully used with PacBio in bulk/root-associated soil and root samples. Bacterial-targeted; other 27F/1492R variants are not interchangeable. [[9](#ref-9)] |
| **Arch519F / Arch915R** | `CAGCCGCCGCGGTAA` | `GTGCTCCCCCGCCAATTCCT` | Archaeal 16S; ~400 bp | Published archaeal-targeted sequencing in soil biocrusts. A separate assay for archaeal questions, with coverage requiring evaluation. [[10](#ref-10)] |

<details>
<summary>Additional published option: 341F / 783Rabc</summary>

Beckers et al. [[6](#ref-6)] evaluated `341F` (`CCTACGGGNGGCWGCAG`) with a **three-oligonucleotide reverse-primer mixture**, `783Rabc`:

| Component | Reverse sequence, 5′→3′ |
| --- | --- |
| 783Ra | `CTACCAGGGTATCTAATCCTG` |
| 783Rb | `CTACCGGGGTATCTAATCCCG` |
| 783Rc | `CTACCCGGGTATCTAATCCGG` |

These are the three mixture components, not three interchangeable spellings of one primer. Consult the original protocol for mixture preparation. The approach reduced some chloroplast amplification but did not eliminate host amplification across tissues [[6](#ref-6)].

</details>

## Fungal ITS1 primers

**ITS1 is the spacer between 18S and 5.8S rRNA genes.** The reverse primer named **ITS2** binds in 5.8S and is commonly used to amplify **ITS1**. A primer's name does not identify the amplified spacer by itself.

| Primer pair | Forward sequence, 5′→3′ | Reverse sequence, 5′→3′ | Published evidence and limitations |
| --- | --- | --- | --- |
| **ITS1F / ITS2** | `CTTGGTCATTTAGAGGAAGTAA` | `GCTGCGTTCTTCATCGATGC` | EMP ITS1 protocol and experimental soil-metabarcoding comparison. Established, but mismatches can underrepresent fungal groups. [[11](#ref-11), [12](#ref-12)] |
| **ITS1-F_KYO1 / ITS2_KYO1** | `CTHGGTCATTTAGAGGAASTAA` | `CTRYGTTCTTCATCGDT` | KYO design/evaluation and successful leaf-endophyte application. Useful candidate for plant-rich extracts; specificity is host dependent. [[13](#ref-13), [14](#ref-14)] |
| **ITS1-F_KYO2 / ITS2_KYO2** | `TAGAGGAAGTAAAAGTCGTAA` | `TTYRCTRCGTTCTTCATC` | Improved predicted fungal coverage; published soil sequencing includes a nested-PCR application. The nested workflow is part of that evidence and may introduce additional bias. [[13](#ref-13), [15](#ref-15)] |
| **BITS / B58S3** | `ACCTGCGGARGGATCA` | `GAGATCCRTTGYTRAAAGTT` | Developed/evaluated for high-throughput fungal profiling; subsequently applied in agricultural-soil sequencing. Does not guarantee quantitative recovery of all taxa. [[16](#ref-16), [17](#ref-17)] |
| **ITS1FI2 / ITS2** | `GAACCWGCGGARGGATCA` | `GCTGCGTTCTTCATCGATGC` | Successfully used for oak root-associated fungi. This is the sequence called ITS1 in the earlier version of this README; it differs from the classic White ITS1 primer. [[18](#ref-18)] |
| **ITS1FI2 / 5.8S**, version shown | `GAACCWGCGGARGGATCA` | `CGCTGCGTTCTTCATCG` | Published soil/root fungal sequencing in silver-fir nursery systems. The reverse sequence differs from standard ITS2. [[19](#ref-19)] |

Product lengths are taxon dependent. Check the expected distribution using appropriate reference sequences and the intended analysis workflow rather than assigning one universal ITS1 length.

## Fungal ITS2 primers

**ITS2 is the spacer between 5.8S and 28S rRNA genes.** These forward primers bind within 5.8S, while the reverse primers bind in the downstream large-subunit region.

| Primer pair | Forward sequence, 5′→3′ | Reverse sequence, 5′→3′ | Published evidence and limitations |
| --- | --- | --- | --- |
| **ITS3 / ITS4** | `GCATCGATGAAGAACGCAGC` | `TCCTCCGCTTATTGATATGC` | Classic pair evaluated experimentally in soil metabarcoding. Broad binding also permits non-fungal amplification; check host matches. [[12](#ref-12)] |
| **fITS7 / ITS4** | `GTGARTCATCGAATCTTTG` | `TCCTCCGCTTATTGATATGC` | Tested with artificial/natural communities and used in soil studies. Fungal-selective, but mismatches affect some groups, including some Mucorales. [[20](#ref-20), [21](#ref-21)] |
| **gITS7 / ITS4** | `GTGARTCATCGARTCTTTG` | `TCCTCCGCTTATTGATATGC` | More degenerate than fITS7; successful maize-rhizosphere application. Broader matching can increase non-fungal amplification. [[20](#ref-20), [22](#ref-22)] |
| **fITS9 / ITS4** | `GAACGCAGCRAAIIGYGA` | `TCCTCCGCTTATTGATATGC` | Artificial/natural-community evaluation and plant-associated sequencing. `I` denotes inosine and must be specified correctly when ordering. [[20](#ref-20), [23](#ref-23)] |
| **ITS86F / ITS4**, ITS86F version evaluated by Op De Beeck et al. | `GTGAATCATCGAATCTTTGAA` | `TCCTCCGCTTATTGATATGC` | Experimentally compared with ITS1F/ITS2 and ITS3/ITS4 in soil metabarcoding. Do not assume equivalent performance in all habitats. [[12](#ref-12)] |
| **ITS3_KYO2 / ITS4** | `GATGAAGAACGYAGYRAA` | `TCCTCCGCTTATTGATATGC` | Successfully used for agricultural-soil fungal communities. High fungal coverage and plant exclusion are different properties. [[13](#ref-13), [24](#ref-24)] |
| **ITS3_KYO2 / ITS4_KYO3** | `GATGAAGAACGYAGYRAA` | `CTBTTVCCKCTTCACTCG` | Successfully used in soil/peat sequencing; ITS4_KYO3 had low predicted land-plant coverage in the design study. That prediction is not a guarantee of host exclusion. [[13](#ref-13), [25](#ref-25)] |

### Important naming check: ITS1FI2 versus fITS7

Some published methods label the pair `GTGARTCATCGAATCTTTG` / `TCCTCCGCTTATTGATATGC` as “ITS1FI2/ITS2” [[26](#ref-26)]. **Those sequences correspond to fITS7/ITS4 and target ITS2**, whereas `GAACCWGCGGARGGATCA` / `GCTGCGTTCTTCATCGATGC` targets ITS1 [[18](#ref-18)]. Record sequences and binding sites when reconciling such reports; do not use the reported names alone to select trimming settings or infer the sequenced region.

## Full-ITS and additional primer variants

### Full ITS: ITS1–5.8S–ITS2

| Primer pair | Forward sequence, 5′→3′ | Reverse sequence, 5′→3′ | Interpretation |
| --- | --- | --- | --- |
| **ITS1F / ITS4** | `CTTGGTCATTTAGAGGAAGTAA` | `TCCTCCGCTTATTGATATGC` | Whole-ITS pair experimentally evaluated with fungal communities. Longer products can be underrepresented. [[20](#ref-20)] |
| **ITS1 / ITS4**, classic ITS1 | `TCCGTAGGTGAACCTGCGG` | `TCCTCCGCTTATTGATATGC` | Established full-ITS amplification/barcoding pair. Include plant co-amplification and length variation in assay validation. [[27](#ref-27)] |
| **ITS1-F_KYO2 / ITS4** | `TAGAGGAAGTAAAAGTCGTAA` | `TCCTCCGCTTATTGATATGC` | Published first-round amplification before ITS2 sequencing of roots/soil. This application does not establish unbiased direct full-ITS sequencing. [[28](#ref-28)] |

Full-ITS products are longer and highly variable. Use an appropriate long-read or explicitly validated short-read strategy; a successful PCR does not establish that paired reads can overlap for every taxon. Amplifying ITS1 and ITS2 separately produces two complementary marker datasets, not interchangeable ASV tables.

### Further variants

- **ITS1Fngs:** shortened forward sequence `GGTCATTTAGAGGAAGTAA`; see the UNITE primer resource and the published ITS1Fngs/ITS2 sequencing workflow [[27](#ref-27), [29](#ref-29)].
- **ITS4ngs:** a reported reverse binding sequence is `TCCTSCGCTTATTGATATGC`; versions with an additional 5′ T also occur. A gITS7/ITS4ngs rhizosphere application is documented in [[30](#ref-30)]. Record the full version used.
- **ITS4ngsUni:** reverse sequence `CCTSCSCTTANTDATATGC`; used with other forward primers in broader assays, including pea-root studies [[31](#ref-31)]. The forward partner determines the amplified span; this is not an independently validated substitute in every ITS4-based pair.

## Choosing primers for soil and plant samples

The following are **starting candidates for a pilot**, not universal rankings.

| Sample or objective | Candidates | What to evaluate |
| --- | --- | --- |
| Bulk soil/rhizosphere; bacteria plus archaea | Updated **515F/806R**; compare **515F/926R** if the longer target is useful | Coverage of important lineages, usable reads, and platform/read-length compatibility. [[1](#ref-1), [2](#ref-2), [3](#ref-3), [4](#ref-4)] |
| Bulk soil/rhizosphere; mainly bacteria | **341F/785R** | Coverage and reproducibility in the intended soil types. [[5](#ref-5), [6](#ref-6), [7](#ref-7)] |
| Root, stem, or leaf bacterial communities | **799F/1193R**, or a broad V4 assay with host-matched blocking clamps | Chloroplast/mitochondrial reads, bacterial coverage, non-target products, and host-specific performance. [[6](#ref-6), [32](#ref-32)] |
| General fungal ITS1 survey | **ITS1F/ITS2**, a **KYO** pair, or **BITS/B58S3** | Fungal lineages recovered, host reads, and length-dependent loss. [[11](#ref-11), [12](#ref-12), [13](#ref-13), [14](#ref-14), [15](#ref-15), [16](#ref-16), [17](#ref-17), [18](#ref-18), [19](#ref-19)] |
| General fungal ITS2 survey | **fITS7/ITS4**, **gITS7/ITS4**, or **ITS86F/ITS4** | Coverage versus non-target amplification; include fungal groups relevant to the hypothesis. [[12](#ref-12), [20](#ref-20)] |
| Plant-rich fungal extracts | Include **ITS1-F_KYO1/ITS2_KYO1** or **ITS3_KYO2/ITS4_KYO3** among candidates | Actual host exclusion and fungal recovery; database predictions alone are insufficient. [[13](#ref-13), [14](#ref-14), [25](#ref-25)] |
| Arbuscular mycorrhizal fungi (AMF) specifically | Add an AMF-focused assay such as **AMV4.5NF/AMDGR** targeting 18S | General ITS primers do not establish comprehensive AMF recovery; AMF-specific assays also have lineage biases. [[33](#ref-33)] |

**Host blocking.** PNA clamps (synthetic molecules that inhibit amplification of matching host sequences) can increase bacterial read recovery. Check clamp sequences against the host: a single mismatch can reduce blocking efficacy, and optimization may be required [[32](#ref-32)]. Clamps are not ordinary DNA amplification primers.

**Study design.** Where possible, use the same assay across compartments being compared. Otherwise primer effects and compartment effects become confounded. Pilot representative extracts from each compartment alongside extraction blanks, PCR negatives, and an appropriate mock community. Inspect non-target reads and amplification failures as well as sequencing depth. Avoid routine nested PCR unless its need and added biases have been assessed.

**Interpretation.** Amplicon read proportions are not direct cell, biomass, or activity measurements. Marker-copy variation, extraction, primer matching, PCR competition, and length-dependent recovery affect the result. A spike-in can support absolute-abundance estimation only under validated assumptions; it does not correct every taxon-specific amplification bias.

## Other markers in this repository

These entries retain the additional marker information from the original README. They are **not a systematic validation catalogue for functional-gene or AMF assays**. Confirm the original assay source, specificity, PCR conditions, and reference coverage before use. The nifH1/nifH2 labels and the NS31 label below correct naming issues in the original table.

| Marker | Forward primer; sequence, 5′→3′ | Reverse primer; sequence, 5′→3′ | Note |
| --- | --- | --- | --- |
| **acdS** | acdSF5: `GGCAACAAGMYSCGCAAGCT` | acdSR8: `CTGCACSAGSACGCACTTCA` | Names/sequences retained from the original README; assay provenance has not been independently established here. |
| **nifH** | nifH1: `TGYGAYCCNAARGCNGA` | nifH2: `ADNGCCATCATYTCNCC` | Established label orientation; successful rice root-associated application. [[34](#ref-34)] |
| **AMF 18S, original entry** | NS31: `TTGGAGGGCAAGTCTGGTGCC` | AMDGR: `CCCAACTATCCCTATTAATCAT` | Forward sequence is NS31, not “AMDGR_NS31” [[35](#ref-35)]. This row preserves the supplied pairing; it is not endorsed here as equivalent to AMV4.5NF/AMDGR. |
| **AMF 18S, published alternative** | AMV4.5NF: `AAGCTCGTAGTTGAATTTCG` | AMDGR: `CCCAACTATCCCTATTAATCAT` | Successfully sequenced from roots and rhizosphere soil. [[33](#ref-33)] |
| **nosZ** | nosZ1mod_f: `WCSYTSTTCMTSGAYAGCCAG` | nosZmod_R: `ATRTCGATSARCTGVKCRTTYTC` | Names/sequences retained from the original README; clade coverage and assay provenance have not been independently established here. |

## Using primers with QIIME 2 resources

**A primer catalogue and a trained classifier are different resources.** Listing a pair above does not establish that any linked classifier was trained for that pair. The download descriptions below are retained from the existing README; the linked artifact contents, provenance, versions, and availability have not been audited as part of this primer update.

1. **Inspect artifact metadata and provenance.** Filenames such as `reads.qza` do not establish the QIIME 2 semantic type (the artifact's declared data category), source database, or preprocessing history.
2. **Check the marker, database release, and taxonomic scope.** A fungal ITS classifier does not classify bacterial 16S or functional genes. Genus/species resolution depends on the marker and reference representation.
3. **For 16S, consider region-specific training.** Matching training sequences to the sequenced region can improve classification, but a region-specific classifier is not mandatory in every workflow. Check orientations and sequence lengths. [[36](#ref-36), [37](#ref-37)]
4. **For fungal ITS, do not automatically apply the 16S extraction recipe.** QIIME 2's classifier-training guidance recommends full-reference UNITE training; primer-based extraction can discard references that lack flanking binding sites. Check the intended workflow and database format. [[36](#ref-36)]
5. **Check software compatibility.** Serialized scikit-learn classifiers can be version specific; confirm compatibility with the installed QIIME 2 environment. [[37](#ref-37)]
6. **Trim actual assay sequences.** Match the oligonucleotides and adapter architecture used by the sequencing provider. Variable-length ITS data should not be forced into a single 16S-style fixed-length assumption.
7. **Validate before biological interpretation.** Use suitable controls and examine host/non-target reads, unclassified sequences, and relevant reference coverage. High read counts or a high classification confidence threshold do not demonstrate biological accuracy.


<a id="hackflex-and-dna-extraction-for-shotgun-metagenomics"></a>

## 🧬 Hackflex and DNA extraction for shotgun metagenomics

**Hackflex is a sequencing-library preparation method, not a DNA-extraction method.** Extraction releases and purifies DNA from the sample; library preparation converts that DNA into adapter-bearing fragments that can be sequenced. Shotgun metagenomics (sequencing DNA across the extracted community) differs from sequencing a targeted 16S or ITS amplicon.

### Origin and published evidence

**Gaio et al. (2022)** developed Hackflex at the University of Technology Sydney as a lower-cost modification of Nextera DNA Flex, now called Illumina DNA Prep. It uses diluted bead-linked transposomes (BLT; enzyme–adapter complexes attached to beads) and replacement reagents. The original work evaluated bacterial isolates spanning different GC contents [[38](#ref-38)].

**Goldman et al. (2024)** evaluated Hackflex with a defined microbial DNA mixture and mouse-fecal metagenomes. Community signatures were recovered, but abundance biases remained. Lower template concentrations performed better in their mock-community experiment; the authors explicitly did **not** test soil or water [[39](#ref-39)]. These results support a soil pilot, rather than a claim of comprehensive validation for soil fungi, plant endophytes, rare taxa, or metagenome-assembled genomes (MAGs; genomes reconstructed from mixed-community sequence data).

### Where Hackflex fits

| Stage | Purpose | Output |
| --- | --- | --- |
| 1. Sampling and preservation | Define the compartment and limit changes after collection | Documented soil, rhizosphere, or plant sample |
| 2. DNA extraction | Disrupt cells and remove sample/kit contaminants | Purified community DNA |
| 3. Input quality control | Measure usable DNA quantity, purity, and integrity | DNA suitable for the chosen library protocol |
| 4. Hackflex tagmentation | Fragment DNA and attach adapter sequences | Adapter-tagged DNA fragments |
| 5. Library amplification and indexing | Amplify fragments and add sample-identifying indices | Indexed sequencing library |
| 6. Cleanup, library QC, and pooling | Remove unwanted fragments and balance libraries | Sequencing-ready pool |
| 7. Sequencing and analysis | Recover reads, remove contaminants/host reads, and answer the biological question | Taxonomic/functional profiles and, where supported, assemblies/MAGs |

**No 515F/806R or ITS1/ITS2 marker-primer pair is used to target community DNA in ordinary shotgun library preparation.** Library PCR uses adapter/index primers. Hackflex does not replace DNA extraction, remove plant DNA, or measure microbial activity.

### DNA extraction: recommendations for soil–plant studies

The following are **planning recommendations**, not a single validated extraction SOP. Choose and document one kit/protocol version, and use its specified sample capacity and instrument settings. The enzyme dilution used for Hackflex is unrelated to the dilution of a soil lysate.

| Decision | Recommended approach | Why it matters |
| --- | --- | --- |
| Define the compartment | Separate bulk soil, root-adhering rhizosphere, root surface, and internal tissue according to the study question | Washing or surface sterilization changes the community being sampled |
| Choose extraction chemistry | Start with an inhibitor-removing environmental-DNA workflow for soil/rhizosphere; PowerSoil Pro is one candidate, not a universal best kit | Humic substances and co-extracted compounds can interfere with quantification and library enzymes |
| Standardize sample input | Homogenize appropriately and record the mass entering each extraction; stay within kit capacity | More soil can increase inhibitors without increasing usable DNA |
| Lyse the intended organisms | Pilot mechanical plus chemical lysis for the bacterial/fungal groups of interest | Insufficient disruption can miss resistant cells/spores; stronger disruption can increase DNA fragmentation |
| Record bead beating | Record bead composition, instrument, setting, duration, and temperature management | Settings are not interchangeable between instruments or extraction matrices |
| Remove inhibitors | Use the chosen protocol's inhibitor-removal and wash steps; assess cleanup on representative extracts | Repeated cleanup can also lose DNA and change recovered fragment distributions |
| Elute compatibly | Use a validated low-salt eluent; assess EDTA and carryover from extraction | Carryover can impair tagmentation or PCR |
| Include controls | Process extraction blanks, library blanks, and a suitable whole-cell mock community | A DNA-only standard tests library preparation, but does not test cell lysis or extraction bias |

A soil benchmark compared extraction workflows across five soil types and found differences in yield, purity, fragment length, and community recovery. Its miniaturized Illumina DNA Prep workflow was **not the same protocol as Hackflex** [[40](#ref-40)]. QIAGEN describes PowerSoil Pro as combining mechanical/chemical disruption with inhibitor removal [[42](#ref-42)]. Select extraction conditions based on the samples and the downstream objective, rather than on yield alone.

### Input DNA quality control

| Check | Practical interpretation before Hackflex |
| --- | --- |
| **Double-stranded DNA concentration** | Quantify with a suitable fluorometric assay, such as Qubit dsDNA HS for low concentrations. Do not substitute NanoDrop concentration for a dsDNA-specific measurement. |
| **Total DNA mass** | Calculate mass as concentration × volume added. Concentration alone is not the reaction input. Retain DNA for QC, repeats, and troubleshooting. |
| **Purity** | Inspect absorbance where concentration permits reliable measurement. Illumina DNA Prep guidance gives A260/A280 around 1.8–2.0 and A260/A230 around 2.0–2.2; these are screening guides, not independently established Hackflex pass/fail thresholds. |
| **Carryover** | Check for humic compounds, ethanol, detergents, phenol, salts, and EDTA. A good absorbance ratio does not prove that an extract is inhibitor-free. |
| **Integrity** | Examine a gel or fragment-analysis trace. Optimize lysis for community recovery while avoiding unnecessary degradation; do not assume that the highest molecular weight gives the most representative extraction. |
| **Plant DNA** | Qubit measures total dsDNA, including host DNA. A high yield from roots/leaves can therefore correspond to little microbial DNA. Estimate the host-read fraction in a pilot. |

The quantification, purity, and carryover guidance above draws on the **parent Illumina DNA Prep workflow** [[41](#ref-41)]. Its input range and normalization behaviour should not automatically be transferred to diluted-transposome Hackflex reactions.

### Published input values: examples, not universal specifications

| Source | Reported condition | How to interpret it |
| --- | --- | --- |
| Original Hackflex [[38](#ref-38)] | **10 ng DNA in 10 µL**, with **1:50 BLT dilution** | A published starting condition; use the complete matching buffer, stopping, washing, amplification, and cleanup protocol |
| Metagenomic evaluation [[39](#ref-39)] | Template concentrations from **0.15625 to 10 ng/µL**; better mock-community performance below 1 ng/µL in that experiment | This is template concentration, not a universal minimum input or a recommendation to dilute every soil extract to 0.15 ng/µL |

The original standard Hackflex reaction used **55°C for 15 minutes** for tagmentation. Published variants differ in washing, polymerase, PCR cycling, and size selection [[38](#ref-38)]. Record the exact variant; do not assemble an SOP by combining isolated settings from different versions. The original study reported substantial **library-reagent** savings, with further savings in a simplified variant; this does not establish current prices or equivalent savings for extraction and sequencing [[38](#ref-38)].

### Library preparation, QC, and the pilot

1. **Normalize input for the selected variant.** Use the measured dsDNA concentration and prescribed input volume. Do not add more DNA simply because a soil extraction yielded more.
2. **Tagment and stop according to that protocol.** Tagmentation simultaneously fragments DNA and adds adapter sequences. Use the specified BLT dilution and matched reaction chemistry.
3. **Amplify/index with the specified reagents.** Record polymerase and cycle number. Excess amplification can increase duplication and representation bias; do not assume the original cycle count suits every input.
4. **Clean and size-select as specified.** Inspect the resulting library trace for an appropriate distribution and short adapter products. Retain library size and concentration measurements; a visible PCR product alone is insufficient QC.
5. **Quantify and pool individually.** For an initial soil Hackflex pilot, assess each library and pool according to the sequencing facility's requirements. Do not assume the parent kit's high-input self-normalization applies.
6. **Evaluate sequence data before scaling.** Include distinct soil/plant matrices and low/high-yield extracts. Where feasible, prepare paired Hackflex and established comparator libraries from the same extracts. Compare host fraction, usable non-host reads, duplicates, contamination, taxonomic/functional consistency, and coverage—not yield alone.

**For root and leaf metagenomes:** host depletion is a separate experimental choice and can introduce recovery bias. Removing plant reads computationally does not recover sequencing capacity already spent on them. If genome reconstruction is the objective, assess library complexity and target-genome coverage in the pilot; successful taxonomic profiling does not guarantee sufficient coverage for MAGs.

**Short-read versus long-read objectives:** Hackflex is an Illumina-compatible fragmentation workflow. Preserve a separate DNA aliquot and use an appropriate extraction/library workflow if long-read sequencing is also planned.

### What to record in the Methods

Report the compartment; preservation; extracted sample mass; extraction kit/version and deviations; bead-beating conditions; elution; DNA quantity/purity/integrity; controls; exact Hackflex source and modifications; DNA mass and volume; BLT dilution; tagmentation conditions; polymerase/cycles; index scheme; cleanup/size-selection settings; library QC/pooling; sequencing platform/read configuration; and host/contaminant-filtering strategy. Report the pilot's observed performance rather than describing the method as unbiased.

**Scope of downstream resources:** the marker-gene classifiers linked elsewhere in this README are not general-purpose shotgun-metagenome classifiers. Select reference databases and analysis tools appropriate to shotgun reads, genes, and/or genomes.


<a id="database-downloads"></a>


## Database downloads

The following sections retain the repository's download links. Consult each artifact's provenance before selecting a resource for a particular marker, primer pair, or software environment.


## 18S QIIME-Compatible Database

The 18S QIIME-compatible database is designed for analyzing eukaryotic microbial communities using the 18S ribosomal RNA (rRNA) gene as a molecular marker. The database includes:
- **reads.qza**: Processed 18S rRNA gene sequence reads
- **taxa.qza**: Taxonomic annotations linked to the reads
- **classifier.qza**: Trained classifier for accurate taxonomic classification

[Download 18S Database](https://app.box.com/s/mkra9cc23pa6bcj0k7cq34picypfde2t) | [Alternative Link](https://drive.google.com/drive/folders/1mMpcjvaqcLxvewOjZ0oA5l5-KhydbgQR?usp=sharing)

---

## 16S QIIME-Compatible Database

The 16S QIIME-compatible database is tailored for exploring bacterial and archaeal communities, utilizing the 16S ribosomal RNA (rRNA) gene as a marker. The database includes:
- **reads.qza**: Processed sequence reads
- **taxa.qza**: Taxonomic annotations for the reads
- **classifier.qza**: Trained classifier for precise taxonomic assignments

[Download 16S Database](https://app.box.com/s/445pwsz06zvh9y7kpepp1phydu3e5heg) | [Alternative Link](https://drive.google.com/drive/folders/1mV6ijpE0wCZHfDMdqlZ0U0keDJSMQsgA?usp=sharing)

---

## ITS QIIME-Compatible Database

The ITS QIIME-compatible database is developed for analyzing fungal communities using the internal transcribed spacer (ITS) region as a DNA barcode. The database includes:

### UNITE-V10
- **reads.qza**: Processed ITS sequence reads
- **taxa.qza**: Taxonomic information associated with the reads
- **classifier.qza**: Trained classifier for accurate taxonomic classification

[Download UNITE-V10 ITS Database](https://app.box.com/s/09t2ijoxpvbrcavu2r88rzsqe4stwo3w) | [Alternative Link](https://drive.google.com/drive/folders/1OEtk7em_1Z7yhWSpW_xjsWroO8lnasg2?usp=sharing)

### UNITE-V9
- **reads.qza**: Processed ITS sequence reads
- **taxa.qza**: Taxonomic information associated with the reads
- **classifier.qza**: Trained classifier for accurate taxonomic classification

[Download UNITE-V9 ITS Database](https://app.box.com/s/fgqc1kc3feybaffjthfkb13ipkjwailt) | [Alternative Link](https://drive.google.com/drive/folders/14Kk_Z7t0W6uEWbc_q2pEVEnONFvU-m9e?usp=sharing)

---

## nifH QIIME-Compatible Database

The nifH QIIME-compatible database supports analysis of nitrogenase reductase (nifH) gene sequences associated with diazotrophs (organisms capable of nitrogen fixation). Detection of a nifH-like sequence alone does not establish nitrogen-fixing activity; homolog identity and reference coverage require evaluation. The database includes:
- **reads.qza**: Processed nifH gene sequence reads
- **taxa.qza**: Taxonomic annotations for the reads
- **classifier.qza**: Trained classifier for precise taxonomic assignments

[Download nifH Database](https://app.box.com/s/vg2jgh6b9beo1zlf07z8ijhr6mx13k2m) | [Alternative Link](https://drive.google.com/drive/folders/1mCp57YTcM17VhVGexGtV4d0C19W_bGqm?usp=sharing)

---

## acdS QIIME-Compatible Database

The acdS QIIME-compatible database targets sequences of the gene encoding 1-aminocyclopropane-1-carboxylate (ACC) deaminase. This enzyme degrades ACC, a precursor of plant ethylene; gene detection alone does not establish enzyme activity or a plant-growth-promoting phenotype. The database includes:
- **reads.qza**: Processed acdS gene sequence reads
- **taxa.qza**: Taxonomic annotations for the reads
- **classifier.qza**: Trained classifier for accurate taxonomic classification

[Download acdS Database](https://app.box.com/s/geb3bv6ocde8hsm231muqpdqxopucvom) | [Alternative Link](https://drive.google.com/drive/folders/1mFtpKfmqiMfKh9q7N55LUiTD_w6kD7bN?usp=sharing)

---

## Eukaryota QIIME-Compatible Database

The Eukaryota QIIME-compatible database is tailored for analyzing eukaryotic communities, utilizing various gene markers such as ITS & 18S rRNA. The database includes:
- **reads.qza**: Processed sequence reads for eukaryotic genes
- **taxa.qza**: Taxonomic annotations associated with the sequence reads
- **classifier.qza**: Trained classifier for precise taxonomic classification of eukaryotic sequences

[Download Eukaryota Database](https://app.box.com/s/15az6wudemhq1sz1uyjg1lsb346sd4ts) | [Alternative Link](https://drive.google.com/drive/folders/14QSEPlW68vLewDJ6PRqApr4uKmBiZ15V?usp=sharing)

---

## nosZ QIIME-Compatible Database

The nosZ QIIME-compatible database targets the gene encoding nitrous oxide reductase, which catalyses reduction of N₂O to N₂. Organisms carrying nosZ need not possess a complete denitrification pathway; check representation of nosZ clades I and II in the reference resource. The database includes:
- **reads.qza**: Processed nosZ gene sequence reads
- **taxa.qza**: Taxonomic annotations for the reads
- **classifier.qza**: Trained classifier for precise taxonomic assignments

[Download nosZ Database](https://app.box.com/s/vuvu76p9gv29m46q45nx8maoj5j3fvfs) | [Alternative Link](https://drive.google.com/drive/folders/12DSESzzPDJYWqcqQDXH0iQxF4OZOezli?usp=drive_link)

---

## References

Numbers in the catalogue identify sequence sources, experimental evaluations, or the explicitly described applications. A design paper and a successful environmental sequencing study provide different kinds of evidence.

1. <a id="ref-1"></a>**Earth Microbiome Project.** [16S Illumina Amplicon Protocol](https://earthmicrobiome.ucsd.edu/protocols-and-standards/16s/). Exact original/updated primer sequences and naming conventions.
2. <a id="ref-2"></a>**Walters et al. (2016).** Improved Bacterial 16S rRNA Gene (V4 and V4-5) and Fungal Internal Transcribed Spacer Marker Gene Primers for Microbial Community Surveys. [doi:10.1128/mSystems.00009-15](https://doi.org/10.1128/mSystems.00009-15).
3. <a id="ref-3"></a>**Zhao, Rodriguez & Martens-Habbena (2023).** Fine-scale evaluation of two standard 16S rRNA gene amplicon primer pairs for analysis of total prokaryotes and archaeal nitrifiers in differently managed soils. [doi:10.3389/fmicb.2023.1140487](https://doi.org/10.3389/fmicb.2023.1140487).
4. <a id="ref-4"></a>**Parada, Needham & Fuhrman (2016).** Every base matters: assessing small subunit rRNA primers for marine microbiomes with mock communities, time series and global field samples. [doi:10.1111/1462-2920.13023](https://doi.org/10.1111/1462-2920.13023).
5. <a id="ref-5"></a>**Klindworth et al. (2013).** Evaluation of general 16S ribosomal RNA gene PCR primers for classical and next-generation sequencing-based diversity studies. [doi:10.1093/nar/gks808](https://doi.org/10.1093/nar/gks808).
6. <a id="ref-6"></a>**Beckers et al. (2016).** Performance of 16s rDNA Primer Pairs in the Study of Rhizosphere and Endosphere Bacterial Microbiomes in Metabarcoding Studies. [doi:10.3389/fmicb.2016.00650](https://doi.org/10.3389/fmicb.2016.00650). See Table 1 for exact sequences and 783Rabc components.
7. <a id="ref-7"></a>**Thijs et al. (2017).** Comparative Evaluation of Four Bacteria-Specific Primer Pairs for 16S rRNA Gene Surveys. [doi:10.3389/fmicb.2017.00494](https://doi.org/10.3389/fmicb.2017.00494).
8. <a id="ref-8"></a>**Agricultural-soil application (2020).** Long-Term Chemical-Only Fertilization Induces a Diversity Decline and Deep Selection on the Soil Bacteria. [doi:10.1128/mSystems.00337-20](https://doi.org/10.1128/mSystems.00337-20).
9. <a id="ref-9"></a>**Soil/root application (2021).** Differential microbial assemblages associated with shikonin-producing Borage species in two distinct soil types. [doi:10.1038/s41598-021-90251-1](https://doi.org/10.1038/s41598-021-90251-1).
10. <a id="ref-10"></a>**Soil-biocrust application (2022).** A Comprehensive Network Integrating Signature Microbes and Crucial Soil Properties During Early Biological Soil Crust Formation on Tropical Reef Islands. [doi:10.3389/fmicb.2022.831710](https://doi.org/10.3389/fmicb.2022.831710).
11. <a id="ref-11"></a>**Earth Microbiome Project.** [ITS Illumina Amplicon Protocol](https://earthmicrobiome.ucsd.edu/protocols-and-standards/its/). ITS1F/ITS2 target-binding sequences and platform constructs.
12. <a id="ref-12"></a>**Op De Beeck et al. (2014).** Comparison and Validation of Some ITS Primer Pairs Useful for Fungal Metabarcoding Studies. [doi:10.1371/journal.pone.0097629](https://doi.org/10.1371/journal.pone.0097629).
13. <a id="ref-13"></a>**Toju et al. (2012).** High-Coverage ITS Primers for the DNA-Based Identification of Ascomycetes and Basidiomycetes in Environmental Samples. [doi:10.1371/journal.pone.0040863](https://doi.org/10.1371/journal.pone.0040863). KYO design, predicted coverage, and experimental PCR evaluation.
14. <a id="ref-14"></a>**Leaf-endophyte application (2020).** Leaf resistance traits influence endophytic fungi colonization and community composition in a South American temperate rainforest. [doi:10.1111/1365-2745.13314](https://doi.org/10.1111/1365-2745.13314).
15. <a id="ref-15"></a>**Soil application (2017).** Land-use types and soil chemical properties influence soil microbial communities in the semiarid Loess Plateau region in China. [Full text and methods](https://pmc.ncbi.nlm.nih.gov/articles/PMC5368647/).
16. <a id="ref-16"></a>**Bokulich & Mills (2013).** Improved Selection of Internal Transcribed Spacer-Specific Primers Enables Quantitative, Ultra-High-Throughput Profiling of Fungal Communities. [doi:10.1128/AEM.03870-12](https://doi.org/10.1128/AEM.03870-12).
17. <a id="ref-17"></a>**Agricultural-soil application (2024).** Incidence of resistance to ALS and ACCase inhibitors in Echinochloa species and soil microbial composition in Northern Italy. [doi:10.1038/s41598-024-59856-0](https://doi.org/10.1038/s41598-024-59856-0).
18. <a id="ref-18"></a>**Oak-root application (2017).** Habitat- and soil-related drivers of the root-associated fungal community of Quercus suber in the Northern Moroccan forest. [doi:10.1371/journal.pone.0187758](https://doi.org/10.1371/journal.pone.0187758).
19. <a id="ref-19"></a>**Soil/root application (2023).** Effects of nursery production methods on fungal community diversity within soil and roots of Abies alba Mill. [doi:10.1038/s41598-023-48047-y](https://doi.org/10.1038/s41598-023-48047-y).
20. <a id="ref-20"></a>**Ihrmark et al. (2012).** New primers to amplify the fungal ITS2 region – evaluation by 454-sequencing of artificial and natural communities. [doi:10.1111/j.1574-6941.2012.01437.x](https://doi.org/10.1111/j.1574-6941.2012.01437.x).
21. <a id="ref-21"></a>**Soil application (2023).** Slow soil enzyme recovery following invasive tree removal through gradual changes in bacterial and fungal communities. [doi:10.1111/1365-2745.14186](https://doi.org/10.1111/1365-2745.14186).
22. <a id="ref-22"></a>**Maize-rhizosphere application (2022).** Soil texture is a stronger driver of the maize rhizosphere microbiome and extracellular enzyme activities than soil depth or the presence of root hairs. [doi:10.1007/s11104-022-05618-8](https://doi.org/10.1007/s11104-022-05618-8).
23. <a id="ref-23"></a>**Plant-associated application (2025).** Interplay between host and environmental filters drives plant-associated microbiomes in the remote sub-Antarctic Kerguelen Islands. [doi:10.1186/s40793-025-00814-2](https://doi.org/10.1186/s40793-025-00814-2). Cited here for the fITS9/ITS4 assay.
24. <a id="ref-24"></a>**Soil application (2019).** Land Use Change and Water Quality Use for Irrigation Alters Drylands Soil Fungal Community in the Mezquital Valley, Mexico. [doi:10.3389/fmicb.2019.01220](https://doi.org/10.3389/fmicb.2019.01220).
25. <a id="ref-25"></a>**Soil/peat application (2016).** New Primers for Discovering Fungal Diversity Using Nuclear Large Ribosomal DNA. [Full text and ITS2 comparator methods](https://pmc.ncbi.nlm.nih.gov/articles/PMC4938210/).
26. <a id="ref-26"></a>**Example of inconsistent primer naming (2024).** Composition and the predicted functions of fungal communities and the key drivers in acidic soils of Jiaodong Peninsula, China. [doi:10.3389/fmicb.2024.1496268](https://doi.org/10.3389/fmicb.2024.1496268). Consult the reported sequences rather than adopting the labels.
27. <a id="ref-27"></a>**Primer resources.** [UNITE primer catalogue](https://unite.ut.ee/primers.php) and [Vilgalys laboratory fungal rDNA primer sequences](https://sites.duke.edu/vilgalyslab/rdna_primers_for_fungi/). These catalogues supplement, rather than replace, assay-specific experimental evidence.
28. <a id="ref-28"></a>**Root/soil application (2013).** Community composition of root-associated fungi in a Quercus-dominated temperate forest: “codominance” of mycorrhizal and root-endophytic fungi. [doi:10.1002/ece3.546](https://doi.org/10.1002/ece3.546).
29. <a id="ref-29"></a>**ITS1Fngs application (2020).** Comparison of the performance of ITS1 and ITS2 as barcodes in amplicon-based sequencing of bioaerosols. [Full text and tagged primer sequences](https://pmc.ncbi.nlm.nih.gov/articles/PMC7032056/). This application is not a soil-specific validation.
30. <a id="ref-30"></a>**Rhizosphere application (2026).** Climate and temporal variation in bacterial and fungal communities of the rhizosphere and roots of young avocado trees. [doi:10.1007/s00374-026-02033-4](https://doi.org/10.1007/s00374-026-02033-4).
31. <a id="ref-31"></a>**Root-associated application (2022).** Identification, pathogenicity and community dynamics of fungi and oomycetes associated with pea root rot in northern France. [doi:10.1111/ppa.13583](https://doi.org/10.1111/ppa.13583).
32. <a id="ref-32"></a>**Host-blocking evaluation (2018).** Chloroplast sequence variation and the efficacy of peptide nucleic acids for blocking host amplification in plant microbiome studies. [Full text](https://pmc.ncbi.nlm.nih.gov/articles/PMC6098832/).
33. <a id="ref-33"></a>**AMF application (2017).** The influence of environmental factors on communities of arbuscular mycorrhizal fungi associated with Chenopodium ambrosioides revealed by MiSeq sequencing investigation. [doi:10.1038/srep45134](https://doi.org/10.1038/srep45134).
34. <a id="ref-34"></a>**nifH application (2022).** Temporal dynamics of total and active root-associated diazotrophic communities in field-grown rice. [doi:10.3389/fmicb.2022.1016547](https://doi.org/10.3389/fmicb.2022.1016547).
35. <a id="ref-35"></a>**NS31 sequence source/application (2017).** Barcoded NS31/AML2 primers for sequencing of arbuscular mycorrhizal communities in environmental samples. [doi:10.3732/apps.1700017](https://doi.org/10.3732/apps.1700017). Cited for NS31 identity, not as evidence for the supplied NS31/AMDGR combination.
36. <a id="ref-36"></a>**QIIME 2.** [Training feature classifiers with q2-feature-classifier](https://docs.qiime2.org/2024.10/tutorials/feature-classifier/). Versioned guidance, including the fungal ITS note; consult the [current plugin documentation](https://amplicon-docs.qiime2.org/en/latest/references/plugins/feature-classifier/) for current interfaces.
37. <a id="ref-37"></a>**QIIME 2.** [Data resources](https://library.qiime2.org/data-resources). Region-specific/full-length classifier considerations and software compatibility.


---

<p xmlns:cc="http://creativecommons.org/ns#" xmlns:dct="http://purl.org/dc/terms/"><a property="dct:title" rel="cc:attributionURL" href="https://github.com/mghotbi/QIIME-compatible-database">QIIME2-Compatible-library</a> by <a rel="cc:attributionURL dct:creator" property="cc:attributionName" href="https://www.linkedin.com/in/mitra-ghotbi-78b34030/">Mitra & Marjan Ghotbi</a> is licensed under <a href="http://creativecommons.org/licenses/by/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">Attribution 4.0 International<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1"></a></p>

