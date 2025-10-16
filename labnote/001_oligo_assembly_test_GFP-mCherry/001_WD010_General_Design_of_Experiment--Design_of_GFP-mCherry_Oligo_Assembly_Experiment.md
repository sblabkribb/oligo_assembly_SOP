---
title: WD010 General Design of Experiment - GFP-mCherry oligo assembly test
experimenter: 윤예린
created_date: '2025-10-13'
end_date: '2025-10-15 18:00'
last_updated_date: '2025-10-16'
---

## \[WD010 General Design of Experiment\] Design of GFP-mCherry Oligo Assembly Experiment

> Briefly describe this workflow (the description below is a template, modify it to fit your purpose) This workflow provides a general-purpose approach for experimental design using the Design of Experiment methodology. It allows for the independent design of variables from various domains to optimize experimental conditions.

## 🗂️ Related Unit Operations

-   \[USW030 Vector Design GFP-mCherry design\]
-   \[USW010 DNA Oligomer Pool Design\_ sfGFP-mCherry oligo assembly를 위한 oligo pool & primer design\]

------------------------------------------------------------------------

### \[USW030 Vector Design GFP-mCherry design\]

-   **Description**: Oligo pool assembly test를 위한 **sfGFP-mCherry vector design** 단계

    oligo assembly가 제대로 이루어졌는지를 간단히 확인하기 위해, 조립된 **sfGFP–mCherry DNA fragment**를 **pRSFDuet vector**에 cloning 한 뒤 **E. coli DH5α**에 transformation하여 형광 발현을 관찰하는 실험을 설계함. 이 실험 설계에 맞춰, oligo assembly로 합성할 **sfGFP–mCherry cassette 서열**을 직접 디자인하였으며, promoter, RBS, terminator 등 발현 조절 요소를 포함하여 **assembly 및 발현 검증이 가능한 형태**로 구성함.

#### Meta

-   Experimenter: 윤예린
-   Start_date: '2025-10-13 10:29'
-   End_date: ''

#### Input

-   아래는 oligo assembly를 수행할 GFP-mCherry cassette 디자인에 사용한 서열 정보

| Part | Name | Sequence / File | Description | Sourc |
|---------------|---------------|---------------|---------------|---------------|
| Vector | pRSF-Duet | [vector_pRSFduet.dna](./resources/vector_map/vector_pRSFduet.dna) | RSF origin, KanR | 김홍연 연구원 |
| CDS | sfGFP-mCherry | [sfGFP_GGSGGS_mCherry.dna](./resources/vector_map/sfGFP_GGSGGS_mCherry.dna) | sfGFP-linker-mCherry fusion | 김홍연 연구원 |
| Promoter | BBa_J23110 | `tttacggctagctcagtcctaggtacaatgctagc` | Anderson constitutive promoter | *iGEM Registry* |
| RBS | BBa_B0030 | `TCTAGAGATTAAAGAGGAGAAATACTAG` | bacterial ribosome binding site | *iGEM Registry* |
| Terminator | BBa_B0015 | `aggcatcaaataaaacgaaaggctcagtcgaaagactgggcctttcgttttatctgttgtttgtcggtgaacgctctctactagagtcacactggctcaccttcgggtgggcctttctgcgtttata` | rrnB T1+ T7 Terminator | *iGEM Registry* |

#### Equipment

-   Software : Snapgene

#### Method

-   이번 단계에서는 oligo assembly가 제대로 이루어졌는지를 간단히 확인하기 위해, 조립된 sfGFP–mCherry DNA fragment를 pRSFDuet vector에 cloning 한 후 E. coli DH5α에 transformation하여 형광 발현을 관찰하는 실험을 설계함.

-   oligo pool 기반 assembly의 성공 여부를 형광 발현 여부로 1차적으로 판단하고자 함.

-   단일 GFP(약 700 bp)는 크기가 작아 oligo pool 주문 단가와 DNA 합성 단가의 차이를 고려했을 때 비용 효율성이 낮다고 판단함. 그래서 GFP와 mCherry를 flexible linker(GGSGGS) 로 연결한 fusion protein 형태로 구성함.

-   **Design rationale** :

    -   Promoter / RBS\
        형광 발현은 확인 가능하지만, 세포 성장에 부담을 줄이기 위해 중간 세기의 constitutive promoter (BBa_J23110) 와 RBS (B

    <!-- -->

    -   Terminator\
        rnB T1 terminator 를 cassette 내에 포함시킴.

    <!-- -->

    -   Cloning compatibility\
        Gibson assembly로 pRSFDuet backbone에 삽입할 수 있도록 cassette 양 끝에 30 bp overlap sequence 를 추가함.

-   Construrc overview :

    `overlap1 (30 bp)– Promoter (BBa_J23110) – RBS (BBa_B0030) – sfGFP_mCherry – Terminator (rrnB T1) - overlap2 (30bp)`

#### Output

아래는 본 단계에서 생성된 vector map 파일

| File | Description | Path |
|-------------------|----------------------------------|-------------------|
| [insert_sfGFP_mCherry_cassette.dna](./resources/vector_map/insert_sfGFP_mCherry_cassette.dna) | oligo assembly를 수행하기 위해 디자인된 insert 서열 (sfGFP–mCherry cassette, 약 1.7 kb) | `resources/vector_map/insert_sfGFP_mCherry_cassette.dna` |
| [final_pRSFduet_sfGFP_mCherry.dna](./resources/vector_map/final_pRSFduet_sfGFP_mCherry.dna) | 최종 assembled vector | `resources/vector_map/final_pRSFduet_sfGFP_mCherry.dna` |

#### Results & Discussions

-   디자인한 insert 서열을 기반으로 **Desembler**를 사용하여 oligo design을 수행할 예정임.\

------------------------------------------------------------------------

### \[USW010 DNA Oligomer Pool Design\_ sfGFP-mCherry oligo assembly를 위한 oligo pool & primer design\]

-   **Description**: Desembler를 사용하여 oligo pool을 디자인함. 본 단계에서는 sfGFP–mCherry cassette (\~1.7 kb)을 oligo 기반으로 합성하기 위해, 각 oligo의 길이, overlap, GC%, Tm 균형 등을 고려해 pool을 디자인함. 추가적으로 oligo assembly 에 필요한 primer 및 vector backbone PCR 에 필요한 primer 도 함께 디자인함.

#### Meta

-   Experimenter: 윤예린
-   Start_date: '2025-10-14 10:53'
-   End_date: ''

#### Input

| Source | Description |
|-----------------------------|-------------------------------------------|
| [insert_sfGFP_mCherry_cassette.dna](./resources/vector_map/insert_sfGFP_mCherry_cassette.dna) | oligo assembly용으로 디자인된 1.7 kb insert 서열 |

#### Equipment

-   Software : Desembler, SapGene

#### Method

1.  **Desembler 를 이용한 oligo design**

    -   Desembler로 1차 oligo 설계를 수행함.

    -   자세한 내용 추가해야 함 !! ✨✨✨

    -   Desembler로 부터 1차로 얻은 oligo desin 결과를 `final_pRSFduet_sfGFP_Cherry.dna` file에 SnapGene 에서 Import Primers from a file 기능을 사용해 불러옴. 이후 서열을 시각적으로 확인하면서 디자인이 적절하게 이루어졌는지 추가 확인함.

    -   이후, 각 Oligo 간 overlap 길이와 Tm 값을 확인하고, 수동으로 조정했음. → 최종 조건**:** overlap ≥ 20 bp, Tm = 58–61 °C

2.  **oligo assembly용 primer design**

    -   oligo assembly 시 양단 증폭용 primer를 추가로 설계함.
        -   overlap_F1 / overlap_R1

3.  **vector backbone PCR용 primer design**

    -   pRSFDuet vector backbone을 증폭하기 위한 primer를 별도로 설계함.
        -   pRSFduet_F1 / pRSFduet_R1

-   primer 서열은 아래 표 또는 Output 파일 참조

| primer name | 5'-Seq-3'                      |
|-------------|--------------------------------|
| overlap_F1  | ctcatgttagtatccggatatagttcctc  |
| overlap_R1  | caaataggggtctaacttacattaattgcg |
| pRSFduet_F1 | cgcaattaatgtaagttagacccc       |
| pRSFduet_R1 | ggaggaactatatccggatactaacat    |

4.  **Oligo pool 및 Primer 주문**

-   Oligo pool은 **IDT**와 **TWIST** 두 업체에 견적 문의 및 구매 요청을 진행함. (주문일: 2025.10.15)

    -   **IDT 의 경우**

        1.  주문 파일을 `hjy@genere.co.kr` (Geneer)에 전달하여 견적서 문의
        2.  견적서 확인 후, 주문 계정 나유진 박사님과 상의
        3.  계정 확정 후 구매요청서 작성하여 구매 진행 - [견적서 파일 (Geneer IDT)](./resources/oligopool_order/251015_geneer_IDT_OligoPool.xlsx)

    -   **TWIST 의 경우**

        1.  주문 파일을 [TWIST 홈페이지](https://www.twistbioscience.com/)에 직접 업로드
        2.  견적서 확인 후, 주문 계정 나유진 박사님과 상의
        3.  계정 확정 후 구매요청서 작성하여 구매 진행 - [견적서 파일 (Xogene TWIST)](./resources/oligopool_order/251015_xogene_TWIST_Q-556728.xlsx)

    -   Primer 는 Macrogen 에 주문함 (주문일: 2025.10.15, 주문번호: HO00426248)

#### Output

-   아래는 본 단계에서 생성된 **oligo pool 및 primer order 파일**임.

| NO. | File | Description | Path |
|----------------|----------------|-------------------------|----------------|
| 1 | [oligo_order_251015_sfGFP_mCherry_58-61Tm.xlsx](./resources/oligopool_order/oligo_order_251015_sfGFP_mCherry_58-61Tm.xlsx) | overlap 길이 및 Tm 값이 포함된 oligo pool 파일 | `resources/oligopool_order/oligo_order_251015_sfGFP_mCherry_58-61Tm.xlsx` |
| 2 | [oligo_order_251015_sfGFP_mCherry.xlsx](./resources/oligopool_order/oligo_order_251015_sfGFP_mCherry.xlsx) | IDT, TWIST oligo pool 주문 파일 | `resources/oligopool_order/oligo_order_251015_sfGFP_mCherry.xlsx` |
| 3 | [primer_order_251015_sfGFP_mCherry.xls](./resources/primers_order/primer_order_251015_sfGFP_mCherry.xls) | oligo assembly 및 PCR 검증용 primer 주문 목록 파일 | `resources/primers_order/primer_order_251015_sfGFP_mCherry.xls` |

#### Results & Discussions

-   Desembler로부터 생성된 oligo pool 서열의 overlap과 Tm 값을 수동 조정했음.
-   sample 수가 늘어날 경우, 수동으로 조정하는 과정에 시간이 많이 소요될 것으로 예상됨.\
    → 다수 샘플을 처리할 때, 현재 연구실에서는 어떻게 자동화 또는 일괄 조정을 수행하고 있는지 확인 필요.
-   현재 Desembler 사용 시, oligo 조정 페이지에서 가장 마지막 oligo 서열이 수동으로 수정되지 않는 오류가 있음. → 확인 필요.
-   향후 oligo pool 및 primer 도착 후 실험을 진행할 계획임.