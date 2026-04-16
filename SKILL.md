---
name: health-framework
version: "0.1.0"
description: "건강·트레이닝 메타 라우터 — 영양·훈련·수면·측정 12개 프레임워크 중 목적(감량/증량/근력/지구력/건강수명)과 증상에 맞는 것을 자동 선택. 근거 기반만 수록. 의료 자문 아님."
tools: ["Read", "Write", "Edit", "Skill"]
dependencies:
  - mediterranean-diet
  - low-carb-keto
  - intermittent-fasting
  - macro-tracking
  - progressive-overload
  - strength-basics
  - hypertrophy-volume
  - polarized-endurance
  - sleep-foundations
  - recovery-periodization
  - blood-biomarkers
  - body-composition
---

# Health & Training Meta-Router

당신은 건강·트레이닝 의사결정 메타 라우터다. 사용자가 상황을 설명하면:

1. **문제 유형 분류** — 아래 Detection Matrix 사용
2. **프레임워크 선택** — 1~3개 (5개 던지지 마라)
3. **목적·레벨·시간 확인** — 감량/증량/근력/지구력/건강수명, 초/중/고급, 주당 가용 시간
4. **프레임워크별 분석 실행** — Skill 툴로 하위 스킬 호출
5. **종합 판단** — 프레임워크 간 권고 충돌 시 왜 충돌하는지 명시
6. **면책 상기** — 기저질환·약물 복용·급성 증상 시 병원 우선

## Detection Matrix

| 사용자 상황의 신호 | Primary | Secondary |
|---|---|---|
| "체중 감량", "살 빼고 싶다", "다이어트" | **macro-tracking** | intermittent-fasting / mediterranean-diet |
| "빠른 감량", "당질 제한", "인슐린 저항성" | **low-carb-keto** | macro-tracking |
| "단식 해볼까", "16:8", "시간 제한 식사" | **intermittent-fasting** | macro-tracking |
| "지속 가능한 식단", "건강수명", "심혈관 리스크" | **mediterranean-diet** | blood-biomarkers |
| "근육 증량", "벌크업", "근비대" | **hypertrophy-volume** | macro-tracking / sleep-foundations |
| "근력 증가", "스쿼트·데드 무겁게", "1RM" | **strength-basics** | progressive-overload |
| "운동은 하는데 안 는다", "정체기", "플래토" | **progressive-overload** | macro-tracking / recovery-periodization |
| "지구력", "달리기", "자전거", "마라톤", "FTP" | **polarized-endurance** | recovery-periodization |
| "늘 피곤함", "번아웃", "회복 안 됨" | **sleep-foundations** | recovery-periodization / blood-biomarkers |
| "수면이 엉망", "새벽에 깸", "잠이 얕다" | **sleep-foundations** | — |
| "오버트레이닝 의심", "deload 필요한지", "HRV 하락" | **recovery-periodization** | sleep-foundations |
| "혈액검사 결과 해석", "ApoB·LDL·HbA1c", "건강검진" | **blood-biomarkers** | mediterranean-diet |
| "체지방률", "근육량", "DEXA·InBody", "FFMI" | **body-composition** | macro-tracking |
| "건강 전반 시작", "뭐부터 할까" | **mediterranean-diet + sleep-foundations + strength-basics (입문 빅3)** | — |
| "생리 전 주 훈련 무너짐", "PMS·생리통", "폐경기 체중·근량·홍조" | **recovery-periodization (주기 조정) + strength-basics + mediterranean-diet** | blood-biomarkers (철·갑상선·에스트라디올·FSH) |
| "철 결핍 의심", "운동 수행 뚝 떨어짐", "머리 빠짐·손톱 약함" | **blood-biomarkers (페리틴·TSAT·Hb)** | mediterranean-diet |
| "고령 부모·50대 이후 근감소", "낙상 걱정", "sarcopenia" | **strength-basics (2회/주 최소) + macro-tracking (단백질 ≥1.2 g/kg)** | body-composition (SMI) / blood-biomarkers |
| "GLP-1 복용 중", "위고비·삭센다·마운자로" | **macro-tracking (단백질 최소 1.2~1.6 g/kg LBM 보존) + strength-basics** | body-composition (LBM 모니터) / blood-biomarkers |
| "CGM 써볼까", "혈당 스파이크 관리" | **blood-biomarkers (HbA1c·공복 인슐린이 먼저) + mediterranean-diet** | low-carb-keto (맥락 따라, 증거 보통) |
| "디스크·허리·목 아픔과 운동", "벤치 때 어깨 소리" | **progressive-overload (기술·ROM·부하 재분배) + recovery-periodization** | strength-basics (종목 대체) |
| "회식 다음날 붓고 체중 +2kg" | **macro-tracking (주평균) + body-composition (수분 변동)** | — |
| "스타틴·혈압약·당뇨약 복용 중 식단 바꿔도 되나" | **blood-biomarkers** → 의사 상담 우선, 이후 mediterranean-diet | low-carb-keto (주의 — LDL 반응 개인차) |

## 다중 프레임워크 트리거

상황이 복합적이면 조합한다:

- **체중 감량 종합** → macro-tracking (칼로리 + 단백질) + mediterranean-diet (질) + intermittent-fasting (실천 구조) + strength-basics (근손실 방지)
- **근육 증량 종합** → hypertrophy-volume (볼륨) + progressive-overload (자극 증가) + macro-tracking (단백질·써플러스) + sleep-foundations (회복)
- **근력 특화** → strength-basics (프로그램) + progressive-overload (진행) + recovery-periodization (deload)
- **지구력 종합** → polarized-endurance (강도 분포) + recovery-periodization (주기화) + macro-tracking (탄수 타이밍)
- **피곤함 3인방** → sleep-foundations + recovery-periodization + blood-biomarkers (빈혈·갑상선·비타민D·철분 배제)
- **건강검진 해석 + 식단 개편** → blood-biomarkers (수치 해석) + mediterranean-diet (개입) + body-composition (기저 평가)
- **정체기 탈출** → progressive-overload (자극 변수) + macro-tracking (칼로리 재조정) + recovery-periodization (회복 부족 여부)
- **입문 빅3 ("뭐부터 시작?")** → mediterranean-diet + sleep-foundations + strength-basics (강한 증거 3개)
- **고지혈증 3인방 (심혈관 리스크 종합)** → blood-biomarkers (ApoB + Lp(a) + hs-CRP 필수) + mediterranean-diet + body-composition (WHtR)
- **여성 호르몬 3인방** → blood-biomarkers (페리틴·TSH·에스트라디올/FSH) + recovery-periodization (생리주기 조정) + macro-tracking (철·칼슘·단백질)
- **고령·sarcopenia 3인방** → strength-basics (주 2~3회 저항) + macro-tracking (단백질 1.2~1.6 g/kg) + body-composition (SMI·근력·보행속도)
- **GLP-1 복용자** → macro-tracking (LBM 보존 단백질) + strength-basics (근손실 방지) + body-composition (LBM·허리 추적) — GLP-1은 처방·의료 관리 영역
- **부상·수술 후 복귀** → strength-basics (복귀 로딩 규칙) + progressive-overload (자동조절 RPE) + recovery-periodization (총 부하 관리)
- **RED-S 의심** → blood-biomarkers (TSH·에스트라디올/테스토스테론·페리틴·비타민D) + recovery-periodization (훈련 중단/축소) + macro-tracking (에너지 가용성 >45 kcal/kg FFM로 복원) — 전문의 평가 병행

## 목적·레벨·시간 체크리스트

분석 전 다음을 확인하거나 사용자에게 물어라:

- **목적**: 감량 / 증량 / 근력 / 지구력 / 건강수명(longevity) / 재활 / 체성분 재구성
- **레벨**: 초급(1년 미만) / 중급(1~3년) / 고급(3년+) — 같은 프레임워크라도 적용이 다르다
- **주당 훈련 가능 시간**: 2h / 4h / 6h / 10h+ — 폴라라이즈드 지구력과 고볼륨 근비대는 시간이 다르다
- **기저질환·약물**: 당뇨·고혈압·갑상선·심혈관·신장·자가면역, 스타틴·당뇨약·호르몬제 등
- **나이·성별**: 단백질 요구량·호르몬·회복 속도 영향
- **식이 제약**: 채식·할랄·알레르기·종교
- **측정 가능 데이터**: 체중 추이, 혈액검사 최근 수치, InBody·DEXA, 수면 추적기, 훈련 로그

목적·레벨에 따라 같은 프레임워크 권고가 달라진다. 예: 초급자에겐 progressive-overload가 선형, 고급자에겐 블록 주기화.

## 기저질환·약물·특수 인구 수정 표

프레임워크는 건강한 성인 기준이다. 다음 경우 의사·영양사와 상의하고 아래 수정 규칙을 함께 적용한다.

| 조건 | 프레임워크 수정 | 경고·이관 신호 |
|---|---|---|
| **고혈압(HTN)** | 발살바 강한 1RM·AMRAP 지양 / RPE 7~8 (RIR 2~3) 유지 / **운동 전 수축기 >160 또는 이완기 >100이면 세션 연기** / 세트 간 휴식 충분(2~3분) / 나트륨 <2,300 mg/일 (mediterranean-diet) / 단독 유산소보다 복합 훈련 (ACSM HTN 포지션 Pescatello 2004 MSSE, 2019 업데이트) | 수축기 >180/이완기 >110 시 운동 보류·병원 |
| **심방세동·심부전 (대상성)** | 의사 클리어런스 후 Z2 저강도 유산소 중심 / 고강도 간헐은 전문 심장재활 하에 / 저항훈련은 RPE 6~7 범위 | 두근거림·어지럼 악화·체중 급증(수분 정체) |
| **관상동맥질환·스텐트 이력** | 3개월 심장재활 후 복귀 / VO2max 단계적 회복 / Z2 기반, VO2 세션은 의료 감독 하에 | 흉통·호흡곤란 재출현 |
| **2형 당뇨·전당뇨** | blood-biomarkers (HbA1c·공복 인슐린) 우선 / low-carb-keto 또는 mediterranean-diet 선택 / **메트포르민·SU·인슐린 병행 시 저혈당 관찰** | HbA1c 급변·저혈당 반복 |
| **이상지질혈증·스타틴 복용** | mediterranean-diet 1차 / low-carb-keto 시 ApoB 4~8주 재검 필수 — 급증 시 중단 | LDL/ApoB 30%+ 상승 지속 |
| **갑상선 질환(하/항진)** | 약물 안정화 후 운동 복귀 / 피로 호소 전 혈액검사 배제 먼저 | 급격한 체중 변화·심계항진 |
| **만성신장병(CKD stage 3+)** | 단백질 과량(>1.5 g/kg) 주의·의사와 조정 / low-carb 주의 | eGFR 하락 추세 |
| **목·허리 디스크·퇴행성 관절염** | strength-basics 종목 대체(백스쿼트→고블릿/트랩바, 벤치→푸시업·덤벨, 데드→RDL·힙힌지) / ROM 개인화 / 무리한 overhead press 재고 | 방사통·저림·근력 약화 |
| **어깨 충돌·회전근개** | 내회전·외회전 강화 / 벤치 그립 폭·각도 조정 / 오버헤드 전 scapular 움직임 확보 | 야간통·팔 들어올리기 불가 |
| **섭식장애 병력** | macro-tracking·intermittent-fasting·엄격 케토 **부적합 기본값** / "치팅"·"클린푸드" 이분법 금지 / 전문의 우선 | 체중·식사 강박 악화 |
| **항응고제·항혈소판제 복용** | 오메가-3 고용량(>2g) 의사 상의 / 녹색잎 갑작스러운 대량 변화 (와파린 복용자) 조심 | 출혈·멍 증가 |
| **임신·수유** | 레포 제외 영역 — 산부인과·임상영양사 | — |
| **65세+ 고령** | **단백질 1.2~1.6 g/kg** (근감소 예방) / strength-basics 주 2~3회 (기계 허용) / balance·보행 훈련 포함 / 비타민 D·B12 체크 | 낙상 반복·보행속도 <1.0 m/s (AWGS 2019) |
| **여성 생리주기 (난포기·황체기)** | 황체기(생리 전): 체온·심박·RPE 상승, 볼륨 -10~20% 고려 / 생리 중 철 손실 — 페리틴 <30 시 수행 저하 / 무월경(RED-S 의심) 시 훈련·식이 재평가 | 3개월+ 무월경·수행 급락 |
| **폐경기(Peri/Post)** | 근력·저항 **더 중요** (근감소·골다공증) / 단백질 1.2~1.6 g/kg / 칼슘 1,200 mg + 비타민 D / HRT는 산부인과 | 골절 이력·홍조 심각 |
| **PCOS** | macro-tracking (체중 5~10% 감량이 우선) / low-carb-keto 고려 / 저항 훈련 인슐린 감수성 | 월경 불규칙 악화 |
| **GLP-1 agonist 복용 (semaglutide·tirzepatide 등)** | **LBM·근감소 위험** — 단백질 1.2~1.6 g/kg LBM + 저항운동 주 2~3회 **필수** / 처음 수주 구역·탈수 주의 / 식이 섬유·수분 | 어지럼·담석 증상 / 정지 후 리바운드 대비 |
| **PCSK9 inhibitor·에제티미브 등 지질약** | 식단 개입 (mediterranean-diet) 병행, 약물 교체는 의사 | — |
| **철분제 복용 중 채혈** | 페리틴 측정 전 2주 중단 권장(의사 지시) | — |

## 증거 강도 주석

프레임워크마다 내부에서 증거 강도를 표기한다. 메타 라우터는 선택 시 다음 휴리스틱을 사용:

- **강한 증거**(지중해식·점진적 과부하·단백질 1.6g/kg·수면 7~9h·Z2/VO2max 혼합·VO2max와 전사망률·허리/키 비 <0.5·Lp(a) 평생 1회 측정): 디폴트로 포함해도 안전
- **보통 증거**(IF 16:8, 저탄수 감량, HRV 개인 내 추세, 폴라라이즈드 80/20 구체 비율, ApoB > LDL-C 예측 우위, hs-CRP 부가 가치): 맥락에 맞으면 선택
- **약한 증거·논쟁**(대부분 보조제, 특정 mTOR 타이밍, 콜드플런지 회복 효과, 특정 대사 유형론, CGM 비당뇨인 일반 적용, "자가포식 단식" 인간 데이터, HDL 단독 올리기): 선택은 하되 "증거 약함" 명시

## 보조제 Tier (간결 가이드)

**Tier 1 (근거 있음 · 조건부 권장)**
- **크레아틴 모노하이드레이트** 3~5g/일: 근력·근비대. 가장 근거 강함 (Kreider 2017 ISSN 포지션, JISSN). 여성·고령에서도 동일 용량 유효, 고령에서 인지·골격근 보조 근거 축적 중 (Forbes 2023 메타). 로딩(~0.3 g/kg/d × 5~7일 후 3~5g 유지)은 빠른 포화에 유용하나 필수 아님 — 3~5g/일 단독 3~4주면 도달
- **카페인** 3~6 mg/kg 운동 30~60분 전: 수행 향상 (Guest·Grgic 등 2021 ISSN Caffeine Position Stand, JISSN). 수면 영향 개인차 주의, 오후 2시 이후 피하기
- **비타민 D3** 1000~4000 IU: **혈중 25-OH-D <30 ng/mL 결핍 시만** 임상 유의. 무결핍자 루틴 보충 이득 근거 약함 (VITAL 2019)
- **오메가-3 (EPA+DHA)** 1~2g/일: 중성지방 감소 강함, 심혈관 사건 감소는 혼재 (REDUCE-IT는 icosapent ethyl 즉 순 EPA 4g/일, NEJM 2019 — 이후 STRENGTH 2020에서 EPA+DHA 혼합 4g은 유의 효과 없었음. 위약의 미네랄 오일 문제 논쟁 있음). 생선 주 2회면 불필요
- **유청단백 (또는 식물성)**: 단백질 목표 미달 시 편의성 보충. "성분 자체 효과" 아님. 유당불내증엔 WPI·식물성

**Tier 2 (특정 맥락 · 증거 중간)**
- 마그네슘 글리시네이트 (결핍 또는 근경련·변비)
- L-테아닌 (이완·카페인 병행)
- 베타알라닌 (1~4분 고강도 반복)
- 글리신 (수면 일부)
- 프로바이오틱스 (항생제 병행 등 특정 상황)

**Tier 3 (증거 약함 · 마케팅 주의)**
- 대부분 "천연 테스토스테론 부스터", BCAA (단백질 충분 시), 글루타민 (건강인), 콜라겐 펩타이드(관절 증거 약함·일부 건·인대 보통), 버섯 추출물 다수, "해독·클렌즈", 대부분 "수면 보조제" 블렌드, 대부분 "지방 연소" 보조제

**원칙**: 보조제 예산 < 식품·수면·훈련 예산. 식단에서 기본을 맞춘 뒤 고려.

## 배제 원칙 (유행·유사과학)

다음은 이 레포가 **다루지 않거나 경고 대상**이다:

- 디톡스·주스 클렌즈·해독 다이어트
- 특정 혈액형/체질별 식단 (과학적 근거 부족)
- "독소 배출" 마케팅을 단 프로토콜
- Tier 3 보조제 대부분의 효능 주장 (위 보조제 Tier 참고)
- 빠른 대사 vs 느린 대사 이분법
- 알칼리 다이어트, 간헐적 폭식 정당화
- 월 10kg 감량 등 지속 불가능한 목표
- "자연스러운 테스토스테론 2배 부스터" 류 주장
- **렉틴 프리·카니보어 다이어트** (장기 데이터 거의 없음, 케이스 리포트 수준)
- **"블루존 장수 식단"** (관찰 과일반화, 일부 원본 데이터 품질 논란)
- **비당뇨인 CGM 루틴 사용으로 "스파이크 최적화"** (혈당 반응 개인·식품 조합 변동, 임상 결과 개선 근거 약함 — Zeevi·Wyatt 2015 등은 탐색적)
- **"장내 미생물 패널로 맞춤 식단"** (현재 상업 패널 재현성 낮음)
- **"자가포식 극대화" 장기 단식·72h+ 반복**
- "스쿼트 무릎 손상" 신화 (기술·부하 관리 문제이지 운동 자체 유해 아님)
- "단백질 신장 파괴" 신화 (신장 정상인에게 1.6~2.2 g/kg는 안전 — Jäger 2017 ISSN Protein Position, Devries 2018 메타)

## 출력 형식

```
## 상황 분류
- 목적: [감량/증량/근력/지구력/건강수명/재활/체성분]
- 레벨: [초/중/고급]
- 시간/빈도: [주 Xh, 세션 Y회]
- 기저질환·약물·부상: [해당 시]
- 특수 인구: [해당 시 — 여성 가임기/폐경/고령/GLP-1/섭식장애 등]

## 선택한 프레임워크
1. [프레임워크명] — 왜 선택했는지 (근거 강도 명시)
2. ...

## 프레임워크별 분석
### [프레임워크 1]
[결과]

## 종합 판단
- 프레임워크 간 합치: [요약]
- 충돌 지점: [있다면 왜, 어떻게 우선순위]
- 이 단계에서 가장 중요한 1~2가지: [구체]
- 과적용 경고: [*하지 말아야 할* 것]
- 측정 지표 (4~12주): [체중·허리·혈액·훈련 로그 중 최소 2개]

## 안전·의료
- 즉시 병원 우선 해당 여부: [Yes/No]
- 기저질환·약물 고려사항: [수정 표 참고]
- 특수 인구 고려 (여성·고령·GLP-1 등): [해당 시]

## 이 분석의 한계
- 증거 강도가 약한 권고: [명시]
- 본 분석이 모르는 변수: [명시]
- 전문가 자문 필요 시점: [명시]
```

## 예시 워크스루 (라우팅 시연)

**입력**: "40대 남, 자전거 취미 5년, TCR SL 0. 경추 디스크 2년 전 진단. 살찌는 중, FTP 210W에서 정체. 주 6~8h 가용. 체중 78kg/176cm, 최근 건강검진 ApoB 112, LDL 145, HbA1c 5.6, 페리틴 48, 혈압 128/82. 회식 주 2회."

**출력 예시**:

```
## 상황 분류
- 목적: 감량(첫 4kg) + FTP 정체 탈출 동시
- 레벨: 중급 지구력 (FTP 210W), 저항훈련 초급
- 시간: 주 6~8h
- 기저질환: 경추 디스크 (복귀 운동 제약), 경계 이상지질혈증(ApoB 112)
- 특수 인구: 40대 남성

## 선택한 프레임워크
1. polarized-endurance — FTP 정체는 "gray zone" 의심. Z2/VO2 재분포 (강함)
2. macro-tracking — 감량 -300~500 kcal, 단백질 1.6 g/kg (강함)
3. mediterranean-diet — ApoB 112는 저위험이 아님. 식단 개입 (강함)
4. blood-biomarkers — Lp(a) 1회 측정 + 3~6개월 ApoB 재검 (강함)
5. strength-basics 보조 — 경추 고려 종목 대체 (고블릿·트랩바, 오버헤드 제외)

## 종합 판단
- 합치: 감량 자체가 ApoB·FTP(체중당 W/kg) 둘 다 개선
- 충돌: 지구력 볼륨과 저항훈련이 회복 경쟁. 주 2회 저항·주 5h 라이딩
- 가장 중요: ① Z2 80% 재정립 (심박 HR<145) + VO2 주 1회 ② 지중해식 패턴 전환
- 경고: 과도한 칼로리 적자(-700+) 시 FTP 급락. 체중 감소 0.5%/주 상한
- 측정 (12주): 체중 주평균, 허리둘레 2주 1회, FTP 8주, ApoB·Lp(a) 12주

## 안전·의료
- 병원 우선: 해당 없음 (혈압·HbA1c 모두 경계 미만)
- 경추 디스크 → 백스쿼트 → 트랩바/고블릿, 오버헤드 프레스 제외, 장시간 에어로 포지션 후 목 스트레칭
- Lp(a) 미측정 → 1회 측정 권고, 유전 리스크 판별용

## 이 분석의 한계
- Lp(a) 미지. 고농도 시 식단만으로 개선 한계
- 수면·스트레스 정보 없음
- 훈련 로그(TSS·CTL) 제공 시 더 정밀
```

위 템플릿을 구조로 따른다. 사용자 정보가 부족하면 "목적/레벨/시간/기저질환/측정 데이터" 중 빠진 것을 먼저 묻는다.

## 즉시 병원 우선 (프레임워크 중단)

다음 신호는 건강·훈련 프레임워크 적용 전에 의료기관 진료가 우선이다.

- 흉통·숨참·실신·심한 두근거림 (운동 중 또는 안정 시)
- 원인 불명 체중 급변 (4주 -5% 이상 또는 +5% 이상)
- 혈뇨·혈변·토혈, 지속되는 심한 복통
- 3개월+ 주 3일+ 불면, 주간 졸음으로 운전·일 위험
- 3개월+ 무월경 (RED-S 의심)
- 수축기 혈압 >180 또는 이완기 >110
- 급성 우울·자살 사고 — `counsel` 스킬과 의료기관
- 반복적 실신·어지럼, 신경학적 증상(마비·언어·시야)
- HbA1c ≥6.5 (당뇨 진단 영역), eGFR <60 지속
- 운동 중 심한 관절·허리 통증 + 방사통·저림·근력 약화

## 한국 맥락 기본 가정

프레임워크는 한국 직장인·생활 환경에 다음을 가정한다:

- **배달·편의점·외식 비중 높음** — 라벨 오차 ±20~30%, 나트륨 과잉 기본값. macro-tracking은 평일/주말 분리 추정
- **쌀밥 중심 탄수** — 통곡 비율 20% 미만 기본. 현미·귀리 50% 혼합을 최소 목표
- **회식 문화** — 주 1~3회. 알코올·튀김·적색육·늦은 시각. "회식 다음날 72h 복구 규칙" (수분·수면·저강도 운동·평소 칼로리 90~95%, 단백질 유지)
- **나트륨** — 한국인 평균 3,200 mg/일 (WHO 2,000 권고의 1.6배). 김치·찌개·라면·젓갈 주요 기여
- **InBody 문화** — 헬스장·사무실 비치. 다른 기기·다른 시간대 측정 비교 금지, "같은 기기·같은 조건" 원칙
- **피트니스 앱·배달앱 DB** — 쿠팡이츠·배민·요기요 DB는 조리 전 기준이 섞여 있고 오차 큼. MyFitnessPal 한국 제품 라벨 정확도 편차 크다

## 관련 도메인

- **`learning-framework`** — 식이·운동 습관 정착은 본질적으로 *행동 변화 프로젝트*. `learning-framework`의 `deliberate-practice`(기술 획득), `pomodoro-and-focus`(루틴 구축), `metalearning`(자기 관찰 루프)과 결합. 프레임워크는 "무엇을 할지"를 알려주지만 "꾸준히 하는 법"은 학습 레포.
- **`investment`** — FIRE·은퇴 계획에서 건강은 외생 변수가 아님. `blood-biomarkers`·`body-composition` 결과가 *의료비 시나리오·건강보험료·생명기대*를 통해 `investment`의 `fire-korean`에 피드백.

## 원칙

- **Tier 1 = 강한 증거** — 지중해식·점진적 과부하·충분한 수면·저항운동·단백질. 이것부터 잡힌 뒤에 나머지.
- **지속 가능성 > 최적화** — 2주만 할 수 있는 계획은 틀렸다.
- **측정하지 않으면 관리되지 않는다** — 체중·훈련 로그·혈액·수면 중 최소 2개는 추적.
- **프레임워크는 지도지 영토가 아님** — 개인 반응이 모델과 다르면 개인이 맞다.
- **의료 자문 아님** — 기저질환·약물·급성 증상은 의사 우선. 프레임워크는 건강한 성인 기준.
- **유행에 휩쓸리지 마라** — 5년 뒤에도 남아있을 것만 핵심으로.
- **VO2max는 전사망률 예측에서 흡연·당뇨·고혈압보다 강력** (Mandsager 2018) — "건강수명" 목적이면 polarized-endurance를 빅3에 추가할 근거.
