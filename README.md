## Oligomer_assembly_SOP_labnote

**oligomer assembly** 관련 실험 기록을 체계적으로 관리하기 위한 디렉토리입니다.

각 실험은 별도의 폴더로 구분되어 있으며, 설계부터 수행, 결과 분석까지의 내용을 포함합니다.

------------------------------------------------------------------------

## 📁 폴더 구성

| 폴더명 | 내용 |
|-------------------------|----------------------------------------------|
| `001_oligo_assembly_test_GFP-mCherry` | sfGFP–mCherry 융합 유전자를 대상으로 한 oligo pool 기반 DNA assembly 실험 기록 |

추가 실험이 진행될 경우, 동일한 형식으로 `002_`, `003_` 등 번호를 부여하여 관리합니다.

------------------------------------------------------------------------

## 📄 폴더 구조 및 구성

각 실험 폴더는 다음과 같은 구조로 구성됩니다.

```         
📂 labnote/
labnote/
└── 001_oligo_assembly_test_GFP-mCherry/ # 실험 폴더
    ├── resources/
    │   ├── oligopool_order/          # 주문 oligopool 서열 파일
    │   ├── primers_order/            # 주문 프라이머 파일
    │   │   └── primer_stock/         # 프라이머 보관 위치 및 서열정보  
    │   └── vector_map/               # 벡터 맵 파일
    │
    ├── 001_WD010_General_Design_of_Experiment--Design_of_GFP-mCherry_Oligo_Assembly_Experiment.md   # 워크플로 연구일지 파일
    │                                  
    └── README.md                      # 실험 개요 문서
```
