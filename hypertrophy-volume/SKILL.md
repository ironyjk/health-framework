---
name: hypertrophy-volume
version: "0.1.0"
description: "근비대 볼륨 관리 — 근군별 주간 세트 수(MV/MEV/MAV/MRV)로 자극 정량화. PPL, Upper/Lower, RP 블록. 반복수 5~30에서 실패 근접이면 모두 유효. 장기적으로 볼륨 주기화."
---

# Hypertrophy Volume Management

## 한 줄 요약

**근비대의 1차 변수는 볼륨(근군별 주간 실패 근접 세트 수).** 5~30 rep 구간은 근비대에 대체로 등가. 핵심은 **MEV·MAV·MRV 구간을 찾아 시간에 따라 오가는 것**.

## 증거 강도

- 주간 세트 수와 근비대 용량반응: **강함** (Schoenfeld·Krieger 메타분석)
- 5~30 rep 범위 등가: **보통~강함** (실패 근접 조건)
- 세트당 실패 근접(RIR 0~3)의 중요성: **강함**
- 빈도 ≥2회/주/근군 > 1회: **보통** (볼륨 동일 시 차이 작음)
- 특정 "근비대 전용" 테크닉(드롭셋·레스트폴즈): **보통** (시간당 효율 이점, 총 볼륨 초과분은 불명)

## 이론·증거 기원

- **Brad Schoenfeld** — 근비대 메타연구 다수. *Science and Development of Muscle Hypertrophy*
- **James Krieger** — 세트-반응 메타분석
- **Mike Israetel · Renaissance Periodization(RP)** — MV/MEV/MAV/MRV 모델 대중화
- **Eric Helms** — Muscle & Strength Pyramid 시리즈
- **Chad Wesley Smith · Juggernaut**

## 핵심 개념

### 1. 볼륨 단위
- **Hard Set** = 실패로부터 0~3 rep 거리(RIR 0~3) 세트
- 근비대 볼륨은 주간 근군별 hard set 수로 측정

### 2. 볼륨 구간 (RP 모델)
- **MV (Maintenance Volume)**: 근량 유지 최소
- **MEV (Minimum Effective Volume)**: 성장 시작 최소. 근군별 대략 주 8~10 세트
- **MAV (Maximum Adaptive Volume)**: 최대 이익 구간. 근군별 주 12~20
- **MRV (Maximum Recoverable Volume)**: 이상 지속 시 과부하 누적

| 근군 | MV | MEV | MAV | MRV |
|---|---|---|---|---|
| 대흉근 | 4 | 8 | 12~20 | 22 |
| 광배/등 | 6 | 10 | 14~22 | 25 |
| 대퇴사두 | 6 | 8 | 12~18 | 20 |
| 햄스트링 | 3 | 6 | 10~16 | 18 |
| 둔근 | 0 | 0 | 4~12 | 16 |
| 어깨(측) | 0 | 8 | 16~22 | 26 |
| 삼두 | 4 | 6 | 10~14 | 18 |
| 이두 | 5 | 8 | 12~20 | 22 |

개인차 ±30%. 자기 자신의 MEV/MRV는 실제 반응으로 확인.

### 3. 반복 범위
- **5~10 rep**: 중량·시간 효율 좋음
- **10~20 rep**: 국소 근피로 신호 강함
- **20~30 rep**: 관절 부담 낮음, 컨디셔닝 효과도
- **결론**: 실패 근접이면 근비대 동등. 종목·관절에 맞게 배분

### 4. 빈도
- 근군당 **주 2~3회**가 주 1회보다 대체로 우수 (볼륨 동일 시 차이 작음, 분산이 회복에 유리)

### 5. 프로그래밍 블록 (RP 계열)
```
Block 1 (Accumulation): MEV → MRV, 4~6주
Deload 1주
Block 2 (Intensification): 강도 상승, 볼륨 하락
Deload
```

## 언제 쓰나

- **근비대·체성분 재구성**이 목표
- 근력 기초 갖춘 뒤(6~12개월+)
- 시각적 목표(보디빌딩·대회·피지크)
- 부상·재활 후 국소 자극 필요
- 근력 프로그램 보조운동 설계

## 대표 분할

### PPL (Push/Pull/Legs) — 주 6일 고급
```
Day 1 Push: 벤치·인클라인·숄더프레스·레터럴·딥
Day 2 Pull: 데드·풀업·바벨로우·페이스풀·컬
Day 3 Legs: 스쿼트·RDL·레그프레스·카프·힙쓰러스트
반복 2회 + 휴식 1일
```

### Upper/Lower — 주 4일 (중급)
```
Mon Upper / Tue Lower / Thu Upper / Fri Lower
복합 1~2 + 보조 2~3개/근군
```

### Full Body — 주 3일 (중급, 시간 제약)
```
복합 2 + 주당 근군별 MEV 채우기
```

### Arnold Split·Bro Split (주 1회/근군) — 덜 추천
- 볼륨 한계, 회복 비효율이나 고급자에겐 선호도 요소

## 운동 선택 원칙

- 각 근군별 **다른 각도/길이** 2~3개
- **Stretch 위치에서 부하**가 강한 종목 우선 (최근 문헌)
  - 대흉 → 인클라인 덤벨·펙덱
  - 햄스트링 → RDL·시티드레그컬
  - 대퇴사두 → 하이바 스쿼트·핵스쿼트
  - 이두 → 인클라인컬
- 복합 운동으로 기반, 단일 관절로 미세 조정

## 실전 체크리스트

- 훈련 로그 (세트·중량·반복·RIR)
- 4~6주 블록마다 주 세트 수 +2~4씩 증가 → MRV 근접 → deload
- 주관 지표: 근육통 2~3일 지속, 수행 저하, 수면 악화 = MRV 경고

## 안티패턴

- **총 볼륨만 추구**, 강도 RIR 무시 → "쓰레기 볼륨"
- **매주 실패까지 모든 세트** → 신경계 소모, MRV 조기 도달
- **근군별 불균형** — 거울 근육(가슴·이두·복근)만 과다, 등·햄스트링 부족
- **반복 범위 편식** — 저반복만 또는 고반복만
- **영양 간과** — 증량 시 써플러스, 단백질 1.6~2.0 g/kg 없이 고볼륨은 근손실
- **호르몬 "비법" 탐색** — 자연 범위 내 근비대 상한은 존재 (Helms의 maximum adaptable potential)
- **"펌프 = 성장" 신화** — 단기 혈류·수분. 성장 신호와 동일시 금지
- **휴식 30초 고집** — 복합운동 2~3분, 단일관절 1~2분이 볼륨·수행에 유리

## 여성·고령·GLP-1 적용

- **여성**: 볼륨 반응은 남성과 유사, 총 제지방 증가 절대량은 더 작음 (호르몬). 근비대 원리는 동일. 하체 반응성이 남성 대비 상대적 강함 (일반 경향)
- **여성 생리주기 (선택 조정)**: 난포기 PR·고볼륨 유리, 황체기는 RPE 여유(RIR +1) 또는 보조운동으로 전환. 강제 규칙 아님
- **폐경기 여성**: 저항훈련 중요도 상승 (골밀도·근감소). 볼륨 유지, 회복 시간 연장
- **고령(65+)**: MEV 낮게 시작(6~8세트/주), 강도 70~80% 1RM, RIR 2~3. 주 2~3회 전신. 기계·덤벨 허용
- **GLP-1 복용자**: LBM 방어 목적 — MEV 볼륨 유지 + 단백질 1.2~1.6 g/kg LBM. 고볼륨 증량 블록은 회복·식욕 저하로 비현실적

## 한국 헬스장 현실

- **복합운동 중량 가용** 편차 — 24시간 헬스장·아파트 gym은 덤벨 30kg 상한 흔함. 대안: 머신·고반복·편측·pause reps
- **혼잡 시간대**(19~22시)에 PPL·4분할 고볼륨 진행 어려움 → 서킷·슈퍼세트로 압축
- **PT 받는 경우**: 프로그램 일관성 우선. 매 PT마다 부위 바꾸는 "피트니스 쇼"는 MEV도 못 채움

## 한계

1. **절대 근력·스프린트엔 비효율** — `strength-basics` 보완
2. **시간 비용 큼** — 주 4~6일, 세션 60~90분
3. **MEV/MRV 개인차 큼** — 남의 표를 그대로 쓰면 부정확
4. **유전적 상한 존재** — 반응자(responder) 편차
5. **지구력·심혈관엔 직접 기여 적음**
6. **보디빌딩 문화의 과장된 주장** — 해독 셰이크·mTOR 윈도우 등 대부분 3차 변수 이하

## 함께 쓰는 것·이 프레임워크가 *틀렸을 때*

- 과부하 원칙 → `progressive-overload`
- 근력 메인 + 보조 근비대 → `strength-basics`
- 회복·deload → `recovery-periodization`
- 영양 정확도 → `macro-tracking`
- 수면 부족 시 → `sleep-foundations` 먼저
- 체성분 추적 → `body-composition`

## 추가 학습 자료

- Schoenfeld, B. *Science and Development of Muscle Hypertrophy.*
- Israetel, M. et al. *Scientific Principles of Hypertrophy Training.*
- Helms, E., Morgan, A., Valdez, A. *The Muscle & Strength Pyramid: Training.*
- Schoenfeld, B. et al. (2017). "Dose-response relationship between weekly resistance training volume and increases in muscle mass." *J Sports Sci.*
- Krieger, J.W. (2010). "Single vs. multiple sets of resistance exercise for muscle hypertrophy." *JSCR.*
